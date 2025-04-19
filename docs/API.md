# 🔌 Documentação da API

## 🔧 Tecnologias

- **Framework**: Spring Boot 3.2
- **Documentação**: SpringDoc OpenAPI (Swagger)
- **Autenticação**: Firebase Admin SDK
- **Validação**: Spring Validation
- **Serialização**: Jackson
- **Testes**: JUnit + Mockito

## Visão Geral
API REST do sistema Mestre dos Jogos, desenvolvida com Spring Boot.


## Autenticação
Todas as requisições devem incluir o token JWT no header:
```
Authorization: Bearer {token}
```

## Endpoints

### Jogos

#### Listar Jogos
```http
GET /jogos
```

Parâmetros de Query:
- `disponivel` (boolean): Filtrar por disponibilidade
- `categoria` (string): Filtrar por categoria
- `jogadores` (number): Número de jogadores
- `page` (number): Página atual
- `size` (number): Itens por página

Resposta:
```json
{
  "content": [
    {
      "id": "string",
      "nome": "string",
      "descricao": "string",
      "precos": {
        "diaria_unica": 25.0,
        "tres_diarias": 30.0,
        "cinco_diarias": 40.0
      },
      "disponivel": true,
      "categorias": ["string"],
      "tags": ["string"],
      "jogadores": {
        "minimo": 2,
        "maximo": 4
      },
      "tempoJogo": 30,
      "idadeMinima": 10
    }
  ],
  "pageable": {
    "pageNumber": 0,
    "pageSize": 20,
    "totalElements": 100
  }
}
```

#### Detalhes do Jogo
```http
GET /jogos/{id}
```

### Aluguéis

#### Criar Aluguel
```http
POST /alugueis
```

Request:
```json
{
  "jogoId": "string",
  "tipoDiaria": "DIARIA_UNICA",
  "dataRetirada": "2024-03-20T14:00:00",
  "dataDevolucao": "2024-03-21T14:00:00"
}
```

#### Listar Aluguéis do Usuário
```http
GET /alugueis/meus
```

#### Confirmar Devolução
```http
POST /alugueis/{id}/devolucao
```

### Usuários

#### Cadastro
```http
POST /usuarios
```

#### Perfil
```http
GET /usuarios/perfil
```

### Avaliações

#### Criar Avaliação
```http
POST /jogos/{id}/avaliacoes
```

### Pagamentos

#### Criar Pagamento
```http
POST /pagamentos
```

## Códigos de Erro

| Código | Descrição                    |
|--------|------------------------------|
| 400    | Requisição inválida         |
| 401    | Não autorizado              |
| 403    | Acesso negado               |
| 404    | Recurso não encontrado      |
| 409    | Conflito                    |
| 422    | Entidade não processável    |
| 500    | Erro interno do servidor    |

## Webhooks

### Notificação de Pagamento
```http
POST /webhooks/pagamento
```

### Notificação de Transporte
```http
POST /webhooks/transporte
```

## Rate Limiting
- 100 requisições por minuto por IP
- 1000 requisições por hora por usuário

## Versionamento
- Versão atual: v1
- Formato: `/v{version}/`
- Deprecated versions: None

## Ambiente de Testes
- URL: `https://api-staging.mestredosjogos.com.br/v1`
- Credenciais de teste disponíveis no portal do desenvolvedor

## Exemplos de Uso

### cURL
```bash
# Listar jogos disponíveis
curl -X GET "https://api.mestredosjogos.com.br/v1/jogos?disponivel=true" \
  -H "Authorization: Bearer {token}"

# Criar aluguel
curl -X POST "https://api.mestredosjogos.com.br/v1/alugueis" \
  -H "Authorization: Bearer {token}" \
  -H "Content-Type: application/json" \
  -d '{
    "jogoId": "123",
    "tipoDiaria": "DIARIA_UNICA",
    "dataRetirada": "2024-03-20T14:00:00"
  }'
```

### JavaScript
```javascript
// Exemplo de chamada com fetch
const response = await fetch('https://api.mestredosjogos.com.br/v1/jogos', {
  headers: {
    'Authorization': `Bearer ${token}`
  }
});
const jogos = await response.json();
```

## Considerações de Segurança
- Todas as requisições devem usar HTTPS
- Tokens JWT expiram em 24 horas
- Implementação de CORS configurável
- Rate limiting por IP e usuário
- Validação de entrada em todas as requisições 
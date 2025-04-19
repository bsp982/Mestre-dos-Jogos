# 💻 Guia de Desenvolvimento

## 🔧 Stack de Desenvolvimento

### Frontend
- **IDE**: VS Code
  - Extensões:
    - Angular Language Service
    - Tailwind CSS IntelliSense
    - Material Icon Theme
    - ESLint
    - Prettier
- **Ferramentas**:
  - Angular CLI
  - Node.js
  - npm
  - Chrome DevTools

### Backend
- **IDE**: IntelliJ IDEA
  - Extensões:
    - Spring Boot
    - Java
    - Lombok
    - Checkstyle
- **Ferramentas**:
  - JDK 21
  - Maven
  - Postman
  - Firebase CLI

### Banco de Dados
- **Ferramentas**:
  - Firebase Console
  - Firebase Emulator
  - Firebase CLI

### Versionamento
- **Git**:
  - Conventional Commits
  - Git Flow
  - GitHub Actions

## Ambiente de Desenvolvimento

### Requisitos
- Java Development Kit 21
- Node.js 20+
- Angular CLI 18
- Docker
- Git
- IDE recomendada: IntelliJ IDEA ou VS Code

### Configuração Inicial

#### 1. Clone do Repositório
```bash
git clone https://github.com/mestre-dos-jogos/platform.git
cd platform
```

#### 2. Configuração do Backend
```bash
cd backend
./mvnw clean install
```

Arquivo `application-dev.yml`:
```yaml
spring:
  application:
    name: mestre-dos-jogos-api
  profiles:
    active: dev

firebase:
  config:
    path: firebase-credentials.json

security:
  jwt:
    secret: your-secret-key
    expiration: 86400000 # 24 hours

cors:
  allowed-origins: http://localhost:4200
```

#### 3. Configuração do Frontend
```bash
cd frontend
npm install
```

Arquivo `environment.development.ts`:
```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080/api/v1',
  firebase: {
    apiKey: 'your-api-key',
    authDomain: 'your-auth-domain',
    projectId: 'your-project-id',
    // ... outras configs
  }
};
```

### Estrutura do Projeto

```
mestre-dos-jogos/
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   │   ├── core/          # Serviços core, guards, interceptors
│   │   │   ├── shared/        # Componentes, pipes, utils compartilhados
│   │   │   ├── features/      # Módulos de funcionalidades
│   │   │   └── layouts/       # Templates e layouts
│   │   ├── assets/
│   │   └── environments/
│   └── ...
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   └── resources/
│   │   └── test/
│   └── ...
└── docs/
```

## Padrões de Código

### Convenções de Nomenclatura

#### Java
```java
// Classes
public class JogoService {
    // Campos privados em camelCase
    private final JogoRepository jogoRepository;
    
    // Métodos em camelCase
    public List<Jogo> buscarJogosDisponiveis() {
        // implementação
    }
}
```

#### TypeScript/Angular
```typescript
// Components
@Component({
  selector: 'app-jogo-card',
  // ...
})
export class JogoCardComponent {
  // Properties em camelCase
  private readonly jogoService: JogoService;
  
  // Métodos em camelCase
  public async carregarJogo(): Promise<void> {
    // implementação
  }
}
```

### Boas Práticas

#### Backend
1. **Controllers**
   - Um controller por recurso
   - Métodos concisos
   - Validação via annotations
   - Documentação Swagger

2. **Services**
   - Lógica de negócio isolada
   - Princípio da Responsabilidade Única
   - Injeção de dependências

3. **Repositories**
   - Queries otimizadas
   - Nomes descritivos
   - Cache quando apropriado

#### Frontend
1. **Componentes**
   - Componentização inteligente
   - Lazy loading
   - OnPush change detection
   - Componentes puros quando possível

2. **Services**
   - Estado centralizado
   - Cache de requisições
   - Tratamento de erros

3. **Styles**
   - BEM methodology
   - Variáveis CSS
   - Responsividade mobile-first

## Fluxo de Trabalho

### Git Flow
1. **Branches**
   - `main`: produção
   - `develop`: desenvolvimento
   - `feature/*`: novas funcionalidades
   - `hotfix/*`: correções urgentes
   - `release/*`: preparação para release

2. **Commits**
   ```
   feat: adiciona sistema de pontos
   ^--^  ^--------------------^
   |     |
   |     +-> descrição
   |
   +-------> tipo: feat, fix, docs, style, refactor, test, chore
   ```

### Code Review
1. **Checklist**
   - Código limpo e legível
   - Testes implementados
   - Documentação atualizada
   - Sem breaking changes
   - Performance otimizada

2. **Pull Request Template**
   ```markdown
   ## Descrição
   [Descreva as alterações]

   ## Tipo de Mudança
   - [ ] Nova feature
   - [ ] Bugfix
   - [ ] Breaking change
   - [ ] Documentação

   ## Testes
   - [ ] Testes unitários
   - [ ] Testes de integração
   - [ ] Testes e2e

   ## Screenshots
   [Se aplicável]
   ```

## Testes

### Backend
```java
@SpringBootTest
class JogoServiceTest {
    @Mock
    private JogoRepository jogoRepository;
    
    @InjectMocks
    private JogoService jogoService;
    
    @Test
    void deveRetornarJogosDisponiveis() {
        // arrange
        // act
        // assert
    }
}
```

### Frontend
```typescript
describe('JogoCardComponent', () => {
  let component: JogoCardComponent;
  let fixture: ComponentFixture<JogoCardComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      // ...
    }).compileComponents();
  });

  it('deve exibir informações do jogo', () => {
    // arrange
    // act
    // assert
  });
});
```

## Deploy

### Ambiente de Desenvolvimento
```bash
# Backend
./mvnw spring-boot:run -Dspring.profiles.active=dev

# Frontend
ng serve
```

### Ambiente de Produção
```bash
# Backend
./mvnw clean package -Pprod
java -jar target/app.jar

# Frontend
ng build --configuration=production
```

## Troubleshooting

### Problemas Comuns

1. **Firebase Connection**
   ```
   Erro: Failed to initialize Firebase
   Solução: Verificar credenciais e permissões
   ```

2. **JWT Token**
   ```
   Erro: Invalid token
   Solução: Verificar expiração e assinatura
   ```

### Logs
- Usar Log4j2 no backend
- NGX Logger no frontend
- Stacktrace completo em dev
- Logs sanitizados em prod

## Recursos Adicionais

### Documentação
- [Spring Boot Docs](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [Angular Docs](https://angular.io/docs)
- [Firebase Docs](https://firebase.google.com/docs)

### Ferramentas Recomendadas
- Postman para testes de API
- Firebase Console
- Chrome DevTools
- Spring Boot DevTools 
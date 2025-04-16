# 🎲 Mestre dos Jogos

**Mestre dos Jogos** é uma plataforma moderna de aluguel de jogos de tabuleiro, desenvolvida com Angular 18 no frontend e Java Spring Boot no backend, utilizando Firebase como banco de dados e autenticação.

[![CI/CD](https://github.com/mestre-dos-jogos/platform/actions/workflows/main.yml/badge.svg)](https://github.com/mestre-dos-jogos/platform/actions/workflows/main.yml)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/mestre-dos-jogos/platform/releases)

## 🌟 Funcionalidades Principais

### Para Clientes
- Catálogo completo de jogos com filtros avançados
- Sistema de aluguel com diferentes opções de diárias
- Avaliações e reviews dos jogos
- Histórico de aluguéis e favoritos
- Notificações de datas importantes

### Para Gestores
- Dashboard completo de gestão
- Controle de estoque e manutenção
- Relatórios financeiros e métricas
- Gestão de promoções e descontos
- Análise de popularidade dos jogos

## 🛠️ Stack Tecnológica

| Camada         | Tecnologia                               |
|----------------|-------------------------------------------|
| Frontend       | Angular 18 (standalone)                   |
| UI/UX          | Angular Material + Tailwind CSS           |
| Backend        | Java 21 + Spring Boot 3.2                |
| Banco de Dados | Firebase Realtime Database               |
| Storage        | Firebase Cloud Storage                   |
| Autenticação   | Firebase Authentication                  |
| Documentação   | SpringDoc OpenAPI (Swagger)              |

## 📚 Documentação

### Guias Principais
1. [Arquitetura do Sistema](docs/ARQUITETURA.md)
   - Visão geral da arquitetura
   - Diagramas e fluxos
   - Decisões técnicas

2. [Regras de Negócio](docs/REGRAS_NEGOCIO.md)
   - Horários de funcionamento
   - Sistema de diárias
   - Políticas e procedimentos

3. [API REST](docs/API.md)
   - Endpoints disponíveis
   - Autenticação
   - Exemplos de uso

4. [Guia de Desenvolvimento](docs/DESENVOLVIMENTO.md)
   - Setup do ambiente
   - Padrões de código
   - Fluxo de trabalho

5. [Deploy e DevOps](docs/DEPLOYMENT.md)
   - Ambientes
   - CI/CD Pipeline
   - Monitoramento

## 🚀 Começando

### Pré-requisitos
- Java Development Kit 21
- Node.js 20+
- Angular CLI 18
- Docker
- Git

### Instalação Rápida

```bash
# Clone o repositório
git clone https://github.com/mestre-dos-jogos/platform.git
cd platform

# Backend
cd backend
./mvnw clean install
./mvnw spring-boot:run -Dspring.profiles.active=dev

# Frontend
cd ../frontend
npm install
ng serve
```

Acesse `http://localhost:4200` para ver a aplicação rodando.

## 🤝 Contribuindo

1. Fork o projeto
2. Crie sua branch de feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add: nova funcionalidade'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

Consulte nosso [Guia de Contribuição](CONTRIBUTING.md) para mais detalhes.

## 📅 Roadmap

### Versão 1.1.0 (Próximo Release)
- [ ] Sistema de reservas inteligente
- [ ] Integração com apps de transporte
- [ ] Sistema de fidelidade
- [ ] Dashboard em tempo real
- [ ] App mobile

### Versão 1.2.0 (Planejado)
- [ ] Recomendações personalizadas
- [ ] Chat em tempo real
- [ ] Eventos e torneios
- [ ] Sistema de achievements
- [ ] Integração com redes sociais

## 📫 Contato

- Site: [mestredosjogos.com.br](https://mestredosjogos.com.br)
- Email: contato@mestredosjogos.com.br
- WhatsApp: (34) 99167-2554
- Endereço: Rua João Balbino, 537

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🙏 Agradecimentos

- A todos os clientes que confiam em nosso serviço
- À comunidade de boardgames
- Aos desenvolvedores que contribuem com o projeto

---

Feito com ❤️ pela equipe Mestre dos Jogos

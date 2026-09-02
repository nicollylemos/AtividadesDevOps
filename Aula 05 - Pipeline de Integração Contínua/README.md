# Gerador de Frases

Projeto desenvolvido para a disciplina de DevOps da Fatec, com o objetivo de demonstrar o funcionamento de uma pipeline de CI/CD usando GitHub Actions.

A aplicação apresenta frases aleatórias ao usuário, organizadas por categoria, e permite copiar a frase gerada para a área de transferência.

## Sobre o projeto

- Geração de frase aleatória por categoria (Motivação, Foco, Criatividade ou Todas)
- Botão para copiar a frase atual para a área de transferência
- Interface simples, feita em HTML, CSS e JavaScript puro
- Cobertura de testes unitários com Jest
- Padronização de código com ESLint
- Pipeline de integração e entrega contínua automatizada via GitHub Actions

## Tecnologias

- HTML5
- CSS3
- JavaScript
- Node.js
- Jest
- ESLint
- GitHub Actions

## Estrutura do projeto

```text
.
├── .github/workflows/pipeline.yml   # Definição da pipeline de CI/CD
├── index.html                       # Estrutura da página
├── style.css                        # Estilos da aplicação
├── script.js                        # Lógica do gerador de frases
├── tests/script.test.js             # Testes unitários
├── eslint.config.js                 # Regras de lint
└── package.json
```

## Como rodar o projeto

```bash
git clone https://github.com/deivisontakatu/projeto-pipelines-devops.git
cd projeto-pipelines-devops
npm install
```

Depois basta abrir o `index.html` no navegador.

### Testes

```bash
npm test
```

### Lint

```bash
npm run lint
```

## Pipeline de CI/CD

A pipeline roda automaticamente a cada `push` ou `pull request` na branch `main`, definida em `.github/workflows/pipeline.yml`. Cada etapa depende da anterior (`needs`), então qualquer falha interrompe o fluxo e as etapas seguintes não são executadas.

| # | Etapa | O que faz |
|---|-------|-----------|
| 1 | **Build** | Baixa o código, configura o Node.js e verifica se os arquivos principais (`index.html`, `style.css`, `script.js`) existem |
| 2 | **Test** | Instala as dependências e executa os testes unitários com Jest |
| 3 | **Quality** | Executa o ESLint para validar padrões de código |
| 4 | **Security** | Roda `npm audit` para identificar vulnerabilidades nas dependências |
| 5 | **Package** | Empacota os arquivos da aplicação em uma pasta `dist/` e confirma que o pacote foi gerado corretamente |
| 6 | **Deploy** | Simula a publicação da aplicação em ambiente de desenvolvimento |
| 7 | **Smoke Test** | Faz uma verificação rápida de que a aplicação está no ar |
| 8 | **Performance** | Simula um teste de performance |
| 9 | **Approval** | Simula a aprovação para produção |
| 10 | **Release** | Simula a criação de uma nova versão da aplicação |
| 11 | **Monitoring** | Simula o monitoramento da aplicação em produção |
| 12 | **Rollback** | Executa apenas se alguma etapa anterior falhar (`if: failure()`), simulando a reversão da versão |

### Fluxo

```text
Build → Test → Quality → Security → Package → Deploy
  → Smoke Test → Performance → Approval → Release → Monitoring
                                                        ↓ (em caso de falha)
                                                     Rollback
```

## GitHub Actions utilizadas

A pipeline combina Actions prontas do GitHub Marketplace com comandos próprios do projeto (scripts do `package.json`), de acordo com o que cada etapa exige.

| Action | Onde é usada | Função |
|--------|---------------|--------|
| [`actions/checkout@v4`](https://github.com/actions/checkout) | Build, Test, Quality, Security, Package | Baixa o código do repositório para o runner, necessário como primeiro passo de qualquer job que precise acessar os arquivos do projeto |
| [`actions/setup-node@v4`](https://github.com/actions/setup-node) | Build, Test, Quality, Security | Instala e configura a versão do Node.js (22) usada para rodar `npm install`, os testes, o lint e a auditoria de dependências |

As demais verificações (testes, lint e auditoria de segurança) são executadas por comandos `npm` diretamente (`npm test`, `npm run lint`, `npm audit`), e as etapas de deploy, release e monitoramento são simuladas com scripts de shell, já que o projeto não possui um ambiente de hospedagem real.

## Autor

**Prof. Me. Deivison S. Takatu**
deivison.takatu@fatec.sp.gov.br

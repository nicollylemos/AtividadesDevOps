# Sistema Comercial Cálculo Automático de Descontos

Projeto desenvolvido para a disciplina de DevOps (FATEC Sorocaba), na aula de Testes Automatizados. A aplicação calcula descontos de forma padronizada e conta com três tipos de testes automatizados, executados de forma independente e integrados a uma pipeline de Integração Contínua no GitHub Actions.

## Contexto

Os vendedores de uma loja de roupas calculavam descontos manualmente, o que gerava erros nos valores cobrados e inconsistência entre atendimentos, já que cada vendedor aplicava o desconto de um jeito. Para resolver isso, foi criado um sistema web que aplica as regras da empresa automaticamente.

### Regras de desconto

 Valor da compra         Desconto 
----------------------------------
 Abaixo de R$ 100        10%      
 Igual ou acima de R$ 100  5%     

## Tecnologias

- React + Vite
- Vitest (runner de testes)
- Testing Library (testes de integração da interface)
- ESLint (qualidade e padronização do código)
- GitHub Actions (pipeline de CI)

## Estrutura do projeto

```
src
├── components
│   └── DiscountDashboard.jsx   # Interface do usuário
├── services
│   └── discountService.js      # Regras de desconto
├── tests
│   ├── unit                   # Testes unitários
│   ├── integration            # Testes de integração
│   └── performance            # Testes de performance
├── App.jsx                     # Estrutura principal da aplicação
└── main.jsx                    # Ponto de entrada
.github
└── workflows
    └── ci.yml                  # Pipeline de Integração Contínua
```

## Tipos de testes

Unitários (`srctestsunit`) validam a função de cálculo de desconto de forma isolada, garantindo que cada faixa de valor receba o percentual correto, inclusive no limite de R$ 100. Se alguém alterar a regra para 15%, por exemplo, o teste falha porque o sistema espera 10% ou 5%.

Integração (`srctestsintegration`) verificam se a interface e o serviço funcionam juntos o usuário digita um valor, clica em Calcular Desconto e o resultado correto aparece na tela. Se o texto do botão mudar para Calcular, o teste não encontra o elemento e falha.

Performance (`srctestsperformance`) avaliam se o cálculo responde dentro de um tempo máximo definido, mesmo sob várias execuções seguidas. Se o limite for configurado para algo irreal, como 1ms, o teste acusa que a aplicação não respondeu a tempo.

Além dos testes, o ESLint faz a análise estática do código e barra problemas como variáveis declaradas e nunca usadas (`no-unused-vars`).

## Como rodar

Instalar as dependências

```bash
npm install
```

Subir a aplicação em modo de desenvolvimento

```bash
npm run dev
```

Executar cada tipo de teste separadamente

```bash
npm run testunit
npm run testintegration
npm run testperformance
```

Rodar todos os testes e o lint

```bash
npm test
npm run lint
```

## Pipeline de CI

A pipeline fica em `.githubworkflowsci.yml` e é disparada automaticamente a cada push na branch `main`. As etapas são

1. Checkout do código
2. Configuração do Node.js
3. Instalação das dependências (`npm ci`)
4. Verificação de qualidade com ESLint
5. Testes unitários
6. Testes de integração
7. Testes de performance

Cada tipo de teste roda em uma etapa própria, então o resultado de cada um aparece separado na aba Actions do GitHub. Se qualquer etapa falhar, a pipeline para e as seguintes não são executadas, evitando que uma versão com problema avance.

## Referências

- HUMBLE, J.; PRIKLANDNICKI, R. Entrega Contínua Como Entregar Software de Forma Rápida e Confiável. São Paulo Bookman, 2013.
- MORAES, G. Caixa de Ferramentas DevOps. São Paulo Casa do Código, 2015.
- PIRES, A.; MILITÃO, J. Integração Contínua com Jenkins. São Paulo Casa do Código, 2019.
- SATO, D. DevOps na prática entrega de software confiável e automatizada. São Paulo Casa do Código, 2014.
- Projeto de referência [deivisontakatuprojeto-pipeline-testes](httpsgithub.comdeivisontakatuprojeto-pipeline-testes)
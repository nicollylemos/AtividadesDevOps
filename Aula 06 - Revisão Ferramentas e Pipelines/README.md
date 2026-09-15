# Revisão: Ferramentas e Pipelines

**Prof. Me. Deivison S. Takatu** — deivison.takatu@fatec.sp.gov.br

---

## Sumário

- DevOps: o ciclo infinito do desenvolvimento moderno
- Estrutura de pipeline
- Exemplos de pipeline
- GitHub Actions
- Entregas de software e automação
- Atividade

---

## DevOps: o Ciclo Infinito do Desenvolvimento Moderno

DevOps é uma cultura, filosofia e conjunto de práticas que integra as equipes de Desenvolvimento (Dev) e Operações (Ops), eliminando silos organizacionais e acelerando a entrega de software com qualidade e confiabilidade. É representado como um ciclo infinito (símbolo de infinito) com 8 etapas.

### PLAN — Planejamento
Ponto de partida do loop. Define o que será desenvolvido, como e quando, usando metodologias ágeis para organizar prioridades, distribuir tarefas e alinhar expectativas entre produto, desenvolvimento e operações.

- **Jira** — gestão de projetos ágeis com sprints, roadmaps e rastreabilidade
- **Trello** — quadros Kanban visuais para equipes menores
- **Azure Boards** — planejamento integrado ao ecossistema Microsoft Azure DevOps

### CODE — Codificação
Etapa em que as ideias planejadas ganham forma técnica. Desenvolvedores escrevem, revisam e versionam o código-fonte de forma colaborativa, garantindo rastreabilidade, segurança e qualidade desde o início.

Boas práticas:
- Escrever código limpo e legível
- Utilizar IDEs
- Manter testes
- Documentar o projeto

### BUILD — Compilação e Build Automatizado
Transforma o código-fonte em um artefato executável (JAR, imagem Docker, pacote NPM, binário) pronto para ser testado e implantado. A automação elimina erros humanos e garante builds consistentes e reproduzíveis.

Etapas:
- Compilação: código-fonte → bytecode/binário
- Resolução de dependências: download automático de bibliotecas
- Empacotamento: geração de JAR, WAR, ZIP, imagem Docker
- Análise estática: verificação de qualidade (ex: SonarQube)
- Publicação de artefato: versionamento e armazenamento seguro

### TEST — Testes Automatizados e Qualidade de Software
Testes automatizados detectam problemas rapidamente, antes que cheguem ao usuário final, integrados diretamente no pipeline de CI/CD.

**Exemplo:** uma plataforma de delivery executa +3.000 testes automatizados a cada deploy, validando frete, pagamentos, notificações e fluxo completo de pedido — tudo em menos de 8 minutos, sem intervenção humana.

### RELEASE — Liberação e Controle de Versões
Ponto de decisão do pipeline: o software já foi desenvolvido, compilado e testado, e agora precisa ser aprovado, versionado e preparado para produção.

O artefato recebe uma versão semântica (ex: v2.4.1, padrão Major.Minor.Patch). *Quality Gates* verificam cobertura de testes, análise de segurança e aprovação manual de stakeholders antes de avançar.

### DEPLOY — Implantação Automatizada
Momento em que o software aprovado é implantado em produção de forma automatizada, rápida e confiável, com risco reduzido e reversão automática em caso de falha.

**Exemplo:** uma empresa de streaming com 47 microsserviços usa Kubernetes no AWS EKS — cada serviço é implantado via pipeline GitLab, a imagem Docker é construída e publicada no ECR, e o Kubernetes atualiza os pods em rolling update, sem downtime e com rollback automático se o health check falhar.

### OPERATE — Operação e Gestão de Infraestrutura
Garante que a aplicação em produção permaneça estável, disponível e escalável. As equipes de Ops gerenciam infraestrutura como código, respondendo proativamente às mudanças de demanda.

**Exemplo:** uma plataforma de streaming (modelo Netflix) usa Kubernetes para aumentar automaticamente réplicas dos serviços em horários de pico, balanceamento de carga entre instâncias saudáveis e Ansible para manter configurações uniformes em todos os nós.

### MONITOR — Observabilidade e Monitoramento Contínuo
Fecha o loop infinito. É onde a equipe obtém visibilidade total do sistema em produção, coletando dados para detectar anomalias, entender comportamentos e alimentar o próximo ciclo de planejamento.

Três pilares:
- **Métricas** — dados numéricos (CPU, memória, latência, taxa de erro, requisições/segundo)
- **Logs** — registros textuais de eventos (erros, transações, autenticações, ações de usuários)
- **Traces** — rastreamento do caminho de uma requisição por todos os serviços envolvidos

---

## Estrutura de Pipeline

**Pipeline:** sequência de validações automatizadas executadas durante o ciclo de entrega do software.

Princípios fundamentais:
- **Build uma única vez** — o mesmo artefato é promovido entre ambientes
- **Mesmo deploy em todos os ambientes** — Desenvolvimento → Homologação → Produção
- **Falhou? Para tudo** — nenhuma etapa continua após um erro

**Exemplo prático:** um desenvolvedor altera a tela de login e envia o código para o GitHub. O pipeline inicia automaticamente:
1. Baixa o código atualizado
2. Compila a aplicação
3. Executa testes automáticos
4. Verifica a qualidade do código
5. Gera uma nova versão da aplicação
6. Publica em ambiente de homologação

### Tipos de pipeline (por etapa)

| Pipeline | Função principal |
|---|---|
| **Build** | Compilação automatizada, geração de artefatos (.jar, .war, .apk, containers Docker), verificação inicial da integridade do código |
| **Testes** | Execução automática de testes, validação contínua, identificação rápida de falhas |
| **Qualidade** | Verificações automatizadas para avaliar se o código atende aos padrões definidos, identificando problemas e inconsistências antecipadamente |
| **Segurança** | Análise de vulnerabilidades no código, verificação de dependências, identificação de configurações inseguras, detecção de informações sensíveis expostas |
| **Artefatos (Package)** | Empacotamento da aplicação, geração de arquivos de distribuição, versionamento e armazenamento em repositórios de artefatos |
| **Deploy** | Preparação do ambiente de destino, publicação do artefato, configuração de variáveis/parâmetros, execução do deploy automatizado |
| **Release e Monitoramento** | Criação e identificação de versões, publicação de releases, controle de versões disponibilizadas, monitoramento da aplicação em produção |

---

## Exemplo de Projeto

Projeto prático utilizando GitHub Actions para automatizar uma pipeline de CI/CD. Cada etapa é executada automaticamente e uma falha interrompe o fluxo.

Link: `github.com/deivisontakatu/projeto-pipelines-devops`

---

## GitHub Actions

Plataforma de automação integrada ao GitHub, que permite criar e executar fluxos de trabalho (workflows) diretamente associados aos repositórios de código.

Os workflows podem ser configurados de acordo com eventos do repositório, como *push*, *pull request*, criação de tags ou releases.

### GitHub Actions Marketplace
Catálogo de Actions, ferramentas e extensões utilizáveis nos workflows. Permite encontrar soluções prontas para build, testes, qualidade, segurança, deploy, cache e outras etapas da pipeline. As Actions podem ser desenvolvidas pelo GitHub, por parceiros ou pela comunidade.

Link: `github.com/marketplace?type=actions`

---

## Entregas de Software e Automação

**DevOps:** integra desenvolvimento, testes e operações por meio da automação, acelerando entregas de software com maior qualidade, estabilidade e redução de falhas.

**Definição de Pipeline** (Humble e Priklandnicki, 2013): sequência automatizada de estágios responsável por conduzir o software desde o commit até o deploy de forma confiável.

**O Papel das Pipelines:** as pipelines de CI tornaram-se fundamentais no desenvolvimento moderno, automatizando validações e garantindo qualidade contínua durante todo o ciclo de entrega.

> "Pipelines promovem qualidade contínua ao longo de todo o processo de entrega" — SATO (2014)

### Gatilhos (Workflows)
Iniciam automaticamente em ações como:
- Push de código
- Pull Requests
- Criação de Releases
- Publicação de Tags

Exemplo de sintaxe (GitHub Actions):

```yaml
# É uma ferramenta nativa do GitHub
# que permite automatizar processos de
# integração contínua, testes e deploy
# de aplicações.

on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
```

---

## Atividade

1. Integrar uma pipeline ao projeto utilizando o GitHub Actions, configurando a automação para ser executada sempre que houver um novo push na branch principal (`main`).
2. Buscar repositórios no GitHub que contenham integração de pipeline e analisar pelo menos três projetos, destacando características, funcionalidades, gatilhos e histórico.

---

## Referências

- HUMBLE, J.; PRIKLANDNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável.* São Paulo: Bookman, 2013.
- MUNIZ, A.; et al. *Jornada DevOps: Unindo Cultura Ágil, Lean e Tecnologia Para Entrega De Software Com Qualidade.* São Paulo: Brasport, 2019.
- SATO, D. *DevOps na prática: entrega de software confiável e automatizada.* São Paulo: Casa do Código, 2014.
- SILVA, R. *Entrega contínua em Android: Como automatizar a distribuição de apps.* São Paulo: Casa do Código, 2016.
- ARUNDEL, J.; DOMINGUS, J. *DevOps nativo de nuvem com Kubernetes.* São Paulo: Novatec, 2019.
- MORAES, G. *Caixa de Ferramentas DevOps: Um guia para construção, administração e arquitetura de sistemas modernos.* São Paulo: Casa do Código, 2015.
- PIRES, A.; MILITÃO, J. *Integração Contínua com Jenkins.* São Paulo: Casa do Código, 2019.
- VITALINO, J. F. N.; CASTRO, M. A. N. *Descomplicando o Docker.* 2 ed. São Paulo: Brasport, 2018.
- SILVERMAN, R. E. *Git: guia prático.* São Paulo: Novatec, 2019.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps: Como obter agilidade, confiabilidade e segurança em organizações tecnológicas.* São Paulo: Starlin Alta Editora, 2018.

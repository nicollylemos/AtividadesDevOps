# Atividade 09 — Documentação de Software

Atividade individual da Aula 09 da disciplina de Integração e Entrega Contínua (DevOps), FATEC Sorocaba, com o Prof. Me. Deivison S. Takatu.

**Aluna:** Nicolly Lemos da Silva ([@nicollylemos](https://github.com/nicollylemos))
**Projeto documentado:** Sistema de Agendamento Online
**Repositório:** https://github.com/nicollylemos/Agendamento

## Resumo da aula

A aula partiu de uma pergunta simples: se alguém entrar hoje no GitHub do seu projeto, consegue entender e executar tudo sem perguntar nada? A documentação existe para isso. Sem ela, o projeto depende de pessoas específicas, quem chega novo demora para se situar, configurações são esquecidas e o conhecimento se perde quando alguém sai da equipe.

Documentação de software é o conjunto de informações que ajuda a entender, usar, desenvolver, testar e manter um sistema. Ela apoia a comunicação, a manutenção, a colaboração e a continuidade do projeto. No contexto DevOps, também registra como o código é desenvolvido, como as mudanças são validadas, como a pipeline funciona e como o sistema é implantado.

Foram apresentados três tipos de documentação:

- **Técnica:** arquitetura, APIs, banco de dados, componentes e configurações.
- **De projeto:** objetivos, requisitos, decisões e organização.
- **De processo:** branches, commits, pull requests, testes, pipeline e deploy.

O README é normalmente o primeiro arquivo que alguém lê num repositório. Ele deve mostrar rapidamente o propósito do projeto, as tecnologias, os pré-requisitos, como instalar, configurar, executar e testar, e a estrutura das pastas. Também ficou claro o que **não** deve entrar na documentação: senhas, chaves de API, tokens, arquivos `.env`, dados pessoais e detalhes de infraestrutura que facilitem acessos indevidos.

## A atividade

Escolher um projeto de software e documentá-lo com objetivo, problema, escopo, requisitos funcionais e não funcionais, tecnologias, arquitetura e organização dos componentes. Além disso, criar ou atualizar o README.md do repositório com pré-requisitos, instalação, configuração e execução e, quando aplicável, documentar APIs, banco de dados, variáveis de ambiente, testes e deploy.

## Entrega

Escolhi o **Sistema de Agendamento Online**, um projeto meu para pequenos negócios de serviços, como salões e barbearias. Nele, o cliente agenda pelo site e garante o horário pagando um sinal via Pix, e a equipe gerencia agenda, estoque, fidelidade e relatórios num painel único.

| Item pedido | Onde está |
| --- | --- |
| Objetivo, problema e escopo | [Documentação em PDF](https://github.com/nicollylemos/Agendamento/blob/main/docs/DOCUMENTACAO_SISTEMA_AGENDAMENTO.pdf), seções 1 a 3 |
| Requisitos funcionais e não funcionais | Documentação, seções 4 e 5 |
| Tecnologias, arquitetura e componentes | Documentação, seções 6 e 7 |
| Banco de dados | Documentação, seção 8 |
| APIs | Documentação, seção 9, e [docs/API.md](https://github.com/nicollylemos/Agendamento/blob/main/docs/API.md) |
| Pré-requisitos, instalação, configuração e execução | [README do repositório](https://github.com/nicollylemos/Agendamento#readme) |
| Variáveis de ambiente | README e documentação, seção 10 |
| Testes e deploy | README e documentação, seção 11 |

Seguindo o que foi visto em aula, o repositório traz só o `.env.example` com valores de modelo. Os arquivos `.env` reais estão no `.gitignore`, e o GitHub Actions roda o gitleaks a cada envio para garantir que nenhum segredo seja publicado.

## Referências

- HUMBLE, J.; PRIKLADNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. São Paulo: Bookman, 2013.
- MUNIZ, A. et al. *Jornada DevOps: Unindo Cultura Ágil, Lean e Tecnologia Para Entrega de Software com Qualidade*. São Paulo: Brasport, 2019.
- SATO, D. *DevOps na prática: entrega de software confiável e automatizada*. São Paulo: Casa do Código, 2014.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps*. São Paulo: Alta Books, 2018.

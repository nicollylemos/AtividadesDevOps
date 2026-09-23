<div align="center">

#  Integração e Entrega Contínua (DevOps)

Atividades, resumos e projetos desenvolvidos ao longo do semestre na Fatec Sorocaba.

![Fatec](https://img.shields.io/badge/Fatec-Sorocaba-B20000?style=for-the-badge)
![DevOps](https://img.shields.io/badge/DevOps-CI%2FCD-0A66C2?style=for-the-badge)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

</div>

---

## 📋 Sobre a disciplina

| | |
|---|---|
| **Disciplina** | Integração e Entrega Contínua (DevOps) |
| **Curso** | Tecnologia em Análise e Desenvolvimento de Sistemas |
| **Instituição** | Fatec Sorocaba |
| **Professor** | Prof. Me. Deivison S. Takatu |
| **Ano** | 2026 |

A disciplina aborda a cultura e as práticas DevOps, com foco em automatizar o ciclo de vida do software, do commit até a entrega. Ao longo do semestre são trabalhados integração contínua (CI), entrega contínua (CD), gerência de configuração, versionamento com Git, construção de pipelines, testes automatizados e controle de qualidade de código, sempre com atividades práticas aplicadas em projetos reais.

A ideia central é que qualidade não é uma etapa isolada no fim do projeto, mas algo que acompanha todo o processo: cada alteração passa por validações automáticas e, se algo falha, a pipeline para antes que uma versão com problema chegue a outro ambiente.

### 👥 Grupo

| Integrante | GitHub |
|---|---|
| Karina de Moraes Garcia | — |
| Mike Willy Franguelli | — |
| Nicolly Lemos da Silva | [@nicollylemos](https://github.com/nicollylemos) |
| Pedro Henrique Cardozo Dias | — |
| Rafaela Mansano Fernandes | [@rafamans4no](https://github.com/rafamans4no) |

---

## 📚 Aulas e atividades

| Aula | Tema | Resumo | Projeto | Deploy |
|:---:|---|:---:|---|---|
| 01 | Apresentação da Disciplina e Introdução ao DevOps | [📂 Abrir](./Aula%2001%20-%20Apresenta%C3%A7%C3%A3o%20da%20Disciplina%20e%20Introdu%C3%A7%C3%A3o%20ao%20DevOps) | — | — |
| 02 | Conceitos de Integração e Entrega Contínua de Software | [📂 Abrir](./Aula%2002%20-%20Conceitos%20de%20Integra%C3%A7%C3%A3o%20e%20Entrega%20Cont%C3%ADnua%20de%20Software) | [LivrariaDevOps](https://github.com/nicollylemos/LivrariaDevOps) | [🌐 Acessar](https://livraria-dev-ops.vercel.app/) |
| 03 | Gerência de Configuração | [📂 Abrir](./Aula%2003%20-%20Ger%C3%AAncia%20de%20Configura%C3%A7%C3%A3o) | [ProjetoGitTemplate](https://github.com/nicollylemos/ProjetoGitTemplate) | [🌐 Acessar](https://projeto-git-template.vercel.app/) |
| 04 | Ferramentas de Integração e Entrega Contínua | [📂 Abrir](./Aula%2004%20-%20Ferramentas%20de%20Integra%C3%A7%C3%A3o%20e%20Entrega%20Cont%C3%ADnua) | — | — |
| 05 | Pipeline de Integração Contínua | [📂 Abrir](./Aula%2005%20-%20Pipeline%20de%20Integra%C3%A7%C3%A3o%20Cont%C3%ADnua) | [Atividade_Aula05](https://github.com/rafamans4no/Atividade_Aula05) | — |
| 06 | Revisão: Ferramentas e Pipelines | [📂 Abrir](./Aula%2006%20-%20Revis%C3%A3o%20Ferramentas%20e%20Pipelines) | — | — |
| 07 | Testes Automatizados | [📂 Abrir](./Aula%2007%20-%20Testes%20Automatizados) | [Atividade07DevOps](https://github.com/nicollylemos/Atividade07DevOps) | — |

---

## 🧠 Conteúdos trabalhados

| Tema | O que foi visto |
|---|---|
| **Cultura DevOps** | Integração entre Dev e Ops e o ciclo infinito Plan → Code → Build → Test → Release → Deploy → Operate → Monitor |
| **Integração Contínua (CI)** | Integração frequente do código, com build e validações automáticas a cada push |
| **Entrega Contínua (CD)** | Build único promovido entre ambientes: Desenvolvimento → Homologação → Produção |
| **Gerência de Configuração** | Versionamento com Git, tags, dependências (`package.json`), templates e o clássico "na minha máquina funciona" |
| **Ferramentas de CI/CD** | Comparação entre GitHub Actions, Azure DevOps, Jenkins e outras plataformas |
| **Pipelines** | Workflows `.yml` no GitHub Actions, com etapas encadeadas e a regra "falhou, para tudo" |
| **Testes Automatizados** | Testes unitários, de integração e de performance executados na pipeline |
| **Qualidade de Código** | Análise estática com ESLint e auditoria de dependências com `npm audit` |

---

## 🛠️ Ferramentas utilizadas

| Categoria | Ferramentas |
|---|---|
| Versionamento | Git, GitHub |
| CI/CD | GitHub Actions |
| Deploy | Vercel |
| Testes | Jest, Vitest, Testing Library |
| Qualidade | ESLint, npm audit |
| Front-end | HTML, CSS, JavaScript, React, Vite |

---

## 🗂️ Estrutura do repositório

```text
AtividadesDevOps/
├── Aula 01 - Apresentação da Disciplina e Introdução ao DevOps/
├── Aula 02 - Conceitos de Integração e Entrega Contínua de Software/
├── Aula 03 - Gerência de Configuração/
├── Aula 04 - Ferramentas de Integração e Entrega Contínua/
├── Aula 05 - Pipeline de Integração Contínua/
├── Aula 06 - Revisão Ferramentas e Pipelines/
├── Aula 07 - Testes Automatizados/
└── README.md
```

Cada pasta tem um `README.md` com o resumo da aula, a atividade proposta e o que foi entregue, além dos slides e documentos em PDF.

---

## 📖 Referências bibliográficas

- HUMBLE, J.; PRIKLANDNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. São Paulo: Bookman, 2013.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps: Como obter agilidade, confiabilidade e segurança em organizações tecnológicas*. São Paulo: Alta Books, 2018.
- MORAES, G. *Caixa de Ferramentas DevOps*. São Paulo: Casa do Código, 2015.
- MUNIZ, A. et al. *Jornada DevOps*. São Paulo: Brasport, 2019.
- PIRES, A.; MILITÃO, J. *Integração Contínua com Jenkins*. São Paulo: Casa do Código, 2019.
- SATO, D. *DevOps na prática: entrega de software confiável e automatizada*. São Paulo: Casa do Código, 2014.

---

<div align="center">

Fatec Sorocaba · 2026

</div>

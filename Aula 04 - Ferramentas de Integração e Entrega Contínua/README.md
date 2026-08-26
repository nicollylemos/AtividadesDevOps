# Comparação entre as Plataformas de CI/CD: Azure DevOps e GitHub

## Introdução

Essa pequisa tem como viés analisar e aprofundar os pontos levantandos no estudo "Comparação prática entre as plataformas de CI/CD Azure DevOps e GitHub" por por Vladislav Manolov, Daniela Gotseva e Nikolay Hinov no ano de 2025 do Departamento de Sistemas de Computação, Faculdade de Sistemas e Tecnologias de Computação, Universidade Técnica de Sófia. Com esse artigo foi possível identificar as ferramentas frequentemente utilizadas no CI/CD, uma análise comparativa entre essas ferramentas, características, qualidades, limitações e cenários onde aplicáveis. Baseado nisso, foi criado um arquivo centralizando as informações, como forma de atividade avaliativa da matéria de Integração Contínua (CI) e Entrega/Implantação.

---

## Ferramentas

O texto explica que ao passar dos anos, com os avanços tecnológicos, diversas metodologias foram criadas para impulsionar o desenvolvimento de aplicações, principalmente as mais complexas. As principais ferramentas mencionadas no artigo focou principalmente em Azure DevOps e no Github, além de Jenkins, GitLab CI/CD, Atlassian Bitbucket, AWS CodePipeline e JetBrains TeamCity, tendo consciencia de que cada serviço possui sua própria necessidade e funcionalidade.

O artigo também cita que o GitHub é a preferência majoriária, liderando o ranking com 33%, e em seguida o Azure DevOps com 24%. Em terceiro em o Jenkins com O Jenkins detém 14% de participação.

---

## Características

Os autores informam que o Azure DevOps fornece suporte para o Git e ao team Foundation Version Control (TFVC), mas o GitHub é mais focado no Git.

Eles também citam sobre automação que "O Azure DevOps oferece o Azure Pipelines, um serviço robusto de CI/CD que suporta pipelines de várias etapas", e "O GitHub implementa CI/CD por meio do GitHub Actions, uma ferramenta de automação de fluxo de trabalho altamente flexível e modular".

---

## Vantagens

Sobre desempenho, o artigo aponta que "Dados empíricos indicam que o Azure Pipelines supera o GitHub Actions em projetos empresariais de grande escala", enquanto o GitHub "tem se mostrado mais rápido e leve para equipes de desenvolvimento de pequeno a médio porte".

Na parte de segurança, um recurso exclusivo do GitHub é a verificação de assinatura de commits, prevenindo commits falsificados e alterações não autorizadas. Já o Azure DevOps se destaca porque integra-se ao Microsoft Defender for DevOps, fornecendo detecção de ameaças em tempo real e detecção de anomalias em pipelines.

Em relação a custo, o GitHub costuma ser a opção mais econômica para pequenas equipes e desenvolvedores independentes, já que oferece repositórios públicos gratuitos e minutos de CI/CD integrados sem custo adicional. O Azure DevOps, por sua vez, compensa esse ponto oferecendo um modelo de pagamento por usuário e por serviço, permitindo que empresas paguem só pelos recursos que realmente utilizam.

---

## Limitações

O GitHub Actions permite usar ações prontas da comunidade, mas isso abre brecha: qualquer um pode publicar uma action.

Em projetos muito grandes, com histórico extenso, o GitHub fica mais lento que o Azure Pipelines, que foi pensado pra esse tipo de carga corporativa pesada. O GitHub Actions nasceu com foco em fluxos ágeis e leves. Mover repositório, recriar pipelines do zero, e garantir que os artefatos não se percam, caso seja feito da forma errada pode trazer instabilidades.

---

## Cenários de uso

Empresas de setores mais regulados, como banco, saúde e defesa, costumam ir de Azure DevOps por causa das certificações de conformidade que ele já traz prontas. Já startups e times menores preferem o GitHub, principalmente porque a hospedagem de repositório sai de graça. No mundo dos jogos rola a mesma lógica: estúdios AAA apostam no Azure DevOps pela integração forte com as ferramentas da Microsoft, enquanto devs indie e projetos de engine open source se sentem mais em casa no GitHub.

---

## Referência

**Comparação prática entre as plataformas de CI/CD Azure DevOps e GitHub**
por Vladislav Manolov, Daniela Gotseva e Nikolay Hinov*

*Departamento de Sistemas de Computação, Faculdade de Sistemas e Tecnologias de Computação, Universidade Técnica de Sófia, 1000 Sófia, Bulgária*
\* Autor a quem a correspondência deve ser dirigida.

Internet do Futuro 2025, 17(4), 153; https://doi.org/10.3390/fi17040153

Submissão recebida em: 7 de março de 2025 / Revisado em: 24 de março de 2025 / Aceito em: 28 de março de 2025 / Publicado em: 31 de março de 2025

> MANOLOV, Vladislav; GOTSEVA, Daniela; HINOV, Nikolay. Practical Comparison Between the CI/CD Platforms Azure DevOps and GitHub. *Future Internet*, v. 17, n. 4, 2025, p. 153. Disponível em: [https://www.mdpi.com/1999-5903/17/4/153](https://www.mdpi.com/1999-5903/17/4/153)

---

## Integração e Entrega Contínua (DevOps)

**Disciplina:** Integração e Entrega Continua (DevOps)
**Professor:** Prof. Deivison S. Takatu
**Instituição:** Fatec Sorocaba


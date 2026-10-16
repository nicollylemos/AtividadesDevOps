# AWS CloudFormation — Apresentação de Ferramentas DevOps

Resumo da Aula 08, Apresentação de Ferramentas DevOps, da disciplina de Integração e Entrega Contínua (DevOps) da FATEC Sorocaba, com o Prof. Me. Deivison S. Takatu. A ferramenta escolhida pelo grupo foi o **AWS CloudFormation**.

## Integrantes

| Nome | GitHub |
| --- | --- |
| Karina de Moraes Garcia | — |
| Mike Willy Franguelli | — |
| Nicolly Lemos da Silva | [@nicollylemos](https://github.com/nicollylemos) |
| Pedro Henrique Cardozo Dias | — |
| Rafaela Mansano Fernandes | [@rafamans4no](https://github.com/rafamans4no) |

## A proposta da aula

Cada grupo escolheu uma ferramenta do ecossistema DevOps e preparou uma apresentação de 15 a 20 minutos explicando o que ela é, que problema resolve, como funciona, em que etapa do DevOps entra, como se integra a um projeto e quais são suas vantagens e limitações. Sempre que possível, a apresentação também precisava ter uma demonstração prática no formato entrada → processo → resultado.

## O que é o CloudFormation

É o serviço de **Infraestrutura como Código (IaC)** nativo da AWS, lançado em 2011. Em vez de criar servidores, bancos e redes clicando no console, você descreve tudo num arquivo YAML ou JSON (o *template*), e a AWS cria os recursos a partir dele. O serviço é gratuito: paga-se apenas pelos recursos criados.

## Que problema resolve

- **Provisionamento manual:** criar recursos pelo console é lento, sujeito a erro e difícil de repetir.
- **Falta de rastreabilidade:** sem código, não fica registrado o que mudou, quando e por quem.
- **Ambientes diferentes:** recriar à mão um ambiente de desenvolvimento, homologação ou produção quase nunca resulta em cópias idênticas.

## Como funciona

1. **Template:** um arquivo YAML ou JSON descreve os recursos e suas dependências.
2. **Stack:** a AWS cria uma *stack*, um conjunto de recursos gerenciado como uma unidade.
3. **Orquestração:** o CloudFormation descobre sozinho a ordem certa de criação.
4. **Rollback:** se algo falhar no meio, ele desfaz o que já tinha sido criado.

Antes de alterar uma stack existente, dá para gerar um **Change Set**, que é uma prévia do que vai ser criado, alterado ou removido.

Exemplo de template simples, que cria um bucket S3:

```yaml
AWSTemplateFormatVersion: "2010-09-09"
Description: Bucket S3 de exemplo

Resources:
  MeuBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-bucket-exemplo-devops
```

```bash
aws cloudformation deploy --template-file template.yaml --stack-name exemplo-devops
```

## Onde entra no DevOps

O CloudFormation atua principalmente nas etapas de **Release e Deploy**. A infraestrutura passa a ser versionada no Git junto com o código, pipelines como o AWS CodePipeline criam ou atualizam os recursos automaticamente, e as mudanças de infraestrutura podem ser revisadas por pull request, como qualquer outro código.

## Integração

- **Serviços AWS:** EC2, S3, RDS, Lambda, VPC, IAM e centenas de outros.
- **CI/CD:** CodePipeline e CodeBuild, para provisionar a infraestrutura a cada deploy.
- **AWS CDK:** permite escrever a infraestrutura em TypeScript ou Python e gerar o template automaticamente.
- **Git:** templates versionados e revisados como código.

## Vantagens e limitações

| Vantagens | Limitações |
| --- | --- |
| Nativo da AWS e sem custo próprio | Só funciona na AWS, não é multi-cloud |
| Rollback automático em caso de falha | YAML/JSON pode ser difícil para iniciantes |
| Gerencia todo o ciclo de vida da infraestrutura | Templates grandes ficam difíceis de manter |
| Change Set mostra as mudanças antes de aplicar | Depurar erros pode ser trabalhoso |

## Concorrentes

| Ferramenta | Provedor | Multi-cloud | Linguagem |
| --- | --- | --- | --- |
| AWS CloudFormation | AWS | Não | YAML / JSON |
| Terraform | HashiCorp | Sim | HCL |
| AWS CDK | AWS | Não | TypeScript, Python, Java |
| Pulumi | Multi-cloud | Sim | TypeScript, Python, Go |
| Google Deployment Manager | Google Cloud | Não | YAML / Python |

## Conclusão

O CloudFormation vale a pena para projetos que já estão na AWS e precisam de ambientes reproduzíveis, para times que querem versionar e auditar cada mudança de infraestrutura e para quem busca automação sem depender de ferramentas de terceiros. O principal aprendizado do grupo foi que tratar a infraestrutura como código traz previsibilidade e reduz o erro humano: é a ponte entre escrever o código e ter um ambiente funcionando.

## Referências

- AWS. *What is AWS CloudFormation?* Documentação oficial. https://docs.aws.amazon.com/cloudformation/
- HUMBLE, J.; PRIKLADNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. São Paulo: Bookman, 2013.
- ARUNDEL, J.; DOMINGUS, J. *DevOps nativo de nuvem com Kubernetes*. São Paulo: Novatec, 2019.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps*. São Paulo: Alta Books, 2018.
- SPACELIFT. *Pulumi Alternatives*: comparativo de ferramentas de Infrastructure as Code, 2026.

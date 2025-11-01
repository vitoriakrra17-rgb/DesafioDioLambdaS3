⚙️ Laboratório AWS Lambda e S3 — Tarefas Automatizadas
🧩 Descrição do Projeto

Este laboratório teve como objetivo consolidar conhecimentos em automação na AWS, utilizando Lambda Functions em conjunto com o Amazon S3.
A proposta foi compreender como integrar serviços serverless e de armazenamento, executando tarefas automatizadas sem necessidade de servidores dedicados.

🎯 Objetivos

Entender o funcionamento e a configuração básica de uma AWS Lambda Function.

Aprender a conectar eventos do S3 (como upload de arquivos) a uma função Lambda.

Experimentar o fluxo automatizado de execução de código em resposta a eventos.

Documentar os insights e aprendizados obtidos durante a prática.

🚀 Implementação

Durante a prática, foi criada uma automação simples onde:

Um bucket S3 recebe arquivos enviados manualmente ou via script.

O envio (upload) de um novo arquivo dispara automaticamente uma função Lambda.

A Lambda Function processa o evento, realizando uma ação simples (por exemplo, registrar logs ou mover o arquivo para outra pasta dentro do bucket).

Exemplo ilustrativo de código Lambda (Python 3.9):

import json

def lambda_handler(event, context):
    print("Evento recebido do S3:")
    print(json.dumps(event, indent=2))
    return {
        'statusCode': 200,
        'body': json.dumps('Execução Lambda concluída com sucesso!')
    }

☁️ Serviços Utilizados

AWS Lambda — execução de código sem servidor.

Amazon S3 — armazenamento e disparo de eventos.

AWS IAM — controle de permissões entre Lambda e S3.

🧠 Insights e Aprendizados

O modelo serverless elimina a necessidade de gerenciar servidores e infraestrutura.

Eventos do S3 permitem respostas automáticas a ações do usuário (upload, exclusão, etc.).

O log no CloudWatch é essencial para depurar e monitorar execuções da Lambda.

É possível escalar facilmente a automação adicionando novas funções ou integrações.

🗂️ Estrutura do Repositório
├── lambda_function.py     # Código da função Lambda
├── template.json          # (opcional) Template CloudFormation/Terraform da infra
├── README.md              # Documentação do projeto
└── /screenshots           # (opcional) Evidências da execução e logs

📘 Conclusão

Este laboratório reforçou o entendimento sobre integração entre Lambda e S3, demonstrando o potencial da automação com serviços AWS serverless.
A experiência serve como base para criar fluxos mais complexos, como processamento de imagens, ETL de dados, ou integrações com DynamoDB e API Gateway.

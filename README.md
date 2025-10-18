# ☁️ Desafio de Projeto — Implementando uma Infraestrutura Automatizada com AWS CloudFormation

## 🎯 Descrição do Desafio

Este repositório contém os materiais e anotações desenvolvidos durante o desafio da **Digital Innovation One (DIO)**:  
**“Implementando uma Infraestrutura Automatizada com AWS CloudFormation”**.

O objetivo é **explorar a automação de infraestrutura como código (IaC)** utilizando templates em **YAML** ou **JSON** para **criar, configurar e gerenciar recursos AWS** de forma padronizada, escalável e segura.

Durante o laboratório, foram aplicados conceitos de:
- **Padronização e replicação de ambientes**
- **Provisionamento automatizado**
- **Segurança e versionamento de templates**
- **Execução e atualização de Stacks**
- **Infraestrutura modular com Nested Stacks**

---

## 📘 Objetivos de Aprendizado

- Entender o ciclo de vida de uma Stack (criação, atualização, deleção).  
- Aprender a **modelar infraestrutura completa** como código (IaC).  
- Explorar o uso de **parâmetros, condições e outputs** em templates.  
- Aplicar boas práticas de **segurança, versionamento e modularização**.  
- Simular cenários reais de provisionamento automatizado de recursos AWS.

---

## 🧩 Arquitetura do Projeto

A infraestrutura projetada inclui recursos essenciais para um ambiente cloud automatizado, como:

- **Instância EC2** configurada automaticamente.  
- **Bucket S3** para armazenamento seguro de dados.  
- **Security Group** com regras de acesso personalizadas.  
- **IAM Role** para controle de permissões.  
- **Outputs** para exportar informações úteis (como IPs e URLs).  

📊 Veja o diagrama de arquitetura na pasta [`/notes/arquitetura.md`](./notes/arquitetura.md).

---

## 📂 Estrutura de Pastas

| Pasta / Arquivo | Descrição |
|------------------|------------|
| [`notes/conceitos-basicos.md`](notes/conceitos-basicos.md) | Resumo teórico sobre CloudFormation e IaC. |
| [`notes/boaspraticas.md`](notes/boaspraticas.md) | Boas práticas de automação e segurança. |
| [`notes/insights.md`](notes/insights.md) | Lições e observações do laboratório. |
| [`notes/arquitetura.md`](notes/arquitetura.md) | Diagrama e explicação da arquitetura criada. |
| [`notes/exemplos-templates.md`](notes/exemplos-templates.md) | Exemplos de templates YAML/JSON. |

---

## 💻 Tecnologias e Serviços Utilizados

- **AWS CloudFormation**  
- **Amazon EC2**  
- **Amazon S3**  
- **IAM Roles & Policies**  
- **Security Groups**  
- **YAML / JSON**  

---

## 💡 Insights Principais

- A automação via CloudFormation reduz erros humanos e aumenta a consistência entre ambientes.  
- Templates versionados permitem **controle e rastreabilidade total da infraestrutura**.  
- O uso de **parâmetros e condições** torna o template dinâmico e flexível.  
- A aplicação de boas práticas de segurança evita configurações vulneráveis.  

---

## 📚 Referências

- [📘 Documentação AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/index.html)  
- [⚙️ Guia de Boas Práticas AWS](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/best-practices.html)   
- [🧩 AWS CloudFormation Designer](https://console.aws.amazon.com/cloudformation/designer)

---

🔗 Desafio de Projeto da [Digital Innovation One (DIO)](https://www.dio.me/) \
📅 Concluído em: Outubro/2025 

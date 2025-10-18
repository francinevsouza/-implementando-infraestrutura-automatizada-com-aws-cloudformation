# ☁️ Conceitos Básicos — AWS CloudFormation e Infraestrutura Automatizada

## 🧱 O que é Infraestrutura como Código (IaC)?

**Infraestrutura como Código (IaC)** é a prática de gerenciar e provisionar recursos de TI (como servidores, redes e bancos de dados) por meio de **arquivos de configuração**, em vez de processos manuais.

Essa abordagem traz **automação, padronização e reprodutibilidade**, permitindo que ambientes complexos sejam criados de forma rápida e consistente.

---

## 🧰 O que é o AWS CloudFormation?

O **AWS CloudFormation** é o serviço de IaC da Amazon Web Services que permite **criar, atualizar e versionar recursos AWS automaticamente** usando templates escritos em **YAML** ou **JSON**.

Com ele, você descreve sua infraestrutura (instâncias, buckets, roles, etc.) e o CloudFormation cuida de **provisionar tudo na ordem correta**, com controle de dependências e rollback automático.

---

## 🧩 Principais Conceitos

| Conceito | Descrição |
|-----------|------------|
| **Template** | Arquivo YAML/JSON que define todos os recursos e parâmetros da infraestrutura. |
| **Stack** | Conjunto de recursos criados e gerenciados como uma unidade. |
| **Parameters** | Valores dinâmicos usados para personalizar o template. |
| **Mappings** | Estruturas para definir variações de configuração por região, ambiente, etc. |
| **Conditions** | Permitem criar recursos apenas quando certas condições são atendidas. |
| **Outputs** | Retornam informações úteis ao final da criação (ex: IP público, URL do site). |

---

## ✅ Benefícios do CloudFormation

- Automação completa de recursos na AWS.  
- Criação de ambientes padronizados e consistentes.  
- Redução de erros humanos.  
- Integração com versionamento Git.  
- Facilidade para replicar ambientes (dev, staging, produção).  
- Suporte a dependências e rollback automático em caso de falha.

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*

# 🧭 Boas Práticas — CloudFormation e Automação de Infraestrutura

## 📋 Organização e Estrutura

- É preferível utilizar **YAML** pela legibilidade e clareza.  
- Utilizar descrições (`Description:`) em cada recurso.  
- Manter a estrutura do template dividida em seções:

```bash
AWSTemplateFormatVersion
Description
Parameters
Resources
Outputs
```

---

## 🧩 Modularização e Reutilização

- Utilizar **Nested Stacks** para dividir grandes templates.  
- Centralizar parâmetros reutilizáveis (ex: tipo de instância EC2, nomes de buckets).  
- Utilizar **Exports/Imports** para compartilhar outputs entre stacks.  
- Criar **templates base** para ambientes padrão (dev, test, prod).

---

## 🔒 Segurança

- Nunca incluir **senhas, chaves ou tokens** no template.  
- Usar **AWS Secrets Manager** ou **SSM Parameter Store**.  
- Respeitar o princípio de **menor privilégio** nas IAM Roles.  
- Criar **Security Groups** com regras específicas e bem documentadas.

---

## ⚙️ Validação e Controle de Versão

Antes de subir qualquer template, validar:
```bash
aws cloudformation validate-template --template-body file://infra.yaml
```

- Versionar os templates com Git.
- Testar em um ambiente sandbox antes de aplicar em produção.
- Documentar mudanças em cada commit.

---

## 🚀 Performance e Escalabilidade

- Usar Auto Scaling Groups quando possível.
- Combinar CloudFormation com AWS Lambda para automações pós-deploy.
- Configurar tags em todos os recursos para controle e billing.

---

## 📝 Dica Extra

- Monitorar alterações não gerenciadas pelo CloudFormation com o comando:

```bash
aws cloudformation detect-stack-drift --stack-name MinhaStack
```

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*

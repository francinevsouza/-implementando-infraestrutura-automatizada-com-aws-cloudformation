# 🧩 Arquitetura — AWS CloudFormation Infraestrutura Automatizada

## 🌐 Visão Geral

O diagrama abaixo representa uma arquitetura típica criada por meio do **AWS CloudFormation**, demonstrando como diferentes serviços da AWS se integram de forma automatizada e segura.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/528174b5-a2c9-44c6-a60c-e5ef6ded4e1b" />

Essa estrutura reflete o cenário de um **servidor web automatizado** com integração a armazenamento e controle de acesso.

---

## 🧱 Componentes da Arquitetura

### 🧍‍♀️ 1. Usuário (Client)
O usuário é quem acessa a aplicação hospedada na nuvem — pode ser um cliente final ou outro sistema.  
O acesso parte da internet e é direcionado para os recursos AWS dentro da VPC.

### 🌐 2. Internet Gateway
O **Internet Gateway** é a “porta de entrada” da VPC, permitindo que os recursos internos (como instâncias EC2) **comuniquem-se com a internet**.  
Ele é essencial para aplicações web que precisam ser acessadas externamente.

### 🛡️ 3. Security Group
O **Security Group** atua como um **firewall virtual**, controlando quais portas e IPs podem se conectar aos recursos dentro da VPC.  
Exemplo:  
- Porta 22 → SSH (acesso administrativo)  
- Porta 80/443 → HTTP/HTTPS (acesso web)

Essas regras garantem **segurança e isolamento de tráfego**.

### 🏗️ 4. VPC (Virtual Private Cloud)
A **VPC** é a **rede virtual privada** onde toda a infraestrutura é hospedada.  
Ela fornece isolamento, sub-redes, roteamento e controle de acesso à camada de rede.  
Todos os recursos — EC2, S3, Security Groups, IAM — estão logicamente dentro dela.

### 💻 5. EC2 Instance
A **EC2 Instance** é o **servidor virtual** onde a aplicação roda (ex: servidor web, API, banco de dados).  
O CloudFormation provisiona essa instância automaticamente, definindo:
- Tipo de instância (ex: t2.micro)  
- Sistema operacional (via AMI)  
- Regras de acesso (Security Group)  
- Permissões (IAM Role)

### 🔑 6. IAM Role
A **IAM Role** define **as permissões seguras** que a EC2 possui dentro da AWS.  
Por exemplo, ela pode permitir que a instância:
- Envie logs para o CloudWatch  
- Acesse um bucket S3  
- Utilize serviços de automação, como Lambda ou SNS  

Isso elimina a necessidade de armazenar chaves secretas localmente.

### 🗃 7. S3 Bucket
O **Amazon S3** é o serviço de armazenamento usado para guardar arquivos da aplicação, logs ou backups.  
A EC2 acessa o S3 de forma segura usando a IAM Role — sem necessidade de credenciais.  

O S3 é essencial em arquiteturas CloudFormation, pois permite **armazenamento escalável e durável** de dados.


## 🔁 Fluxo de Comunicação

1. O **usuário** acessa a aplicação via navegador ou API.  
2. O tráfego passa pelo **Internet Gateway** e **Security Group**, garantindo segurança.  
3. A **EC2 Instance** processa a requisição.  
4. A **IAM Role** autoriza a EC2 a interagir com o **S3 Bucket**, quando necessário.  
5. O resultado é enviado de volta ao usuário.

---

## ⚙️ CloudFormation em Ação

Todos esses componentes são definidos em um **template CloudFormation (YAML ou JSON)**, que descreve:
- Recursos (Resources)
- Dependências (DependsOn)
- Parâmetros e Outputs

Ao executar o template, a AWS cria automaticamente toda a infraestrutura descrita, aplicando o conceito de **Infraestrutura como Código (IaC)**.

---

## 🚀 Benefícios da Automação

- **Padronização:** todos os ambientes seguem a mesma configuração.  
- **Reprodutibilidade:** fácil replicar em dev, staging e produção.  
- **Segurança:** permissões e acessos controlados.  
- **Escalabilidade:** recursos prontos para crescer com a demanda.  
- **Controle de versão:** templates versionados no GitHub.

---

> 💡 **Resumo:**  
> O AWS CloudFormation transforma a criação manual de infraestrutura em um processo **automático, previsível e seguro**, permitindo que desenvolvedores foquem em lógica de negócio, não em configuração de servidores.

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*

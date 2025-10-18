# 📄 Exemplos de Templates — AWS CloudFormation Infra

---

## ☁️ Template Completo em YAML — Infraestrutura Base (EC2 + S3 + Security Group)

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Infraestrutura base com EC2, S3 e Security Group

Parameters:
  KeyName:
    Description: Nome do par de chaves SSH existente
    Type: AWS::EC2::KeyPair::KeyName

Resources:
  WebServerSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: Permitir SSH e HTTP
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0

  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0
      KeyName: !Ref KeyName
      SecurityGroupIds:
        - !Ref WebServerSecurityGroup
      Tags:
        - Key: Name
          Value: CloudFormationServer

  MyS3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: !Sub "meu-bucket-${AWS::AccountId}-${AWS::Region}"

Outputs:
  EC2PublicIP:
    Description: IP público da instância EC2
    Value: !GetAtt MyEC2Instance.PublicIp
  S3BucketName:
    Description: Nome do bucket criado
    Value: !Ref MyS3Bucket
```

---

Este exemplo demonstra um ambiente automatizado com:

- EC2 configurada automaticamente.
- Security Group seguro e reutilizável.
- S3 Bucket nomeado dinamicamente por conta e região.
- Uso de parâmetros e outputs para flexibilidade e reutilização.

---

✍️ *Anotações e prática desenvolvidas por **Francine Souza**, como parte do desafio da DIO.*

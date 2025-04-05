# 🚀 Projeto de Migração e Modernização de Infraestrutura para AWS

Este projeto documenta as etapas de **migração Lift-and-Shift (As-Is)** com **AWS MGN** e a posterior **modernização com Kubernetes (EKS)**, incluindo práticas de segurança, automação com CI/CD, backup e controle de custos via AWS Calculator.

---

## 🧭 Etapa 1: Migração Lift-and-Shift (As-Is)

### Diagrama da Infraestrutura 

![Migração](/Imagens/Migração%20(2).png)

### ✅ Atividades Necessárias

**Preparação da Infraestrutura AWS**
- Criar **VPC** e **Subnets** (públicas e privadas).
- Definir **Security Groups** e **IAM Roles**.
- Configurar **AWS WAF** para proteção contra ataques.
- Criar **Amazon Route 53** para gerenciamento de DNS.

**Migração com AWS MGN**
- Instalar o **AWS MGN Replication Agent** nos servidores legados.
- Configurar replicação contínua para a AWS.
- Criar instâncias **EC2** idênticas ao ambiente original.

**Banco de Dados**
- Criar uma instância **Amazon RDS MySQL Multi-AZ**.
- Migrar dados usando **AWS DMS** (Database Migration Service).

**Redirecionamento de Tráfego**
- Configurar o **Application Load Balancer (ALB)**.
- Atualizar o **Route 53** para apontar para o ambiente AWS.

**Finalização e Otimização**
- Testar a aplicação na AWS.
- Desativar os servidores antigos.
- Configurar **AWS Backup** e **CloudWatch**.

---

### 🧰 Ferramentas Utilizadas

- **AWS MGN** – Migração Lift-and-Shift.
- **Amazon EC2** – Execução das instâncias migradas.
- **Amazon RDS Multi-AZ** – Banco de dados gerenciado.
- **AWS DMS** – Migração de dados.
- **Amazon Route 53** – Gerenciamento de DNS.
- **AWS WAF** – Proteção contra ataques Web.
- **AWS Secrets Manager** – Armazenamento seguro de segredos.
- **CloudWatch** – Monitoramento de métricas e logs.
- **AWS Backup** – Políticas de backup.

---

### 🔐 Requisitos de Segurança

**Infraestrutura**
- VPC privada com subnets isoladas.
- Regras de **Security Groups** e **Network ACLs**.
- Controle de permissões com **IAM Roles** e **Policies**.
- **AWS WAF** contra ataques DDoS e exploração de vulnerabilidades.

**Dados**
- Alta disponibilidade com **RDS Multi-AZ**.
- Criptografia com **AWS KMS**.
- Armazenamento seguro de credenciais com **Secrets Manager**.

---

### 💾 Backup

- **RDS**: Snapshots automáticos e backups manuais.
- **Arquivos/Servidores**: Armazenamento no **S3**.
- **EC2**: Proteção por políticas do **AWS Backup**.

---

### 💰 Custo Estimado (AWS Calculator)

- **Custo Mensal**: **US$ 935,28**
- [👉 Ver estimativa](https://calculator.aws/#/estimate?id=a347619030bf6ab70a7d70824b942da06e6a3430)

---

## 🧱 Etapa 2: Modernização com Kubernetes

### Diagrama da Infraestrutura 
![Modernização](/Imagens/Modernização.png)

### ✅ Atividades Necessárias

- Criar um **Cluster Amazon EKS**.
- **Dockerizar** a aplicação para contêineres.
- Configurar **Auto Scaling** e **Load Balancer**.
- Implementar **CI/CD** com **CodePipeline** e **CodeBuild**.
- Armazenar segredos no **AWS Secrets Manager**.

---

### 🧰 Ferramentas Utilizadas

- **Amazon EKS** – Orquestração de contêineres.
- **AWS Fargate** – Execução sem gerenciamento de servidores.
- **CodePipeline & CodeBuild** – Automação de CI/CD.
- **AWS Secrets Manager** – Gestão de credenciais.
- **Amazon ECR** – Armazenamento de imagens Docker.

---

### 🔐 Requisitos de Segurança

**Execução**
- IAM Roles e Policies restritivas no EKS.
- Controle de acesso com **RBAC** no Kubernetes.
- Proteção de camada 7 com **AWS WAF**.

**Dados**
- Gestão segura de senhas e tokens com **Secrets Manager**.
- Armazenamento de artefatos criptografados no **S3**.

---

### 💾 Backup

- **RDS**: Snapshots automáticos.
- **EKS/Contêineres**: Versionamento no **ECR**.
- **Aplicações**: Protegidas com **AWS Backup**.

---

### 💰 Custo Estimado (AWS Calculator)

- **Custo Mensal**: **US$ 942,18**
- [👉 Ver estimativa](https://calculator.aws/#/estimate?id=cc6ff4425a72f035d9dcb006bd483839620f3b98)

---

## 📄 Autor

**Autor:** Caique Mendes Pereira Rocha  
**Autor:** Efrain Levi de Jesus

---



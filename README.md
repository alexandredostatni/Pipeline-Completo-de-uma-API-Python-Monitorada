Pipeline Completo de uma API Python Monitorada

Projeto prático de DevOps Júnior desenvolvido inteiramente no GitHub Codespaces, cobrindo o ciclo completo de uma aplicação: desenvolvimento, containerização, infraestrutura como código, orquestração, CI/CD e monitoramento.

---

Objetivo:

Construir e documentar um pipeline DevOps completo, usando as principais ferramentas do mercado, simulando um cenário real de entrega de uma API Python com métricas expostas para Prometheus.

---

Tecnologias Utilizadas:

| Categoria              | Ferramentas                          |
|------------------------|--------------------------------------|
| Linguagem              | Python (Flask)                       |
| Containerização        | Docker                               |
| Orquestração           | Kubernetes (k3d)                     |
| Infraestrutura como Código | Terraform                        |
| Configuração           | Ansible                              |
| CI/CD                  | GitHub Actions                       |
| Cloud                  | AWS (EC2, ECR, VPC, IAM)             |
| Monitoramento          | Prometheus + Grafana                 |
| Versionamento          | Git + GitHub                         |
| Ambiente de desenvolvimento | GitHub Codespaces               |

---

Estrutura do Repositório:

├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── terraform/
│   └── main.tf
├── ansible/
│   ├── inventory.ini
│   └── playbook.yml
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── .github/workflows/
│   └── ci-cd.yml
├── .gitignore
└── README.md


---

Como Executar o Projeto:

### Pré-requisitos

- Conta no GitHub
- Conta na AWS (Free Tier)
- Usuário IAM com Access Key e permissões adequadas
- GitHub Codespaces (recomendado)

### 1. Abrir o projeto no Codespace

1. Acesse o repositório
2. Clique em **Code → Codespaces → Create codespace on main**
3. Escolha a máquina de 4 cores

### 2. Configurar credenciais AWS

```bash
export AWS_ACCESS_KEY_ID="sua-access-key"
export AWS_SECRET_ACCESS_KEY="sua-secret-key"
export AWS_DEFAULT_REGION="us-east-1"

Lições Aprendidas:

A pasta .terraform/ nunca deve ser commitada (gera arquivos de centenas de MB).
Key Pairs no AWS são imutáveis — a melhor prática é gerar a chave via Terraform (tls_private_key).
Credenciais AWS no Codespace precisam ser exportadas novamente a cada reinício da sessão.
Secrets do GitHub Actions devem ser colados com extremo cuidado (sem espaços extras).
O uso de k3d no Codespace é excelente para praticar Kubernetes sem custo de cluster gerenciado.
Separar bem as responsabilidades (IaC, configuração, aplicação e monitoramento) facilita o entendimento e a manutenção.

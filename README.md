#  Assessment — Pipeline Completo de DevOps

Este repositório contém a consolidação de todas as etapas do projeto avaliativo, implementando um pipeline completo de **Dockerização**, **Orquestração com Kubernetes** e **Automação CI/CD com GitHub Actions**.  
O objetivo é demonstrar um fluxo real de DevOps, desde o código-fonte até a entrega contínua.

---

##  Estrutura do Projeto

| Diretório/Arquivo      | Descrição |
|-----------------------|-----------|
| `devcalc-api/`        | Código-fonte da aplicação Java/Maven. |
| `Kubernetes-k8s/`     | Arquivos YAML do Deployment e Service. |
| `.github/workflows/`  | Workflows de CI/CD utilizados no TP3. |
---

#  Etapa 1 — Dockerização do Projeto

A aplicação foi containerizada para garantir portabilidade e padronização entre ambientes.

###  Configuração do Dockerfile  
- Baseado em uma imagem Java  
- Copia o `.jar` gerado pelo Maven  
- Mantém o container ativo para orquestração (`tail -f /dev/null`)  

###  Imagem publicada

###  Evidências
<img width="1079" height="235" alt="docker" src="https://github.com/user-attachments/assets/6d62ddf5-aace-44b4-87be-8795d7623772" />

<img width="750" height="421" alt="container" src="https://github.com/user-attachments/assets/4a3c3bfe-046d-4018-ab1f-06672aaacf77" />

---

#  Etapa 2 — Kubernetes (Orquestração)

O projeto foi implantado em um cluster Kubernetes para proporcionar alta disponibilidade e tolerância a falhas.

###  Deployment (2 réplicas)
- Nome: `at-app-deployment`
- Tipo: ReplicaSet
- Garante resiliência e escalabilidade

###  Service (ClusterIP)
- Nome: `at-app-service`
- Proporciona um endereço interno estável
- Distribui o tráfego entre as réplicas

###  Evidências

<img width="519" height="92" alt="3de3 aheeeee" src="https://github.com/user-attachments/assets/83a0ed68-1939-4a52-bea0-e1724651e0a0" />

<img width="715" height="131" alt="final tp3" src="https://github.com/user-attachments/assets/738dddb5-1de2-4cb3-9b48-6f23bd1f076e" />

---

#  Etapa 3 — Workflows CI/CD (GitHub Actions)

A automação foi implementada usando GitHub Actions, atendendo aos requisitos do TP3:

### ✔️ Pipeline de Build  
### ✔️ Uso de Variáveis e Secrets  
### ✔️ Execução automática via gatilhos (`push`, `pull_request`)  

###  Evidências

<img width="217" height="239" alt="image" src="https://github.com/user-attachments/assets/ec4eba8f-ae98-40e8-abe9-6ff321bdab12" />

<img width="194" height="253" alt="image" src="https://github.com/user-attachments/assets/e16a00c5-fe78-4973-a3fa-0a7976004961" />

<img width="407" height="387" alt="image" src="https://github.com/user-attachments/assets/f99a564c-6f88-4931-9ad6-d4e4d4875d33" />

---

#  1. Git e o Ciclo de DevOps

O Git é a base para automação e rastreabilidade no pipeline.

###  Controle de Versão
- Histórico imutável  
- Auditoria  
- Rollback rápido  

###  Branches
- `main`: produção  
- `feature/*`: novas implementações  
- `fix/*`: correções  
- Integração via Pull Requests  

###  Tags
- Usadas para versões estáveis:  


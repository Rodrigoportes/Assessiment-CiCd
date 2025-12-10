Assessment: Pipeline Completo de DevOps
Este repositório contém a consolidação de todas as atividades desenvolvidas, demonstrando um pipeline completo de, Dockerização, e Orquestração com Kubernetes e Worckflows.
Estrutura do Projeto
Diretório/Arquivo
Conteúdo
devcalc-api
Código fonte da aplicação Java/Maven.
Kubernets-k8s/
Arquivos de orquestração Kubernetes (deployment.yaml, service.yaml).
.github/workflows/
Pipelines de CI/CD (Workflows do TP3).
Dockerfile
Arquivo de build da imagem Docker.


Etapa 1: Dockerização do Projeto 
O projeto foi containerizado utilizando Docker para garantir portabilidade.
Dockerfile: Localizado na raiz do projeto. O Dockerfile é configurado para usar o JAR gerado pelo Maven e garantir que o container permaneça ativo (via tail -f) para o K8s.
Imagem: rodrigopotes/at-cdci:latest (Publicada no DockerHub).
Evidência:


Etapa 2: Kubernetes (Orquestração) 
A aplicação roda em um cluster Kubernetes, garantindo a alta disponibilidade e gerenciamento do ciclo de vida.
Deployment: 2 Réplicas configuradas para o at-app-deployment. Isso garante a resiliência e alta disponibilidade.
Service: Um Service (at-app-service) foi criado e exposto via ClusterIP para fornecer um endereço estável e balancear o tráfego entre as 2 réplicas.
Evidência

Etapa 3: Workflows no GitHub Actions (CI/CD)
Pipelines automatizados no GitHub Actions que atendem a todas as especificações do TP3 (Build, Variáveis e Segurança).
Workflows do Projeto (TPs 1, 2 e 3)




1. Git e o Ciclo de DevOps

O Git desempenha um papel central na entrega contínua:
Controle de Versão e Rastreamento: O Git mantém um histórico imutável, permitindo auditoria e rollback rápido em caso de falhas.
Integração Contínua (CI): O commit atua como o gatilho (trigger) para os pipelines no GitHub Actions.
Importância de Branches e Tags
Branches: Essenciais para desenvolvimento paralelo. A main deve ser estável (produção), enquanto feature/ e fix/ são usadas para desenvolvimento isolado, integradas via Pull Request.
Tags: Marcam pontos imutáveis (v1.0.0). No CD, tags podem disparar o processo de Release.

2. Pipelines CI/CD (GitHub Actions)
Os workflows são arquivos YAML que definem a automação do ciclo de vida do software, estruturando os processos de Integração Contínua (CI) e Entrega Contínua (CD).
Estrutura dos Workflows
Jobs e Steps: Workflows são compostos por jobs (que rodam paralelamente ou em sequência) e steps (comandos ou actions).
Gatilhos (Triggers): Eventos como push ou pull_request iniciam a execução.
Evidências Adicionais
Detalhes da Execução
Logs de Execução
Logs de debug e mensagens de sucesso de cada step.
Configurações
Configuração de secrets e vars no GitHub (demonstrado no TP3).
Artefatos
O JAR é o artefato gerado pelo Maven CI Pipeline.



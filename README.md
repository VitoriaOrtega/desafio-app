# Desafio-app

Esta é uma aplicação simples que exibe uma página HTML, configurável via Kubernetes. A página é configurada por meio de um ConfigMap e a aplicação é empacotada usando Helm, o que facilita sua instalação no Kubernetes. A imagem Docker da aplicação usa o Nginx como servidor web


## Descrição dos Arquivos
- configmap.yaml: Define o conteúdo da página HTML
- deployment.yaml: Configura como o Kubernetes vai criar e gerenciar os pods da aplicação
- ingress.yaml: Define o acesso externo à aplicação
- service.yaml: Cria o serviço que expõe a aplicação dentro do cluster
- Dockerfile: Define a imagem Docker, usando o Nginx para servir o conteúdo HTML
- docker-compose.yaml: Para rodar a aplicação localmente usando Docker Compose
- values.yaml: Contém os parâmetros configuráveis do Helm, como número de réplicas, imagem Docker, portas, etc

## Requisitos

- Um cluster Kubernetes em execução (por exemplo, Minikube)
- Helm instalado e configurado no seu ambiente
- Docker e Docker Compose instalados localmente (opcional para rodar a aplicação localmente)

## Como executar

- Construa a imagem Docker da aplicação:
`docker build -t vitoriaortegaa/desafio-experts:1.0.1 . `

- Instale o Helm chart no cluster Kubernetes:
`helm install desafio-app ./chart/desafio-app`

- Confira se os pods foram criados corretamente:
`kubectl get pods`

### Para acessar a Aplicação:
Acesse a aplicação pelo Ingress. No arquivo `values.yaml`, o host configurado é `application-vitoria.local`. Certifique-se de que seu DNS ou /etc/hosts aponta para o IP correto

### Testar a aplicação localmente usando Docker Compose:
`docker-compose up`
# Homelab Linux Mint - Docker, Portainer, Nginx Proxy Manager e Homarr

Projeto desenvolvido para aprendizado prático de infraestrutura, virtualização e gerenciamento de containers, utilizando um ambiente Linux Mint como servidor de laboratório.

## Objetivos

- Aprender gerenciamento de containers Docker
- Utilizar Docker Compose para orquestração de serviços
- Centralizar o gerenciamento de containers através de uma interface web
- Implementar um proxy reverso para acesso simplificado aos serviços
- Criar um dashboard centralizado para visualização e monitoramento
- Documentar toda a infraestrutura de forma organizada e profissional

## Tecnologias

- Linux Mint
- Docker / Docker Compose
- Portainer CE
- Nginx Proxy Manager
- Homarr

## Portainer CE

O Portainer foi o primeiro passo do projeto, utilizado para gerenciar os containers Docker através de uma interface gráfica, facilitando a criação de stacks e o monitoramento dos serviços em execução.

### Atividades realizadas

- Instalação do Portainer CE
- Configuração do ambiente Docker
- Resolução de problemas relacionados ao Setup Token
- Criação da primeira Stack utilizando Docker Compose
- Implantação de containers via Portainer

<img width="1917" height="794" alt="portainer-local" src="https://github.com/user-attachments/assets/1390c815-21e0-4fdf-8f95-0190c9dea5e3" />

## Nginx Proxy Manager

Implementado como o "porteiro" da rede do laboratório, o Nginx Proxy Manager centraliza o acesso aos serviços através de domínios locais (`.local`), eliminando a necessidade de decorar IP e porta de cada aplicação.

<img width="1503" height="698" alt="image (1)" src="https://github.com/user-attachments/assets/c67b9268-964b-4deb-93dc-4ca81eb9004f" />


### Proxy Hosts configurados

| Domínio | Destino |
|---|---|
| `grafana.local` | `http://10.0.2.15:3000` |
| `homarr.local` | `http://10.0.2.15:7575` |
| `nginx.local` | `http://127.0.0.1:81` |
| `portainer.local` | `http://10.0.2.15:9000` |
| `prometheus.local` | `http://10.0.2.15:9090` |

### Aprendizados

- Configuração de proxy hosts e resolução de domínios via `/etc/hosts`
- Diferença entre SSL "HTTP Only" e reverse proxy com certificados
- Uso do bloco "Block Common Exploits" para reforçar a segurança
- Acesso aos serviços por nome (`.local`) em vez de IP:porta

## Homarr

O Homarr serve como o painel central do laboratório, reunindo em um único lugar o status, consumo de recursos e acesso rápido a todos os serviços implementados (Grafana, Prometheus, Portainer e Nginx Proxy Manager).

<img width="1860" height="880" alt="homarr-local" src="https://github.com/user-attachments/assets/db103ec7-3737-4f85-b479-6024b0452a53" />

## Próximos Passos

- Migrar o Homarr para Docker Compose
- Gerenciar todos os serviços através de Stacks
- Estudar HTTPS e Reverse Proxy com certificados

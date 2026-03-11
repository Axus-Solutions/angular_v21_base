#  Mini-Alura — Plataforma de Estudos Colaborativa

![Angular](https://img.shields.io/badge/Angular-21-red?logo=angular)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Node](https://img.shields.io/badge/Node.js-22-green?logo=node.js)
![pnpm](https://img.shields.io/badge/pnpm-fast%20package%20manager-orange?logo=pnpm)
![HLS](https://img.shields.io/badge/Streaming-HLS-purple)



## Sumário

- [ Sobre o Projeto](#sobre-o-projeto)
- [ Objetivos](#objetivos)
- [ Tecnologias Utilizadas](#tecnologias-utilizadas)
  - [ Frontend](#frontend)
- [ Streaming de Vídeo](#streaming-de-vídeo)
  - [Fluxo de Processamento de Vídeo](#fluxo-de-processamento-de-vídeo)
- [ Principais Páginas da Aplicação](#principais-páginas-da-aplicação)
  - [ Home](#home)
  - [ Cursos](#cursos)
  - [ Aula](#aula)
  - [ Dashboard](#dashboard)
- [ Como Rodar o Projeto](#como-rodar-o-projeto)
  - [ Rodando com Docker (Recomendado)](#rodando-com-docker-recomendado)
    - [Pré-requisitos](#pré-requisitos)
    - [Clonar o Repositório](#clonar-o-repositório)
    - [Subir a Aplicação](#subir-a-aplicação)
  - [ Rodando Localmente](#rodando-localmente)
    - [Pré-requisitos](#pré-requisitos-1)
    - [Instalar pnpm](#1-instalar-pnpm)
    - [Instalar Dependências](#2-instalar-dependências)
    - [Rodar Aplicação](#3-rodar-aplicação)
- [ Estrutura do Projeto](#estrutura-do-projeto)
- [ Melhorias Futuras](#melhorias-futuras)
- [ Links Úteis](#links-uteis)



## Sobre o Projeto

O **Mini-Alura** é uma plataforma de ensino online colaborativa inspirada em plataformas como a Alura.  
O objetivo do projeto é simular um ambiente completo de ensino digital, permitindo que usuários criem, organizem e consumam conteúdos educacionais estruturados em cursos.

A aplicação permite que criadores publiquem cursos organizados em **módulos e aulas**, enquanto outros usuários podem assistir às aulas em formato de vídeo, interagir através de comentários e avaliar o conteúdo.

Além disso, o projeto explora conceitos importantes como:

- Streaming de vídeo
- Arquitetura de aplicações modernas
- Organização de conteúdo educacional
- Escalabilidade de plataformas de ensino



## Objetivos

A plataforma foi projetada para permitir:

- Criação e organização de cursos
- Consumo de conteúdo educacional em vídeo
- Interação entre usuários através de comentários
- Avaliação e feedback dos cursos
- Navegação e descoberta de cursos
- Organização de conteúdo em módulos e aulas



## Tecnologias Utilizadas
- Angular
- TypeScript
- TailwindCSS
- PrimeNG
- Hls.js (streaming de vídeo)
- pnpm
- Docker



## Streaming de Vídeo

A aplicação utiliza o protocolo **HLS (HTTP Live Streaming)** para entregar vídeos de forma eficiente.

Esse protocolo fragmenta o vídeo em pequenos segmentos permitindo:

- streaming adaptativo
- carregamento progressivo
- melhor experiência em conexões instáveis

### Fluxo de processamento de vídeo
```text
Upload de vídeo
    │
    ▼
Backend recebe o arquivo
    │
    ▼
FFmpeg converte para HLS
    │
    ▼
Arquivos .m3u8 e .ts gerados
    │
    ▼
Arquivos armazenados no storage
    │
    ▼
Frontend consome o playlist.m3u8
```
Estrutura gerada:
```text
curso-1/
    playlist.m3u8
    segment0.ts
    segment1.ts
    segment2.ts
```

O player no frontend utiliza **Hls.js** para reproduzir o streaming.



## Principais Páginas da Aplicação

### Home

Página inicial da plataforma contendo:

- cursos em destaque
- navegação principal
- categorias disponíveis



### Cursos

Página responsável pela listagem de cursos disponíveis.

Inclui:

- busca por cursos
- filtros
- paginação



### Aula

Página dedicada ao consumo do conteúdo.

Contém:

- player de vídeo
- descrição da aula
- comentários
- progresso do aluno



### Dashboard

Área para gerenciamento de conteúdo.

Permite:

- criação de cursos
- organização de módulos
- adição de aulas
- upload de vídeos



## Como Rodar o Projeto

Existem duas formas de executar o projeto:

- usando **Docker**
- instalando as dependências localmente



## Rodando com Docker (Recomendado)

### Pré-requisitos
- Docker
- Docker Compose



### Clonar o repositório

```bash
git clone https://github.com/seu-usuario/minialura
cd minialura
```

### Subir a aplicação
```bash
docker compose up --build
```
a url de acesso ficara disponível na seguinte URI: [`http://localhost:4200`](http://localhost:4200) 

## Rodando Localmente
### Pré-requisitos
- Node.js 20+
- pnpm

### 1. Instalar pnpm
```bash
npm install -g pnpm
```

### 2. Instalar dependências
```bash
pnpm install
```
### 3. Rodar aplicação
```bash
pnpm start
```


a url de acesso ficara disponível na seguinte URI: [`http://localhost:4200`](http://localhost:4200)

##  Estrutura do Projeto
```bash
minialura/
  frontend/
    src/
    angular.json
    package.json
  ...
  backend/
    src/
  docker-compose.yml
  README.md
```

## Melhorias Futuras
- Sistema de progresso do aluno
- Recomendações de cursos
- Certificados de conclusão
- Streaming adaptativo com múltiplas qualidades
- CDN para distribuição de vídeos
- Upload direto para storage
- Sistema de playlists


## Links Úteis
- [Angular](https://angular.dev/overview)
- [Tailwind](https://tailwindcss.com/docs)
- [Hls.js](https://nochev.github.io/hls.js/docs/html/)
- [PrimeNg](https://primeng.org/installation)
- [Docker](https://docs.docker.com/)
- [Typescript](https://www.typescriptlang.org/)











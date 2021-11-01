---
title: "Vercel - Nuxt"
abstract: ""
imageHeader: "https://i.imgur.com/5QyMYlV.png"
cover:
createdDate: "2021-10-29 15:15"
updatedDate: ""
type: "normal"
headerLayout: "portrait-left"
layout: ""
isPublished: true
---

Nuxt.js é uma estrutura baseada em Vue.js de código aberto que fornece vários modos de renderização diferentes, um dos quais permite gerar um aplicativo estático.

Neste guia, você aprenderá a criar e implantar um aplicativo Nuxt.js com Vercel.

## Etapa 1: configurar seu projeto Nuxt.js

A primeira etapa na configuração de seu novo projeto Nuxt.js é gerá-lo com
`create-nuxt-app`:

```bash
npm init nuxt-app my-nuxt-app
```

Quando perguntado sobre qual modo de renderização você deseja usar, selecione `Single Page App`.

Com seu projeto Nuxt.js inicializado, vá para o diretório:

```bash
cd my-nuxt-app
```

Em seguida, altere o script de construção no arquivo `package.json` para o seguinte:

```json
{
  "scripts": {
    ...
    "build": "nuxt generate"
  }
}
```

## Etapa 2: Implantar Seu Projeto Nuxt.js com Vercel

Para implantar seu aplicativo Nuxt.js com Vercel para Git, certifique-se de que ele foi enviado para um repositório Git.

Importe o projeto para o Vercel usando o provedor Git de sua escolha.

Depois que seu projeto for importado, todos os envios subsequentes para as ramificações gerarão implantações de visualização e todas as alterações feitas na ramificação de produção (geralmente "principal") resultarão em uma implantação de produção.

Depois de implantado, você receberá um URL para ver seu aplicativo ativo, como o seguinte: https://nuxtjs.examples.vercel.com

Configure um aplicativo Nuxt.js com alguns cliques usando o botão Deploy e crie um repositório Git para ele no processo para implementações automáticas de suas atualizações.

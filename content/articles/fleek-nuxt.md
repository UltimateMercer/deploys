---
title: "Fleek - Nuxt"
abstract: ""
imageHeader: "https://i.imgur.com/EqLRbFT.png"
cover:
createdDate: "2021-10-29 15:30"
updatedDate: ""
type: "normal"
headerLayout: "portrait-left"
layout: ""
isPublished: true
---

## Implantando NuxtJS por meio de IPFS no Fleek

Neste artigo, mostraremos como implantar seu site construído em NuxtJS e como implantar usando IPFS em Fleek.

### O que é Fleek

Fleek é tudo que você precisa para criar sites e aplicativos rápidos e modernos em IPFS. Tudo em um fluxo de trabalho perfeito, do desenvolvimento local à implantação global, seu site não será executado apenas em IPFS, mas também será complementado com um CDN global de nível empresarial, permitindo velocidade, escala e desempenho superiores à hospedagem normal.

### O que é IPFS

IPFS significa `InterPlanetary File System`. O InterPlanetary File System é um protocolo e rede ponto a ponto para armazenar e compartilhar dados em um sistema de arquivos distribuído. O IPFS usa endereçamento de conteúdo para identificar exclusivamente cada arquivo em um namespace global conectando todos os dispositivos de computação.

### Iniciando um Projeto NuxtJS

O primeiro passo é criar um aplicativo nuxt envolvido em create-nuxt-app, o nome do meu diretório é `deploy-nuxtjs-using-ipfs-on-fleek`, o seu pode ser nomeado como quiser.

```bash
$ npx create-nuxt-app deploy-nuxtjs-using-ipfs-on-fleek
```

Uma vez feito isso, você agora tem seu repo criado, tudo o que resta é entrar no diretório usando a empresa abaixo

```bash
cd deploy-nuxtjs-using-ipfs-on-fleek
```

Execute o comando abaixo para iniciar o servidor de desenvolvimento que criaria um servidor em `http://localhost:3000/`

```bash
yarn dev
```

### Conteúdo da estrutura do arquivo

#### Assets

O diretório de assets é feito para ativos em relação a design/style, para este projeto estamos executando em CSS tailwind, portanto, em nossos assets/css temos `tailwind.css`

```scss
/* purgecss start ignore */
@import "tailwindcss/base";
@import "tailwindcss/components";
/* purgecss end ignore */
@import "tailwindcss/utilities";
```

#### Pages

O diretório `pages` é composto de suas Views e rotas reais do projeto, nuxt iria procurar por arquivos que terminam com uma extensão `.vue` e construir seus aplicativos a partir disso, neste artigo temos apenas um único arquivo chamado `index.vue`

```vue
<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        NuxtJS &
        <a href="https://fleek.co"> Fleek.co </a>
      </h1>
      <h2 class="subtitle">Deploying NuxtJS using IPFS on Fleek</h2>
      <div class="links">
        <a href="https://fleek.co" target="_blank" class="button--grey">
          Fleek
        </a>
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
  components: {
    Logo,
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
```

### Implantando para IPFS em Fleek

Implantar no IPFS nunca foi tão fácil graças ao Fleek, primeiro, visite fleek.co e signup.login usando sua conta GitHub, uma vez configurado, você deve ver seu painel

Depois de fazer isso, clique em Adicionar Novo Site, que o levará a uma nova página

Imediatamente após a conexão, pesquise o nome do repo no GitHub usando o recurso de pesquisa do lado direito da tela e clique no repo que foi listado

É importante notar neste ponto que o Nuxt oferece suporte a SSR (renderização do lado do servidor). Não queremos executar nosso site em SSR porque nossos arquivos são simplesmente hospedados em IPFS e não há servidor em execução neste cenário. Portanto, devemos nos certificar de que o site seja exportado como um site estático.

A próxima etapa é a página de configurações de implantação, a estrutura/linguagem é selecionada automaticamente pelo Fleek, uma vez que você tenha chegado a esta tela, clique em `Deploy Site`.

Enquanto seu aplicativo é implantado, você pode assistir a implantação usando o `Fleek Deploy Log`, deve levar menos de um minuto para completar a implantação

Sim! nosso aplicativo foi implantado, role até o topo e você encontrará um link, clicar nesse link leva você ao seu site implantado

### Trocando o nome ou adicionando um domínio no Fleek

Normalmente, quando você implanta um novo site no Fleek, você tem um nome de domínio muito engraçado, por exemplo `https://crimson-lab-6839.on.fleek.co/`, você pode alterar isso acessando as configurações e clicando em Alterar Dominio e, em seguida, coloque o domínio de sua preferência.

### Reflexões finais

…e é isso! A implantação de um site NuxtJS no Fleek é rápida e muito fácil, Fleek está procurando mudar a forma como a implantação funciona no IPFS, melhorando tudo.

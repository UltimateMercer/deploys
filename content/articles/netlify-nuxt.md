---
title: "Netlify - Nuxt"
abstract: ""
imageHeader: "https://i.imgur.com/X9cpS8c.png"
cover:
createdDate: "2021-10-29 15:00"
updatedDate: ""
type: "normal"
headerLayout: "portrait-left"
layout: ""
isPublished: true
---

## Nuxt no Netlify

Nuxt é uma estrutura modular de código aberto para a construção de sites e aplicativos de alto desempenho usando Vue.js.

### Características principais

Esses recursos do Nuxt fornecem benefícios importantes para sites e aplicativos, incluindo aqueles criados e implantados com o Netlify.

- _SEO aprimorado._ Com a capacidade de gerar estaticamente o seu site, a Nuxt pode ajudar a impulsionar a otimização do mecanismo de pesquisa para o seu conteúdo.

- _Roteamento de página._ Nuxt tem uma estrutura de roteamento baseada no sistema de arquivos. Organizar arquivos e subdiretórios dentro de um diretório de páginas resulta automaticamente em rotas correspondentes.

- _Otimização de imagem._ O módulo `nuxt/image` permite otimizar imagens automaticamente para o seu site.
- _Git-based Headless CMS._ O módulo `nuxt/content` analisa arquivos Markdown, JSON, YAML, XML e CSV em seu site.

### Integração Netlify

Os sites Nuxt no Netlify podem se beneficiar da detecção automática da estrutura e requerem considerações mínimas de configuração.

> Nuxt 3 beta no Netlify
>
> O Nuxt 3 beta foi lançado e está pronto para você experimentar no Netlify!
>
> Nuxt 3 apresenta novas opções de renderização, como renderização do lado do servidor (SSR). Como ele está atualmente em beta, recomendamos seguir o conselho da equipe do Nuxt sobre não usar o Nuxt 3 ainda em produção.

#### Detecção automática de estrutura

Quando você vincula um repositório para um projeto, o Netlify tenta detectar a estrutura que seu site está usando.

Se o seu site foi construído com Nuxt, o Netlify fornece um comando de construção sugerido e diretório de publicação:

- Nuxt 2: nuxt generate e dist
- Nuxt 3 (beta): nuxt build e dist

Se você estiver usando a CLI para executar o Netlify Dev para um ambiente de desenvolvimento local, a CLI deve funcionar automaticamente assumindo que você está usando o comando dev e a porta: `nuxt` e `3000`. Você pode substituir os valores sugeridos ou defini-los em um arquivo de configuração. mas a detecção automática da estrutura pode ajudar a simplificar o processo de configuração de um site no Netlify.

#### Considerações de configuração

Ao configurar um site Nuxt 2 gerado estaticamente para implantação no Netlify, verifique o seguinte:

- Se você estiver usando create-nuxt-app para gerar um novo projeto Nuxt, faça estas seleções:
  - Modo de renderização: `Universal (SSR / SSG)` (default)
  - Alvo de implantação: `static` (hospedagem estática / JAMstack)
- Se você tiver um projeto Nuxt existente, o arquivo `nuxt.config.js` do projeto deve conter target: `static`.

Para aplicativos de página única com renderização do lado do cliente, consulte a documentação do Nuxt para obter informações de configuração.

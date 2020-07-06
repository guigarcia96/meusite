---
template: post
title: Hello World API com NodeJS
slug: hello-world-api-nodejs
draft: false
date: 2020-07-06T14:37:03.058Z
description: >-
  Hoje em dia praticamente só se fala em NodeJS, mas você sabe usá-lo? 

  Hoje Criaremos uma simples API que retorna um JSON contendo o famoso "Hello World" 
category: NodeJS
tags:
  - "#nodejs #express #api"
---
Hoje em dia praticamente só se fala em NodeJS, mas você sabe usá-lo? 

Hoje Criaremos uma simples API que retorna um JSON contendo o famoso "Hello World" 

Vou partir do princípio que você já tem o Node e o NPM instalados. Caso não tenha, vou deixar um link de [instalação](https://www.devmedia.com.br/como-instalar-o-node-js-npm-e-o-react-no-windows/40329)

Primeiro criamos uma pasta com o nome hello_world_api. 

No terminal de comando, entramos na pasta que criamos e digitamos `npm init -y` (com isso criaremos o nosso package.json onde terá informações e configurações do servidor)

Vamos abrir o VSCode 

Dentro do VSCode criaremos a pasta src e dentro dela o arquivo index.js.

Não podemos esquecer de mudar o nosso package.json após criar um novo index.js. Dentro do package.json, no campo main, mudaremos para src/index.js

Agora que temos nossa estrutura de projeto, instalaremos o express

`npm install express `

Com o express vamos iniciar o nosso servidor backend 

Dentro do index.js faremos a importação do express e a configuração da variável app.

<!--StartFragment-->

`const express=require('express')`

`const app=express() `

`app.use(express.json()) //configuramos nosso servidor para requisições JSON.`

<!--EndFragment-->

Seguiremos para a configuração da nossa rota e retorno do Hello World.

<!--StartFragment-->

`//utilizaremos o metodo GET para retornar uma informação para o frontEnd`\
`//a rota escolhida será a pagina inicial do nosso servidor`

`app.get('/', (request,response)=>{`

`return response.json({message:"Hello World"})`

})

<!--EndFragment-->

Temos que definir a porta do nosso servidor e colocar alguma mensagem no terminal informando que o servidor está rodando

<!--StartFragment-->

`app.listen(3333, ()=>{`

`console.log('Servidor Rodando')`

`})`

<!--EndFragment-->

Por fim, nosso código ficará assim:

<!--StartFragment-->

`const express=require('express')`

`const app=express()`

`app.use(express.json())`

`app.get('/', (request,response)=>{`

`return response.json({message:"Hello World"})`

`})`

`app.listen(3333, ()=>{`

`console.log('Servidor Rodando')`

`})`

<!--EndFragment-->

Vamo rodar o servidor utilizando o código `node src/index.js`

![servidor](/media/servidor.png)

Agora é só abrir seu navegador, digitar <!--StartFragment-->

`http://localhost:3333/ ` e consumir sua aplicação do jeito/modo que quiser

<!--EndFragment-->



![hello_world](/media/localhost.png)



Claro que esse isso é o básico do básico em questão de NodeJS, porém já é um ótimo ponto inicial para você que quer começar a estudar ou até mesmo utilizá-lo em algum projeto.
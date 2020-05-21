# :pushpin: Sumário

1. [Objetivo do Projeto](#dart-objetivo-do-projeto)
2. [Sobre](#page_with_curl-sobre)
3. [Tecnologias Utilizadas](#rocket-tecnologias-utilizadas)
4. [Requisitos](#gear-requisitos)
5. [Rodar o Projeto](#arrow_forward-rodar-o-projeto)
6. [Resultado](#keyboard-resultado)
7. [Redes Sociais](#man_technologist-redes-sociais)

---

## :dart: Objetivo do Projeto

Uma API REST que gerencia o login, cria um usuário, autentica a seção com token JWT, refine sua senha, e tem uma rota protegida para realizar as operações de crud de um projeto no mongoDB.

## :page_with_curl: Sobre

O projeto foi desenvolvido seguindo uma PlayList do canal da [RocketSeat](https://www.youtube.com/channel/UCSfwM5u0Kce6Cce8_S72olg) - [Série API NodeJS](https://www.youtube.com/playlist?list=PL85ITvJ7FLoiXVwHXeOsOuVppGbBzo2dp), com o @diego3g ministrando as aulas, foi uma das primeiras API que criei com o Node.js, então a parte de autenticação com JWT e de criptografia com o Bcrypt foram novidades, até o envio de e-mail com Nodemailer, e a utilização do serviço MailTrap que é uma caixa de e-mail fake, para fazer envio de e-mail em ambiente de desenvolvimento, que pra falar a verdade nem sabia que existia esse tipo de serviço, foi um projeto muito interessante e pude obter muito conhecimento com ele.

## :rocket: Tecnologias Utilizadas

* [JS](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
* [Node.js](https://nodejs.org/en/)
* **Banco de dados:** [MongoDB](https://www.mongodb.com/)
* **Cliente REST:** [Insomnia](https://insomnia.rest/)

**Dependências**

* [bcryptjs](https://www.npmjs.com/package/bcryptjs)
* [express](https://expressjs.com/)
* [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
* [mongoose](https://mongoosejs.com/docs/index.html)
* [nodemailer](https://nodemailer.com/about/)
* [nodemailer-express-handlebars](https://www.npmjs.com/package/nodemailer-express-handlebars)
* **Serviço:** [MailTrap](https://mailtrap.io/)

## :gear: Requisitos

* [Git](https://git-scm.com/) (Para clonar, opcional)
* [Node.js](https://nodejs.org/en/)
* [Npm](https://www.npmjs.com/) (É instalado junto com o Node)
* [MongoDB Local](https://www.mongodb.com/download-center/community) ou [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/signup)
    - caso escolha o MongoDB Atlas, será necessário trocar o link do banco na função connect dentro de **src/database/index.js**

**Arquivos:**

* É necessario criar dois arquivos dentro da pasta **src/config**.
* **auth.json** com o conteúdo:
    - { "secret": "456bc20d374ee2f9db6cb55f87714559" }
    - secret, é o hash da aplicação para gerar o token.
    - vc pode gerar um hash md5 [Aqui](https://www.md5hashgenerator.com/).
* **mail.json** com o conteúdo necessario para criar o transporter do Nodemailer: 
    - { "host": "oHost", "port": aPorta, "user": "seuUser", "pass": "seuPass" }

## :arrow_forward: Rodar o Projeto

* Primeiro passo, clone ou baixe o projeto em sua maquina
* Abra a pasta do projeto no terminal
* Instale as dependências com o comando `npm i` 
* Inicie o servidor com o comando `npm start` 
* A aplicação estara disponível na porta: **3000**

## :keyboard: Resultado

**Rotas para lidar com a autenticação**

``` js
    // (POST) --- Rota de registro:
    'http://localhost:3000/auth/register'

    // Objeto usuario:
    {
        "name": "devsp",
        "email": "devsp@teste.com",
        "password": "123456"
    }

    // (POST) --- Rota de autenticação:
    'http://localhost:3000/auth/authenticate'

    // Objeto autenticação:
    {
        "email": "devsp@teste.com",
        "password": "123456"
    }

    // (POST) --- Rota de esqueci a senha:
    'http://localhost:3000/auth/forgot_password'

    // Objeto esqueci a senha:
    {
        "email": "devsp@teste.com",
    }

    // (POST) --- Rota de redefinir senha:
    'http://localhost:3000/auth/reset_password'

    // Objeto redefinir senha:
    {
        "token": "560bd885f4441f485b49ed4c42d0910261a5f053",
        "email": "devsp@teste.com",
        "password": "12345678"
    }
```

**Rotas para lidar com os projetos**

``` js
    // (GET) --- Rota para listar todos os projetos:
    'http://localhost:3000/projects'

    // (GET) --- Rota para um projeto:
    'http://localhost:3000/projects/idProjetoAqui'

    // (POST) --- Rota para cadastrar novo projeto:
    'http://localhost:3000/projects'

    // Objeto novo projeto:
    {
        "title": "tarefa 1",
        "description": "descrevendo tarefa",
        "tasks": [{
            "title": "nome da tarefa",
            "assignedTo": "idDoUsuario"
        }]
    }

    // (PUT) --- Rota para editar projeto:
    'http://localhost:3000/projects/idProjetoAqui'

    // Objeto editar projeto:
    {
        "title": "tarefa 1 (Editado)",
        "description": "descrevendo tarefa (Editado)",
        "tasks": [{
            "title": "nome da tarefa (Editado)",
            "assignedTo": "idDoUsuario"
        }]
    }

    // (DELETE) --- Rota para deletar um projeto:
    'http://localhost:3000/projects/idProjetoAqui'
```

## :man_technologist: Redes Sociais

* [instagram](https://www.instagram.com/devsp011/)
* [Linkedin](https://www.linkedin.com/in/vitor-sampaio-4532451a7/)

---

<h5 align='center' >Feito com :purple_heart: por <a href="https://github.com/devsp011" target="_blank">DevSp</a> </h5>

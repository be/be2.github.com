---
layout: post
title: "Bamboo migration"
description: "Parece que o problema identificado no post sobre o toto rss não era apenas no index.builder."
category: video
tags: [remix, talk, creativity, video]
---
{% include JB/setup %}

Parece que o problema identificado no post sobre o toto rss não era apenas no ‘index.builder’. Na verdade, o código do ‘index.builder’ original do toto funcionaria normalmente não fosse um problema nos apps que estão nos stacks bamboo 1.9.2 do heroku. A solução do Dmitry continua elegante, porém erros de sintaxe faziam com que o feed não pudesse ser validado, erros estes que tinham como causa a incompatibilidade do stack em questão com o código do toto. Heroku docs:

>A stack is a complete deployment environment including the base operating system, the language runtime and associated libraries. As a result, different stacks support different runtime environments – heroku docs.

O stack 1.8.7 é constituído por ruby 1.8.7 & rubygems 1.3.7 e o stack 1.9.2 por ruby 1.9.2 & rubygems 1.3.7, ambos sobre [x86_64-linux].

Atualmente o toto tem alguns issues com o ruby 1.9.2, portanto temos que migrar / retornar para o bamboo 1.8.7. Descobri isso ao tentar validar o feed via feedburner, quando fiquei intrigado com as mensagens de erro de teor de mal-formação simplória, como a falta de um slash numa linha, um caractere não permitido em outra, etc., que quando corrigidos reapareciam em outras linhas.

Neste [pull request](https://github.com/cloudhead/toto/pull/118) no ‘cloudhead:master’ encontra-se a solução. Para aplicativos existentes devemos fazer o seguinte:     

    heroku stack:migrate bamboo-ree-1.8.7

Para aplicativos novos:

    heroku create --stack bamboo-ree-1.8.7 

Segue a minha mudança no terminal:

    Last login: Thu Apr 12 22:02:44 on console
    MacBook-Pro-de-Bernardo-Alonso:~ bernardoalonso$ cd lacuna
    MacBook-Pro-de-Bernardo-Alonso:lacuna bernardoalonso$ heroku stack:migrate bambo
    o-ree-1.8.7
    -----> Preparing to migrate lacuna
    bamboo-mri-1.9.2 -> bamboo-ree-1.8.7

     NOTE: You must specify ALL gems (including Rails) in manifest

     Please read the migration guide:
     http://devcenter.heroku.com/articles/bamboo

    -----> Migration prepared.
     Run 'git push heroku master' to execute migration.
       
Aproveitei para atualizar um artigo antes de fazer o push master (caso contrário, o terminal te dá uma mensagem de ‘everything is up to date’):


    MacBook-Pro-de-Bernardo-Alonso:lacuna bernardoalonso$ git add articles/2012-04-1
    1-the-infinite-looper-nose.txt
    MacBook-Pro-de-Bernardo-Alonso:lacuna bernardoalonso$ git commit -m "the infinit
    e looper nose"
    [master a216fbc] the infinite looper nose
    1 files changed, 1 insertions(+), 1 deletions(-)
    MacBook-Pro-de-Bernardo-Alonso:lacuna bernardoalonso$ git push heroku master
    Counting objects: 7, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (4/4), done.
    Writing objects: 100% (4/4), 350 bytes, done.
    Total 4 (delta 3), reused 0 (delta 0)

    -----> Heroku receiving push
    -----> Migrating from bamboo-mri-1.9.2 to bamboo-ree-1.8.7

    -----> Installing gem builder from http://rubygems.org
       Successfully installed builder-3.0.0
       1 gem installed

    -----> Installing gem rdiscount from http://rubygems.org
       Building native extensions.  This could take a while...
       Successfully installed rdiscount-1.6.8
       1 gem installed

    -----> Installing gem toto from http://rubygems.org
       Successfully installed toto-0.4.9
       1 gem installed

    -----> Compiled slug size is 1.4MB
    -----> Launching... done, v253
       http://lacuna.heroku.com deployed to Heroku

    -----> Migration complete, your app is now running on bamboo-ree-1.8.7
    
    To git@heroku.com:lacuna.git
     1de90b4..a216fbc  master -> master
    MacBook-Pro-de-Bernardo-Alonso:lacuna bernardoalonso$


---
layout: post
title: "Permission denied publickey"
description: "Uma das coisas mais irrintantes que podem acontecer quando você está montando um projeto com ruby on rails no heroku é ao tentar usar o git push heroku master aparece a desgramada mensagem de erro."
category: apps
tags: [git, heroku, ssh]
---
{% include JB/setup %}


Uma das coisas mais irrintantes que podem acontecer quando você está montando um projeto com ruby on rails no heroku é ao tentar usar o

    git push heroku master 

aparece a desgramada mensagem de erro:

    Permission denied (publickey).
    fatal: The remote end hung up unexpectedly

Mas não se apoquente meu caro, a solução é simples ~ 

Através do terminal vá até à pasta do seu projeto:

    cd nomedoseuprojeto

E em seguinda insira o seguinte código:

    heroku keys:add ~/.ssh/id_rsa.pub

Agora a sua key será autenticada normalmente, pode mandar ver:

    git push heroku master

Voilá!


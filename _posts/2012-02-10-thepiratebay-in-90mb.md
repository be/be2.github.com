---
layout: post
title: "Thepiratebay in 90Mb"
description: "A maior de todas as vantagens dessa mudança é que será possível baixar tais dados em arquivos txt, ou seja, temos agora acesso a quase dois milhões de arquivos comprimidos em apenas 90Mb."
category: apps
tags: [thepiratebay, magnet links, txt, proxys]
---
{% include JB/setup %}


Ontem o site [Torrentfreak](http://torrentfreak.com/download-a-copy-of-the-pirate-bay-its-only-90-mb-120209/) divulgou a notícia de que em breve o The Pirate Bay, tradicional website de disseminação de arquivos torrent, vai migrar totalmente para o modelo de [magnet links](http://en.wikipedia.org/wiki/Magnet_link) e não mais semeará torrents. Todos sabem que o bicho está pegando. As corporações querem a todo custo manter o antigo e falido modelo da indústria do Audiovisual e para tanto não medirão esforços para destruir os focos de liberdade na rede. Apesar da tolerante política governamental da Suécia, sede da baía pirata, a pressão do governo americano já fez com que os responsáveis pelo site mudassem seu domínio de ‘.org’ para ‘.se’, caso os yankees tentem interromper o tráfego bloqueando a extensão do domínio.
Como é historicamente sabido que a covardia anglo-saxã não tem limites, os suecos resolveram disponibilizar uma maneira de compartilhar TODOS os dados do site de modo compacto usando a tecnologia de magnet links para uma eventual emergência (aka ataque). A maior de todas as vantagens dessa mudança é que será possível baixar tais dados em arquivos txt, ou seja, temos agora acesso a quase dois milhões de arquivos comprimidos em apenas 90Mb. Portanto, se os urubus do governo americano resolverem derrubar os servidores do The Pirate Bay, milhares de outras pessoas no mundo terão cópias do site e estarão aptas a manter viva nossa liberdade de trocar informação. O único problema é que muitas pessoas ainda não sabem como ler os dados baixados. Aqui vai uma singela contribuição de como fazer para usar os dados baixados e ativar os magnet links lá contidos:

**Step by step**

A primeira coisa que você deve fazer é baixar o site através deste [endereço](https://thepiratebay.se/torrent/7016365) (há a opção de magnet links ou torrents ainda, mas não por muito tempo).

Feito isso abra o arquivo que você baixou (.gz). Você vai encontrar listas de dados (hashes) que estão neste [formato](http://i.imgur.com/4jUUn.png). É aconselhável usar um bom editor de texto para que as infindáveis linhas não quebrem. Recomendo o [gVim](http://www.vim.org/download.php).

Repare que a informação está dividida no seguinte padrão: TPBID|TorrentName|SizeInBytes|Seeders|Leachers|MagnetLinkHash

O que você deve fazer é selecionar o arquivo que quer baixar ou compartilhar e copiar o hash deste, p.ex.:

5316391aed813d4283178dce2b95c8ad56c5be72

Na frente do hash inclua o prefixo magnet:

magnet:?xt=urn:btih:

O resultado final é:

magnet:?xt=urn:btih:5316391aed813d4283178dce2b95c8ad56c5be72

Cole no seu browser favorito (que não seja o internet explorer, putaqueopariu), aperte enter e o seu cliente bittorrent vai abrir como uma flor. Bom compartilhamento!

**Links úteis:**

magnet link do The Pirate Bay (90Mb) – magnet:?xt=urn:btih:938802790a385c49307f34cca4c30f80b03df59c

magnet link do Bitsnoop (500Mb – 17 milhões de arquivos) – magnet:?xt=urn:btih:F5615DFB80AC995787C1B2219A75DF7805278DEA

[gVim](http://www.vim.org/download.php)

[7zip](http://www.7-zip.org/) – para abrir arquivos .gz
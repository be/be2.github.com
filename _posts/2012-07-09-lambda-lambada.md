---
layout: post
title: "Lambda lambada"
description: "Meus problemas sempre foram peculiares, de acreditar demais na força da correspondência e não compreender plenamente as objeções."
category: philosophy
tags: [logica denotacional, correspondence, functions, lambda calculus]
---
{% include JB/setup %}

Vamos ver se rola, provavelmente não me expressarei bem neste primeiro momento. Eu tenho problemas com algumas características da "correspondence theory of truth", traduza como quiser, é sempre uma bosta fazer isso, apesar de necessário. Meus problemas sempre foram peculiares, de acreditar demais na força da correspondência e não compreender plenamente as objeções. P.ex., você pega o [artigo](http://plato.stanford.edu/entries/truth-correspondence) da SEP e lá há 3 objeções: 

(1): 

>"Although they apply to truths from some domains of discourse, e.g., the domain of science, they fail for others, e.g. the domain of morality: there are no moral facts." 

Talvez seja a melhor das objeções, mas não ganha força se conseguimos um mínimo de tradução, vamos falar disso mais tarde. (2):
 
>"Correspondence theories are too obvious; they are trivial, vacuous, engaging in mere platitudes." 

Essa acho fraca, óbvio é a minha língua seca depois de uma sexta à noite. E (3):
 
>"Correspondence theories are too obscure."

Óbvio ou obscuro? Bom, o problema é um clássico, mas acho que está longe de bem definido. A melhor objeção é:

>"In a nutshell, the objection is that a correspondence theory of truth must inevitably lead into skepticism about the external world because the required correspondence between our thoughts and reality is not ascertainable. Ever since Berkeley’s attack on the representational theory of the mind, objections of this sort have enjoyed considerable popularity. It is typically pointed out that we cannot step outside our own minds to compare our thoughts with mind-independent reality. Yet—so the objection continues—on the correspondence theory of truth, this is precisely what we would have to do to gain knowledge. We would have to access reality as it is in itself, independently of our cognition of it, and determine whether our thoughts correspond to it. Since this is impossible, since all our access to the world is mediated by our cognition, the correspondence theory makes knowledge impossible (cf. Kant 1800, intro vii). Assuming that the resulting skepticism is unacceptable, the correspondence theory has to be rejected.” 

Bom, não sei, sinceramente, se isso funciona se você é um ficcionalista ou funcionalista (vários tipos) e consegue computar proposições de vários domínios em diferentes modos obtendo os mesmos resultados, como fazemos habitualmente. Ainda há correspondência, apesar de "pensarmos" de modo diferente, com diferentes tipos de computação, métodos, caminhos, sei lá. Apesar do ataque externalista, há uma dimensão interna que resolve problemas e cospe resultados - "é isto, não aquilo". Não compreendo, em última instância, como isso não é correspondência, p.ex., quando comparados determinados conceitos admitimos que este faz parte de um grupo A e não de outro B, apelando para a nossa memória ao compararmos os dados, da percepção externa, imaginação, computações, etc. IMHO, o máximo a que chega tal objeção é dizer que estávamos enganados porque não era ouro e sim ourina, o que só um especialista (e aí externalistas e ficcionalistas se amam) dirá se é verdadeiro, mas para ambos, num primeiro momento, é ouro. A objeção parece levar a um caminho obtuso que nos informa que ninguém está de posse de uma verdade que "corresponde" à realidade, só diz que a realidade é uma puta louca. OK, *we get it*, mas corresponde em vários domínios do que percebemos como realidade, não? Amigos, muy amigos(?) já disseram que é um erro categórico, pois o correspondentismo diz sobre a realidade ela mesma, wtf? Não sei o que é isso. Será que estou meramente *begging the question*? Ora, se adotarmos o mínimo de humildade científico-filosófica nos resta o quê então, falar sobre uma realidade inalcansável? Isso parece bem tosco. Há algum tipo de correspondência, afirmo, e ela não é tão obscura como diz (3). 

Vamos explorar um pouco mais o lado técnico e pegar como exemplo a semântica denotacional. Do ponto de vista da ciência da computação são adotadas algumas suposições quando pensamos na semântica denotacional como ferramentas para compreensão de ontologias de linguagens de programação: *Composicionalidade*, *extensionalidade* e completude. Não falaremos da última, mas as duas primeiras características são importantes para fazer vale o argumento deste post. 

A composicionalidade diz que o significado de uma expressão complexa é sistematicamente arregimentado através dos significados de suas partes. Em semântica denotacional funções são definidas via recursão da estrutura sintática da linguagem, noção amplamente incontroversa. Já a extensionalidade está relacionada primariamente à interpretação de programas, e acho que aqui pode haver confusão. Dois programas são iguais se e somente se suas denotações são as mesmas. Isso significa que sua igualdade é dada em termos das funções que computam. Isso é aplicado em semântica denotacional fazendo as denotações de programas serem funções de conjuntos (set theoretic functions), como indicado anteriormente. E é aí que reside a possibilidade de tradução entre domínios que modelam estruturas. 

Numa semântica de conjuntos cada dado ou controle (programação) é compreendido como denotando um objeto matemático de algum tipo, e é claro, como a nossa semântica é de conjuntos tal abordagem indica que o substrato matemático é em última instância constituído por conjuntos, ora bolas. 

Usar linguagens de programação como indicador de correspondência não é uma escolha aleatória, tampouco fruto de capricho. Elas estão no meio do caminho entre as linguagens da lógica matemática e a linguagem natural. Nem mesmo a PROLOG pode ser explicitamente traduzida em linguagem puramente lógica, o que torna o exemplo das linguagens de programação muito interessante. Justamente por estarem distantes da pureza lógica e igualmente distantes da linguagem natural é que as linguagens de programação devem ser semanticamente investigadas com a estratégia denotacional. É claro que um problema a ser resolvido é o clássico: fornecer denotações para programas recursivos que são definidos em termos de si próprios, p.ex. a função de fatorial:

    factorial ≡ λ(n) if (n==0) then 1 else n*factorial(n-1) 

Mas a solução está na raiz do *lambda calculus* ele mesmo (oh coisinha recursiva do pai). A solução consiste em construir o denotação por aproximação começando com o conjunto vazio de pares ordenados (o que, em teoria dos conjuntos seria escrito como {}). Se {} está conectado à definição acima de fatorial, em seguida, a denotação é {[0 1]}, que é uma melhor aproximação do fatorial. Iteração: Se {[0 1]} está conectado à definição, em seguida, a denotação é {[0 1] [1 1]}. Por isso, é conveniente pensar em uma aproximação para factorial como uma entrada *F* da seguinte maneira:

- *F*^0 ({}) é a função parcial indefinida {};

- *F*^1 ({}) é a função {[0 1]} que é definido em 0, para ser 1, e indefinido noutro local;

- *F*^5 ({}) é a função {[0 1] [1 1] [2 2] [3 6] [4 24]}.

Aonde *F*^i indica as implicações [*i*-many](http://en.wikipedia.org/wiki/Iterated_function) de *F*

Pode ser que automaticamente esteja aderindo à uma espécie de [realismo estrutural](http://plato.stanford.edu/entries/structural-realism/).

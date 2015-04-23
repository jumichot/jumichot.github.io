---
layout: post
title: "Meetup Vim Avril 2015"
date: "2015-04-21 19:00:00 +0200"
---


Seconde participation au meetup Vim organisé par Silex Labs([@silexlabs](https://twitter.com/silexlabs)) hébergé chez Mediabox.
Il y avait beaucoup plus de participants que la première fois où je suis venu, ce qui nous poussé à changer de salle
après le premier talk pour être un peu moins à l'étroit.

![Atelier vim chez Media Box](/images/posts/meetups/vim-7/atelier-vim-silex-labs.png)

David Foucher ([@tyjak](https://twitter.com/tyjak)), utilisateur de Vim de puis 8 ans, a commencé par une présentation
du meetup et du programme de la soirée.

Comme à chaque session un compte rendu [est disponible](https://gist.github.com/tyjak/138bf649176f4d99659d).

## Actualités Vim

Concernant les actualités liées à Vim, avec la fermeture prochaine de Google code, les sources de Vim ont été déplacées 
sur [Github](https://github.com/vim/vim).

David a également évoqué [cet article](http://schier.co/blog/2015/04/19/switching-from-vim-to-intellij.html) d'une personne
ayant basculé de Vim vers IntelliJ. Visiblement cette personne devait écrire du java, le changement d'IDE a donc était un peu subi.
L'auteur montre qu'avec un plugin nommé IdeaVim on est capable d'émuler certaines fonctionnalités de Vim, la transition
n'est pas trop douloureuse. Ce plugin est aussi capable de lire le .vimrc et de récupérer une partie de ses
configurations.

## Les ressources pour bien débuter
![Vim pour les humains](/images/posts/meetups/vim-7/vim-pour-les-humains.png)

Il y avait quelques débutants dans la salle, nous avons donc eu l'occasion de revoir les plugins de base à avoir dans
une configuration basique :

- [NERDTree](https://github.com/scrooloose/nerdtree) : pour voir la hiérarchie de fichier
- [CtrlP](https://github.com/kien/ctrlp.vim) : pour ouvrir rapidement des fichiers
- [NeoBundle](https://github.com/Shougo/neobundle.vim) et [Vundle](https://github.com/gmarik/Vundle.vim) : pour gérer
l'installation de ses plugins

Nous avons parlé différentes ressources pour monter rapidement en compétences.

Les formations interactive :

- le traditionnel vimtutor (commande à taper dans un terminal)
- [Vim Genius](http://www.vimgenius.com/)
- [Vim Adventures](http://vim-adventures.com/)

Une réponse stackoverflow : [Your problem with Vim is that you don't grok vi](http://stackoverflow.com/questions/1218390/what-is-your-most-productive-shortcut-with-vim)

Et enfin un très bon livre que je recommande fortement : [Vim pour les humains](https://vimebook.com/). Il se lit rapidement,
et contient l'essentiel pour construire soi-même un environnement proche de celui offert par Sublime Text.
Le livre à aussi l'avantage d'être à prix libre, vous mettez ce que vous voulez.

## Les autres ressources évoquées

### Les plugins

- [Vim GitGutter](https://github.com/airblade/vim-gitgutter) : montre les changements effectués (git diff) sur le fichier avec un
icône à gauche du numéro de ligne

  ![Vim GitGutter](/images/posts/meetups/vim-7/git-gutter.png)

- [Gist.vim](https://github.com/mattn/gist-vim) : permet de manipuler facilement depuis Vim ses Gists hébergés sur
Github

- [Vim wiki](https://github.com/vimwiki/vimwiki) : permet d'avoir un wiki avec des fichiers textes pour organiser ses
idées, ses todo lists...

  ![Vim wiki](/images/posts/meetups/vim-7/vimwiki.png)

- [calendar-vim](https://github.com/mattn/calendar-vim) : plugin affichant un calendrier pour créer des entrées dans
vim wiki

- [vim-startify](https://github.com/mhinz/vim-startify) : change l'écran d'accueil par défaut et propose à la place des
raccourci pour ouvrir les derniers fichiers/sessions utilisés.

  ![vim-startify](/images/posts/meetups/vim-7/vimstartify.png)

- [scratch.vim](https://github.com/mtth/scratch.vim) : un plugin pour prendre facilement des notes temporaires.
Selon David qui a testé, le plugin n'est pas idéal. Il ne synchronise pas les notes si on lance plusieurs session Vim différentes.

  ![scratch.vim](/images/posts/meetups/vim-7/vimscratch.png)

  Personnellement pour le moment j'utilise la méthode de Ben Orenstein dans ses [dotfiles](https://github.com/r00k/dotfiles/blob/master/vimrc) qui
  consiste simplement à avoir un raccourci vers un fichier Dropbox :

  {% highlight vim %}
    map <Leader>cn :e ~/Dropbox/notes/coding-notes.txt<cr>
  {% endhighlight %}

- [Asciidoc](https://github.com/dagwieers/asciidoc-vim) pour formater ses documents

- [Endwise](https://github.com/tpope/vim-endwise) pour les rubyistes pour terminer automatiquement id, do, def

### Les autres astuces

{% highlight vim %}
:map
{% endhighlight %}
Permet de voir tous ses raccourcis clavier

{% highlight vim %}
nmap <silent> <leader>se :set spelllang=en spell!<CR>
nmap <silent> <leader>sf :set spelllang=fr spell!<CR>
{% endhighlight %}
Permet d'activer la validation orthographique lors de la rédaction d'articles par exemple

{% highlight vim %}
:.w !cat - >> file.txt
{% endhighlight %}
Permet d'envoyer la ligne sous le curseur dans un autre fichier

{% highlight vim %}
:mksession testsession
:source testsession
{% endhighlight %}
Vim a un gestionnaire de session assez peu connu. David a fait une petite démo est ça à l'air intéressant si on
travaille souvent dans le même environnement, avec la même disposition de fenêtre par exemple. Plus d'info via `:help
:mksession`.

{% highlight vim %}
:reg
{% endhighlight %}
Permet de voir les registres. Les registres sont une sorte de clipboards plus évolués, on peut copier coller dans
différents registres. C'est une fonctionnalité que j'utilise assez peu vu que je me sers de [ClipMenu](http://www.clipmenu.com/)
mais ça à l'air vraiment intéressant.

{% highlight vim %}
autocmd BufWritePost $MYVIMRC so $MYVIMRC
{% endhighlight %}
Permet de recharger la configuration Vim automatiquement lorsqu'on la modifie.

## Conclusion
C'était encore un meetup enrichissant, j'ai passé une bonne soirée. Comme d'habitude je repars avec tout un tas de plugins à tester.

Voici quelques liens récapitulatifs :

 - la page officielle du [meetup](http://www.meetup.com/Vim-Paris/)
 - Tuppervim : un autre [événement](http://www.tuppervim.org/) sur Vim chez Mozilla
 - la configuration Vim de [David](https://github.com/tyjak/vim-config/blob/master/.vimrc), [Thomas](https://github.com/boubz/dotfiles), et la [mienne](https://github.com/jumichot/dotfiles/blob/master/vimrc)

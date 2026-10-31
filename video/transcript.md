# Transcription de la vidéo de démo

Bonjour , donc je vais vous présenter mon projet N810 en deux grandes soirées. Alors tout d'abord, je vais vous présenter
mon workflow que vous pouvez voir ici. Son objectif et ses différentes grandes étapes. Et ensuite, je vous présenterai
différentes commandes N810 CLI que je vais exécuter dans mon terminal. Alors concernant mon workflow, son objectif
c'était de trier les mails de ma boîte Gmail personnelle et de les ajouter à différentes libellés, mais également de
m'envoyer le mail récap des différents tris qui ont été effectués au cours de la semaine. Alors concernant l'architecture
de mon workflow, elle se distingue en deux grandes parties. La première partie ici qui correspond au tri et la deuxième
partie en dessous qui correspond à la zone récap. Concernant la zone tri, on peut voir que j'ai le noeud d'entrée qui est le
noeud nouveau mail, donc qui prend mes nouveaux mails de la semaine. Mais au-dessus, j'ai également un nœud
manuel qui récupère mes anciens mails. Alors, j'ai ces deux nœuds d'entrée par rapport à mes mails qui vont
directement être triés par une IA pour ce nœud-là qui est l'IA GEV via OpenRouter . Cette IA, elle prend donc tous mes
différents mails, puis elle va les trier et les mettre dans les différentes catégories, donc dans les différentes libellés qui
sont créés sur ma boîte Gmail. Si jamais GEV, plant, bug ou qu'importe la raison, j'ai une IA de secours qui est l'IA GEMI
que j'ai notamment fait avec un prompt que vous pouvez voir juste ici. Et le dernier point que je peux ajouter sur cette
partie de tri, c'est que donc ici, on peut voir la catégorie, enfin le noeud catégorie selon à quelle catégorie l'IA va mettre
mes mails, mais j'ai également le libellé à vérifier . Donc si jamais l'IA ne trouve pas la catégorie correspondante qui va
donc directement dans le noeud après ajouter le libellé, elle va la mettre dans le libellé à vérifier . Donc voilà pour cette
partie de tri. Ensuite, pour la soirée récap du dimanche, donc tous les dimanches à 19h, comme on peut le voir ici sur ce
nœud, c'est bien déterminé. Dimanche à 19h. Il y a tous ces différents types de mails qui vont être pris en compte, donc
les mails de la semaine, les importants non lus, les à vérifier et également les pubs avec leur lien des abonnements.
Grâce à ces différents mails qui vont être pris, ça va construire un récap, puis me l'envoyer . Un autre point important de
cette partie, c'est que dans le récapitulatif et dans le tri qui a été effectué de la semaine, on va prendre tous mes mails,
pubs et connexions et me les mettre à la corbeille. Pour vous prouver le bon fonctionnement de mon workflow, je peux
vous le montrer ici. Donc voilà, ici, vous pouvez voir les différentes libellés qui ont été créés, notamment avec le libellé à
vérifier . Comme vous pouvez voir , pas mal de mails qui ont été ajoutés. Je peux également vous montrer un mail
récapitulatif qui m'a été envoyé lorsque j'ai fait un test tout à l'heure. Donc voilà, ils disent bonjour avec mon prénom. J'ai
le nombre de mails reçus dans la semaine, les différentes libellés correspondant aux mails ont été ajoutés, le récap sur
les mails importants non lus, sur les mails à vérifier , le libellé que je vous ai montré juste avant, et sur les mails pubs avec
les liens de désabonnement, ce qui était une partie très importante de mon workflow. Et pour vous montrer , on peut voir
ici que dans le libellé pub, je n'en ai plus aucun, et qu'ils ont tous été ajoutés à ma corbeille, comme ici. Voilà. Pour vous
montrer , je vous montre les différentes exécutions sur mon workflow. Donc voilà, ici, la première, c'est l'exécution du
récap, du mail récap. Ici, c'était l'exécution pour les nouveaux mails, et ici, l'exécution pour le rattrapage des anciens
mails. Alors, maintenant, je vais vous présenter l'outil N8N CLI, qui est un outil en ligne de commande qui fait le lien
entre mon N8N et les différents fichiers type script. La première commande que je peux vous présenter , c'est le test N8N
CLI. Donc ça, ça teste les différents... Ah, pardon, je me trompe, j'ai évoqué. Ah, voilà. Bah non. Alors, pardon, j'avais
oublié de mettre le env test, mais du coup, cette commande, elle teste les différents moyens de connexion à mon D8N.
On peut voir qu'ici, moi, mon mode de connexion, ça a été via le serveur MCP, et non le REST API et Database, qui ne
sont pas configurés, mais qui sont également mis en optionnel. Une commande différente... Enfin, une autre
commande, pardon, que je peux vous montrer , c'est la commande statut, qui est celle-ci compare mes fichiers locaux à la
dernière synchronisation. Donc voilà, ici, on peut voir le résultat. Ça indique que tout est à jour et que je n'ai rien à
envoyer ni à récupérer . Une autre commande que je peux vous montrer , c'est Folders List. Alors, celle-ci, elle liste les
différents projets de... Les différents dossiers, pardon, dans mon projet N8N. Donc, on peut voir que j'en ai bien quatre,
Templates, Sandbox, Utils et Project. C'est une autre commande que je pourrais vous montrer . C'est la commande Valider .
Alors, il faut... Ça prend un peu plus de temps que les autres. C'était... Donc, Sandbox qui est un de mes dossiers. Alors,
par contre, j'ai juste oublié... Ah non, c'est bon, je l'ai bien mise. Tri, Gmail et Récap. Donc là, je mets le nom de mon
workflow... Qui m'intéresse. Workflow.ts Ah, oui. Alors, ici... Oh, pardon. Je me suis encore trompée. Validez, N1, Tri,
Gmail. Ah, petite erreur là. Très bien, voilà. Donc, cette fois-ci, ça a marché. Ça, ça vérifie que la structure de mon projet
est bonne. Donc, ça met bien le petit mot Valid. Donc, par rapport à ce fichier-là. Et une dernière que je pourrais vous
montrer . Alors, pareil, je reprends le nom de mon workflow qui m'intéresse. Mais cette fois-ci, je vais vous montrer avec
la commande Diff. Ok, je ne vais pas faire comme ça parce que ça bug. C'est un petit peu long. Donc, je suis désolée. Je
vais juste mettre pause le temps de tout copieur . Voilà. Donc, je l'ai bien copié. Voilà. D'accord. Donc, j'ai le résultat. Alors,
cette commande, elle compare mon fichier local à la version qui est dans le N8N. Donc, ici, on peut voir qu'il n'y a aucune
différence trouvée. Donc, il n’y a aucune différence entre les deux. Tout est bon. Rien à modifier . Rien à envoyer . Donc
voilà. C'était les différentes commandes N8N CLI que je voulais vous montrer qui peuvent m'aider pour avoir certaines
informations par rapport à mes fichiers. Voir si tout est correct, etc. Et je finis juste ma vidéo avec un petit feedback sur
le cours qu'on a eu avec vous durant la semaine. Moi, ce que j'ai apprécié dans ce cours, c'est qu'on a directement pu
utiliser l'outil et du coup voir directement. Mais en même temps, ça a été un peu compliqué parce qu'on ne connaît pas
du tout ça avant. Et je crois que j'aurais peut-être préféré avoir un cours théorique d'une journée entière sur les
différentes commandes N8N CLI, le workflow, les nodes, etc. Mais vraiment, enfin, je sais que ça aurait été condensé
mais que du coup, une fois qu'on utilise l'outil, on sait un peu là où on met les pieds, etc. J'arrive que ça m'a pas mal
bugué. Donc, moi, je suis repassée sur Cloud Code mais en soi, j'ai quand même bien aimé le cours. Donc voilà, j'ai
beaucoup aimé faire un workflow. En plus, c'était utile. Donc, ça, c'était cool. Et voilà, c'est tout pour ma vidéo. Je suis
désolée pour les petits moments de pause que j'ai eu dans les commandes N8N CLI. Je voulais pas faire perdre trop de
temps. Et voilà, merci beaucoup de m'avoir écouté et bonne soirée.

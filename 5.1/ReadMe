Explication des codes du TF-IDF

On va utiliser trois Map-Reduce de suite pour sortir le TFIDF :
  - Le premier tour de MAPReduce (FirstTask) va nous permettre de donner le nombre d'occurence de chaque mot dans chaque document. 
  On retire la ponctuation. De plus, pour bien differencier les deux documents, chacun a son propre Mapper via MultipleInputs.addInputPath.
  Par contre il y a un seul driver et un seul reducer
  Le outout de ce premier map reduce est (on prend deux lignes en exemple ):
  
youth@callwild	2
youth@defoerobinson103	1
  
  - Dans ce deuxieme tour de MapReduce (SecondTask), on sort la frequence de chaque mot dans chaque document i.e. le nombre d'occurence du mot
  dans un document par rapport au nombre de mots de ce document. Le input est le txt sorti dans le MapReduce precedent.
  Le output sera un txt :
clapping@callwild	1/122353
busied@callwild	1/122353
attended@defoerobinson103	1/32461
yukon@defoerobinson103	7/32461

  
  - Dans le troisieme tour de MapReduce (DerniereTache), on calcule le TF-IDF final. On commence par voir dans combien de document un mot est present
  (soit 1 soit 2).Dans notre reducuer nous considerons que si le mot  est present dans tous les documents, on remplace le "log(1)" par 1 tout simplement 
  sinon on aurait un TF-IDF de 0 pour ces mots. On peut alors sortir le TF et le IDF puis le TF-IDF.
  les 20 mots avec les plus grands TF-IDF sont :
  
the	in	defoerobinson103	TF	IDF	is	0.07017652
the	in	callwild	TF	IDF	is	0.048196611
and	in	defoerobinson103	TF	IDF	is	0.047195096
i	in	callwild	TF	IDF	is	0.042099499
and	in	callwild	TF	IDF	is	0.039353346
to	in	callwild	TF	IDF	is	0.035234118
of	in	callwild	TF	IDF	is	0.028859121
of	in	defoerobinson103	TF	IDF	is	0.026863005
he	in	defoerobinson103	TF	IDF	is	0.025107052
was	in	defoerobinson103	TF	IDF	is	0.021410308
to	in	defoerobinson103	TF	IDF	is	0.020794184
a	in	defoerobinson103	TF	IDF	is	0.020332091
a	in	callwild	TF	IDF	is	0.018634606
my	in	callwild	TF	IDF	is	0.017506722
his	in	defoerobinson103	TF	IDF	is	0.017282277
in	in	defoerobinson103	TF	IDF	is	0.016604541
was	in	callwild	TF	IDF	is	0.016476915
in	in	callwild	TF	IDF	is	0.015831242
that	in	callwild	TF	IDF	is	0.015447108
it	in	callwild	TF	IDF	is	0.01507932

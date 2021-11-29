Spring Cloud Gateway:
---------------------------
Gateway est une Api qui permet d'orchestrer et dispose de fonctionnalité de sécurité et monitoring.
Api Gateway dispose de plusieurs implémentations comme Zuul(Qui est un proxy utilisant des entrées sorties bloquantes et Spring Cloud Gateway(Proxy utilisant des entrées sorties 
non bloquantes).

Dans notre projet on optera pour la configuration d'un spring cloud gateway qui est plus performant et scalable(Montée en charge), vu la disponibilité permanentes des threads pour traitement
de requetes entrantes, ces derniers sont traitée en background de manières asynchrones, une fois le traitement est achevé la requete est renvoyé.
Les requetes sont toujours traités sauf saturation de mémoire et CPU.

---------------------------
Cas 1 : Utilisation d'un fichier application.yml
----
A)
Dans ce fichier yml on mentionne la route vers laquelle nous voulons qu'une requete soit destinée:
-Uri de destination.
-Predicate(Condtion).
-Filters(Optionel).

B)Au niveau du main, nous utilisons la méthode RouteLocator qui éxecute à l'aide de l'annotation @Bean

---------------------------
Cas 2 : Utilisation d'un fichier application.properties
----
Sur ce fichier on mentienne : 
-Le port du server(8888).
-Le nom de la Gateway.
-Activation du discovery(true).

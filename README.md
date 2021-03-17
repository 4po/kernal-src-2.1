# kernal-src-2.1
Spark est un système de calcul en cluster rapide et général pour le Big Data. Rewrite par 4po.

# Apache Spark

Spark est un système de calcul en cluster rapide et général pour le Big Data. Il fournit
API de haut niveau en Scala, Java, Python et R, et un moteur optimisé qui prend en charge les
supporte des graphes de calcul généraux pour l'analyse des données. Il prend également en charge un
Il prend également en charge un riche ensemble d'outils de niveau supérieur, notamment Spark SQL pour SQL et DataFrames,
MLlib pour l'apprentissage automatique, GraphX pour le traitement des graphes,
et Spark Streaming pour le traitement des flux.

<http://spark.apache.org/>


## Documentation en ligne

Vous pouvez trouver la dernière documentation Spark, y compris un guide de programmation.
guide de programmation, sur la [page web du projet](http://spark.apache.org/documentation.html).
Ce fichier README ne contient que des instructions de configuration de base.

## Construction de Spark

Spark est construit à l'aide de [Apache Maven] (http://maven.apache.org/).
Pour construire Spark et ses programmes d'exemple, exécutez :

    build/mvn -DskipTests clean package

(Vous n'avez pas besoin de faire cela si vous avez téléchargé un paquet pré-construit).

Vous pouvez construire Spark en utilisant plus d'un thread en utilisant l'option -T avec Maven, voir ["Parallel builds in Maven 3"](https://cwiki.apache.org/confluence/display/MAVEN/Parallel+builds+in+Maven+3).
Une documentation plus détaillée est disponible sur le site du projet, à l'adresse suivante
["Building Spark"](http://spark.apache.org/docs/latest/building-spark.html).

Pour des conseils généraux de développement, y compris des informations sur le développement de Spark à l'aide d'un IDE, voir 
http://spark.apache.org/developer-tools.html](la page Outils de développement utiles).

## Shell Scala interactif

La façon la plus simple de commencer à utiliser Spark est d'utiliser le shell Scala :

    ./bin/spark-shell

Essayez la commande suivante, qui devrait retourner 1000 :

    scala> sc.parallelize(1 to 1000).count()

## Shell Python interactif

Alternativement, si vous préférez Python, vous pouvez utiliser le shell Python :

    ./bin/pyspark

Et exécuter la commande suivante, qui devrait également retourner 1000 :

    >>> sc.parallelize(range(1000)).count()

## Programmes d'exemple

Spark est également livré avec plusieurs exemples de programmes dans le répertoire `examples`.
Pour exécuter l'un d'eux, utilisez `./bin/run-example <class>[params]`. Par exemple :

    ./bin/run-example SparkPi

exécutera l'exemple Pi localement.

Vous pouvez définir la variable d'environnement MASTER lors de l'exécution des exemples pour soumettre des exemples à un cluster.
exemples à un cluster. Il peut s'agir d'une URL mesos:// ou spark://,
"yarn" pour exécuter sur YARN, et "local" pour exécuter
local avec un thread, ou "local[N]" pour exécuter localement avec N threads. Vous pouvez utiliser
Vous pouvez également utiliser un nom de classe abrégé si la classe se trouve dans le paquet
est utilisé. Par exemple

    MASTER=spark://host:7077 ./bin/run-example SparkPi

La plupart des programmes d'exemple affichent une aide à l'utilisation si aucun paramètre n'est fourni.

## Exécution des tests

Pour effectuer des tests, il faut d'abord [construire Spark] (#building-spark). Une fois que Spark est construit, les tests
peuvent être exécutés en utilisant :

    ./dev/run-tests

Veuillez consulter les conseils sur la façon de
exécuter des tests pour un module ou des tests individuels](http://spark.apache.org/developer-tools.html#individual-tests).

## Note sur les versions d'Hadoop

Spark utilise la bibliothèque centrale d'Hadoop pour communiquer avec HDFS et d'autres systèmes de
systèmes de stockage supportés par Hadoop. Comme les protocoles ont changé dans les différentes versions de
Hadoop, vous devez construire Spark avec la même version que celle utilisée par votre cluster.

Veuillez consulter la documentation sur la construction à l'adresse
["Spécification de la version d'Hadoop"](http://spark.apache.org/docs/latest/building-spark.html#specifying-the-hadoop-version)
pour des conseils détaillés sur la construction pour une distribution particulière d'Hadoop, y compris
la construction pour des distributions particulières de Hive et Hive Thriftserver.

## Configuration

Veuillez consulter le [Guide de configuration](http://spark.apache.org/docs/latest/configuration.html)
dans la documentation en ligne pour un aperçu de la façon de configurer Spark.

## Contribuer

Veuillez consulter le [Guide de contribution à Spark](http://spark.apache.org/contributing.html)
pour des informations sur la façon de commencer à contribuer au projet.


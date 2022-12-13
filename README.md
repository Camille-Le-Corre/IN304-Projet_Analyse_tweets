# Projet IN304 - InPoDa
# Collecte, traitement et analyse de données de réseaux sociaux


### LE CORRE Camille
### LEFEVRE Laura
### LDD BI


## Présentation du projet :

Ce projet a pour objectif d'analyser des données issues de réseaux sociaux. Ici, nous travaillons sur des tweets.
Notre programme représente une plateforme fictive nommée InPoDa.
Dans un premier temps, le prinicipe consiste à récupérer les tweets issus d'un fichier json (nous avons à disposition le fichier versailles_tweets_100.json par exemple). Ceux-ci vont être manipulés, triés et nettoyés, pour faciliter leur utilisation lors de la suite du projet.
Une fois les données nettoyées, nous allons pouvoir les analyser. Les différentes fonctionnalités d'analyse possibles par InPoDa seront détaillées plus tard.

## Présentation d'un tweet :

Un tweet est une publication sur la plateforme Twitter. Chaque utilisateur peut publier un tweet. Il s'agit d'un texte, qui peut être accompagné de mentions d'autres utilisateurs (en utilisant le symbole '@') ou de hashtags (avec le symbole '#'). 


## Traitement des tweets

Comme décrit précédemment, nous récupérons les tweets d'un fichier json. Ce fichier est une liste de dictionnaires, où chaque dictionnaire représente un tweet. Dans chaque tweet, nous pouvons retrouver des informations comme son auteur, son texte, les hashtags utilisés, les mentions, etc.

La première étape consiste à créer un fichier zone_atterrissage.json, qui comprend les mêmes données que le fichier source, à la seule différence que les textes des tweets ont été nettoyés. En effet, nous appliquons aux textes un certain nombre de filtres, permettant de supprimer tous les caractères spéciaux, les emojis, etc.

Ensuite, notre but est de transformer le fichier json en un DataFrame de tweets (à l'aide de la librairie pandas), en ne gardant uniquement que les informations qui nous seront utiles lors de l'analyse des données. Chaque ligne du DataFrame correspond à un tweet, et les colonnes représentent les informations que nous avons sur ces tweets, telles que son auteur, son texte, le ou les hashtag(s), le ou les utilisateur(s) mentioné(s), le topic et le sentiment du tweet. Le topic du tweet lui est attribué aléatoirement à partir d'une liste de topics pré-établie. Son sentiment (positif, neutre ou négatif) est donné grâce à la librairie textBlob, qui analyse des mots-clé du texte du tweet.

## Analyse des tweets

Maintenant que nous avons notre DataFrame, nous allons pouvoir analyser nos tweets.
Voici les fonctionnalités proposées par InPoDa :

- Obtenir le Top k des hashtags, des utilisateurs, des utilisateurs mentionnés ou bien des topics (k est un paramètre choisi par l'utilisateur ). Par exemple, le Top 3 hashtags retournera les 3 hashtags les plus utilisés dans les tweets.

- Afficher des diagrammes du nombre de publications par utilisateur, par hashtag ou pas topics (en utilisant la librairie matplotlib).

- Obtenir l'ensemble des tweets d'un utilisateur spécifique, ou bien mentionnant un utilisateur spécifique.

- Obtenir les utilisateurs mentionnant un hashtag spécifique ou mentionnés par un utilisateur spécifique.
# Au Fournil du Sud — site archivé

Ce site a été regroupé avec les deux autres boulangeries sur
**[mkboulangeries.fr](https://mkboulangeries.fr)**.

Le dépôt ne sert plus qu'à rediriger l'ancienne adresse vers la page de la
boulangerie : `https://mkboulangeries.fr/au-fournil-du-sud`.

La redirection est un **308 permanent** défini dans `vercel.json`. C'est
elle qui transmet à la nouvelle page le référencement déjà acquis, et qui
évite que Google voie deux fois le même contenu sans savoir lequel classer.

`src/pages/index.astro` n'est qu'un filet de sécurité : une page servie
uniquement si la redirection d'hébergement ne s'applique pas, pour ne
jamais laisser un visiteur dans le vide.

Le contenu et l'historique de l'ancien site restent dans l'historique git.

**Le code du site vivant est dans le dépôt `site-vitrine-mk`.**

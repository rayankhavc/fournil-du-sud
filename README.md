# Au Fournil du Sud, ancien site

Ce dépôt ne sert plus qu'à rediriger. Le site des trois boulangeries a été
regroupé sur un domaine unique (dépôt `site-vitrine-mk`), et la page de cette
boutique y vit désormais :

<https://maisonkhalifa.vercel.app/au-fournil-du-sud>

## Pourquoi une redirection plutôt qu'une suppression

Tant que cette adresse répondait, deux sites servaient le même contenu pour
les mêmes recherches locales. Google n'en classe qu'un, et pas forcément le
bon : c'est exactement ce que le regroupement devait éviter.

Une redirection permanente (308) transfère le signal de l'ancienne adresse
vers la nouvelle. Une 307 dirait au contraire à Google de garder l'ancienne
URL en réserve, donc de la revérifier indéfiniment sans rien transférer.

Le code source du site reste en place, il n'est simplement plus servi :
toutes les URL, racine comprise, partent vers la nouvelle page. Les deux
règles de `vercel.json` sont nécessaires, `/:chemin+` exige au moins un
segment et ne couvre donc pas `/`.

## Le jour où le domaine définitif arrive

`mkboulangeries.fr` n'est pas encore réservé. Quand il le sera et qu'il
sera branché sur le projet Vercel du site MK, remplacer les deux
destinations de `vercel.json` par `https://mkboulangeries.fr/au-fournil-du-sud`,
pour éviter une redirection en deux temps.

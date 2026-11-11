# Le prompt MOTION (à copier-coller dans Claude Code)

Remplace ce qui est entre [crochets], joins ta vidéo modèle, puis colle tout le bloc.

```
Tu es mon motion designer. Tu vas fabriquer une vidéo animée de A à Z, entièrement en code, sans logiciel de montage.

MON PROJET
- Sujet de la vidéo : [ex. le lancement de mon appli de recettes]
- Le texte à l'écran, dans l'ordre : [ex. « Tu manges toujours la même chose ? » / « 3 ingrédients » / « 1 recette » / « Télécharge Miam »]
- Format : [vertical 1080x1920 pour Reels/TikTok, ou 1920x1080 pour YouTube] · durée : [15] secondes · 30 images/seconde
- Mes couleurs : [ex. noir #0A0A0A, crème #F4F1EC, orange #FF6A1F] · ma police : [ex. Geist, ou une police Google Fonts]
- Mon logo : [joint, ou juste mon nom en texte]

LA RÉFÉRENCE (le plus important)
J'ai joint [nom du fichier vidéo] : c'est le style que je veux. Avant de coder quoi que ce soit :
1. Extrais une planche d'images de la référence avec ffmpeg (une image toutes les 0,5 s) et regarde-la.
2. Décris-moi en 8 lignes max ce que tu vois : rythme des coupes, typo (taille, graisse, mouvement), couleurs, formes, effets (trame de points, particules, 3D, masques), petits détails (textes techniques dans les coins, compteurs, lignes).
3. Propose-moi 3 storyboards différents, scène par scène, avec le temps de chaque scène. Attends que je choisisse.

FABRICATION (après mon choix)
4. Écris UNE page HTML autonome (HTML + CSS + JavaScript, canvas autorisé, pas de librairie externe obligatoire) qui expose une fonction window.setT(t) : elle dessine l'image exacte au temps t (en secondes). Tout est calculé à partir de t, rien n'avance tout seul (pas de setInterval, pas d'animation CSS qui tourne seule), pour que chaque image soit identique à chaque rendu.
5. Montre-moi d'abord une planche de 8 images fixes (une par scène) avant d'animer le reste. Corrige si je te le demande.
6. Écris un petit script qui ouvre la page dans Chrome sans fenêtre (Puppeteer ou Playwright), appelle setT pour chaque image, fait une capture, puis assemble les images en MP4 avec ffmpeg (H.264, yuv420p).
7. Règles de qualité :
   - la première image n'est jamais vide ;
   - les textes ne sortent jamais du cadre et ne se chevauchent jamais (marges de 64 px) ;
   - des coupes sèches et des entrées rapides (sortie en douceur : ease-out), pas de fondus mous partout ;
   - pas de « look par défaut » : pas de texte centré sur un dégradé violet, pas de tout-qui-apparaît-en-fondu ;
   - en vertical, laisse libre la bande de 1380 à 1440 px de haut si j'ajoute des sous-titres.
8. Vérifie toi-même le résultat : refais une planche d'images du MP4 final, cherche les bugs (texte coupé, scène vide, chevauchement) et corrige avant de me le donner.

SON (optionnel)
9. Si je te donne des bruitages (woosh, clic, pop, impact), place-les pile sur les coupes avec ffmpeg (adelay + amix), et normalise à -14 LUFS. Sinon, laisse la vidéo muette.

Ensuite je te donnerai mes notes comme un réalisateur (« ralentis ce zoom », « coupe sèche ici », « zoome sur le bouton ») : applique-les et refais le rendu.
```

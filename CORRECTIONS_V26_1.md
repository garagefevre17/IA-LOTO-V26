# V26.1 — Correctifs ciblés

- Lien visible vers le journal serveur V26 depuis l’accueil historique. Les moteurs V24/V25 restent indépendants : **aucune unification des données n’est revendiquée**.
- Affichage du journal V26 par `textContent` et création d’éléments DOM plutôt que `innerHTML` avec les données du flux (réduction du risque d’injection HTML).
- Comparaison des dates de prévisions selon le calendrier Europe/Paris côté navigateur.
- Contrôle du jour de calcul serveur avec le vrai fuseau Europe/Paris (y compris heure d’été), au lieu d’un UTC+1 fixe.
- Les garde-fous existants restent en place : source HTTPS auditée, 300 tirages minimum, aucun calcul rétroactif, pas de certification automatique.

## Limites
La source officielle FDJ et les secrets GitHub/Netlify restent à configurer. `v26-state.json` est toujours non configuré. Le journal V24 reste local et séparé. Aucun avantage prédictif démontré.

## Vérifications
`python -m unittest discover -s engine -p 'test_*.py'`
`node --check app.js` et `node --check ev.js` (si Node disponible).

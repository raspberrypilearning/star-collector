
--- question ---

---
legend: Question 3 sur 3
---

Un projet utilise cette ligne de code pour afficher des informations dans l'UI sur les étoiles collectées.

```
starText.SetText("Stars:" + stars);
```

Le GameObject texte a été correctement ajouté au script et le jeu est prêt à être testé.

![La vue Inspector affichant le texte a été connectée au script.](images/star-text-added.png)

Qu'est-ce que l'écran affichera une fois que le joueur a collecté une étoile et que la variable `stars` est définie sur `1`.

--- choices ---

- ( )

![La vue Scene avec un texte indiquant « Stars : 1 ».](images/stars-1.png)

  --- feedback ---

  Pas tout à fait. Regarde attentivement la chaîne de caractère dans le code.

  --- /feedback ---

- ( )

![La vue Scene avec un texte indiquant «"Stars :" + stars »](images/stars-full.png)

  --- feedback ---

  Pas tout à fait. Les lettres entre guillemets doubles `"` forment une chaîne de caractère. L'opérateur `+` joint des chaînes ensemble. Lorsque tu ajoutes `+` une variable à une chaîne, la valeur de la variable est ajoutée à la chaîne.

  --- /feedback ---

- (x)

![La vue Scene avec un texte indiquant « Stars : 1 ».](images/no-space.png)

  --- feedback ---

  Oui. Il n'y a pas d'espace après le `:` dans la chaîne de caractère du code, il n'y en aura donc pas dans le texte affiché.

  --- /feedback ---

- ( )

![La vue Scene sans texte.](images/no-text.png)

  --- feedback ---

  Non, il n'y a pas d'erreurs dans le code, donc le code affichera du texte dans l'UI de la scène.

  --- /feedback ---

--- /choices ---

--- /question ---

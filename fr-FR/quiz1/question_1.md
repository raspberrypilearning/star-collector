## Réflexion

Tu as réussi ! Tu as créé ton premier mini-jeu Unity et appris de nombreuses nouvelles compétences en cours de route.

Maintenant, il est temps de réfléchir - la réflexion est une partie importante de l'apprentissage, car elle aide à établir de nouvelles connexions dans ton cerveau.

Réponds aux trois questions ci-dessous pour réfléchir à ce que tu as appris.

Après chaque question, appuie sur Soumettre. Tu seras guidé vers la bonne réponse. Tu peux faire cette activité autant de fois que tu le souhaites.

--- question ---

---
legend: Question 1 sur 3
---

Un GameObject à collectionner a ce box collider configuré : ![Les limites du Box Collider dans la vue Scene.](images/star-collider.png) ![Les propriétés du composant Box Collider avec Box Collider activé et "Is Trigger" désactivé. Les coordonnées sont positionnées en fonction de l'objet à collectionner.](images/inspector-collider.png)

Et cette méthode `OnTriggerEnter` est dans un script qui est attaché au GameObject :

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

Le message de débogage « Collision detected » (Collision détectée) ne s'imprime pas lorsque le joueur entre en collision avec le GameObject à collectionner.

Comment pourrais-tu régler cela ?

--- choices ---

- ( ) Ajouter un composant Trigger au lieu d'un composant Box Collider

  --- feedback ---

Pas tout à fait. Pour créer un trigger, tu dois d'abord ajouter un collider.

  --- /feedback ---

- (x) Cocher la case "Is Trigger" pour transformer le collider en trigger

  --- feedback ---

  Oui. Cocher "Is Trigger" transforme un collider en trigger. Cela signifie que le `OnTriggerEnter` sera appelé lorsqu'une collision est détectée.

  --- /feedback ---

- ( ) Sélectionner la fenêtre de la console pour voir la sortie de débogage

  --- feedback ---

  Pas tout à fait, le message de débogage s'imprimera dans la fenêtre de la console même si la fenêtre n'est pas visible pour toi. La sortie apparaît également dans la barre en bas de l'éditeur Unity.

  --- /feedback ---

- ( ) Décocher la case "Box Collider" pour désactiver le collider.

  --- feedback ---

  Pas tout à fait, cela signifiera que le joueur peut entrer dans le GameObject à collectionner, mais il n'appellera pas la méthode `OnTriggerEnter`.

  --- /feedback ---

--- /choices ---

--- /question ---

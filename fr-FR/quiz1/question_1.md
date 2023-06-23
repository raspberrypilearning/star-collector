## Quick quiz

Answer the three questions. There are hints to guide you to the correct answer.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
legend: Question 1 sur 3
---

A collectible GameObject has this box collider set up: ![The Box Collider boundaries in Scene view.](images/star-collider.png) ![The Box Collider component properties with the Box Collider enabled and 'Is Trigger' disabled. The coordinates are positioned to fit the collectable.](images/inspector-collider.png)

And this `OnTriggerEnter` method is in a script that is attached to the GameObject:

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

The debug message "Collision detected" is not printing when the Player collides with the collectible GameObject.

How could you fix this?

--- choices ---

- ( ) Ajouter un composant Trigger au lieu d'un composant Box Collider

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider.

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

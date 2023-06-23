## Quick quiz

Answer the three questions. There are hints to guide you to the correct answer.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
legend: Vraag 1 van 3
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

- ( ) Voeg een Trigger-component toe in plaats van een Box Collider-component

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider.

  --- /feedback ---

- (X) Schakel het selectievakje 'is Trigger' in om de collider in een trigger te veranderen

  --- feedback ---

  Ja. Als je 'is Trigger' aanvinkt, verandert een collider in een trigger. Dit betekent dat `OnTriggerEnter` wordt aangeroepen wanneer een botsing wordt gedetecteerd.

  --- /feedback ---

- ( ) Selecteer het Console venster zodat je de debug uitvoer kunt zien

  --- feedback ---

  Niet helemaal, het foutopsporingsbericht wordt in het Console-venster afgedrukt, zelfs als het venster niet zichtbaar is voor jou. De uitvoer verschijnt ook in de balk onder aan de Unity Editor.

  --- /feedback ---

- ( ) Schakel het vakje 'Box Collider' uit om de collider uit te schakelen.

  --- feedback ---

  Niet helemaal, dit betekent dat de speler het te verzamelen GameObject kan binnenlopen, maar het zal niet de `OnTriggerEnter` methode aanroepen.

  --- /feedback ---

--- /choices ---

--- /question ---

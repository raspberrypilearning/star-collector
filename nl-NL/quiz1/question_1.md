## Quick quiz

Answer the three questions. Je wordt naar het juiste antwoord geleid.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
legend: Vraag 1 van 3
---

Aan een te verzamelen GameObject werd deze box-collider toegevoegd: ![De Box Collider Boundaries in de Scèneweergave.](images/star-collider.png) ![De eigenschappen van de Box Collider-component met de Box Collider ingeschakeld en 'is Trigger' uitgeschakeld. De coördinaten worden zo geplaatst dat ze passen bij de verzamelobjecten.](images/inspector-collider.png)

En deze `OnTriggerEnter` methode bevindt zich in een script dat is gekoppeld aan het GameObject:

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

Het debug bericht "Collision detected" wordt niet geprint wanneer de speler botst met het te verzamelen GameObject.

Hoe kun je dit oplossen?

--- choices ---

- ( ) Voeg een Trigger-component toe in plaats van een Box Collider-component

  --- feedback ---

Niet helemaal. Om een trigger te maken, moet je eerst een collider toevoegen.

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

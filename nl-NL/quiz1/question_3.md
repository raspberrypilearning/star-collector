
--- question ---

---
legend: Vraag 3 van 3
---

Een project gebruikt deze regel code om informatie in de gebruikersinterface weer te geven over de verzamelde sterren.

```
starText.SetText("Stars:" + stars);
```

De tekst GameObject is correct aan het script toegevoegd en het spel is klaar om te testen.

![De Inspector-weergave toont dat de tekst is verbonden met het script.](images/star-text-added.png)

Wat zou op het scherm worden getoond nadat de speler een ster heeft verzameld en de `sterren` variabele is ingesteld op `1`.

--- choices ---

- ( )

![De scèneweergave met de tekst 'Stars: 1'.](images/stars-1.png)

  --- feedback ---

  Niet helemaal. Kijk goed naar de tekststring in de code.

  --- /feedback ---

- ( )

![De scèneweergave met tekst '"Stars:" + stars'](images/stars-full.png)

  --- feedback ---

  Niet helemaal. De letters tussen de dubbele aanhalingstekens `"` vormen een tekststring. De `+` operator voegt strings samen. Wanneer je `+` een variabele toevoegt aan een string, wordt de waarde van de variabele toegevoegd aan de string.

  --- /feedback ---

- (x)

![De scèneweergave met de tekst 'Sterren:1'.](images/no-space.png)

  --- feedback ---

  Ja. Er is geen spatie na de `:` in de tekstreeks in de code, zodat er ook geen spatie staat in de tekst die wordt weergegeven.

  --- /feedback ---

- ( )

![De scèneweergave zonder tekst.](images/no-text.png)

  --- feedback ---

  Nee, er zijn geen fouten in de code, dus de code zal wat tekst uitvoeren naar de scene-gebruikersinterface.

  --- /feedback ---

--- /choices ---

--- /question ---

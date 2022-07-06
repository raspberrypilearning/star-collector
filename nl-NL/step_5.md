## De tijd bijhouden

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Nu een speler sterren kan verzamelen, voeg je een timer toe om de tijd te laten zien die nodig is om alle drie de sterren te verzamelen. 
</div>
<div>
![de spelweergave met een 'sterren' en een 'tijd' variabele op het canvas, waarbij de timer stopt wanneer de derde ster wordt verzameld.](images/timer-stops.gif){:width="300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">**Game mechanics**</span> are a key part of game design. They are the rules that control a player's actions. Een **timer** is een spelmechanisme dat een uitdaging toevoegt aan videogames. In feite zijn er veel Guinness World Records op basis van hoe snel spelers uitdagingen in games kunnen voltooien!
</p>

De speler moet bijhouden hoelang het duurt om de minigame te voltooien, je kunt dit doen met een andere variabele.

--- task ---

In the Hierarchy window, right-click on your **Canvas** and from UI create another **Text - TextMeshPro GameObject**. Je ziet 'New text' op je scherm in de spelweergave:

![De spelweergave met een 'new text' UI-tekstitem dat op het scherm wordt weergegeven.](images/new-timer.png)

--- /task ---

--- task ---

Klik met de rechtermuisknop op het nieuwe **Text (TMP) GameObject** en selecteer **hernoemen**. Noem hem `Tijd Tekst` om hem gemakkelijk te kunnen identificeren:

![Hernoemde Tijd GameObject in het Hierachy venster.](images/time-gameobject.png)

--- /task ---

--- task ---

Wijzig `new text` in `tijd: 0` in het Inspector venster, in de eigenschap tekstinvoer van het nieuwe TextMeshPro GameObject.

Gebruik de **Rect Transform** component om de uitlijning te wijzigen in **Top Right**. Wijzig ook de positie in `x = -60`, `y = -50`:

![Het Inspector venster met het vervolgkeuzemenu Anchor presets dat rechtsboven toont en de 'Pos x' = -60 en 'Pos y' = - 50 waarden bijgewerkt.](images/reposition-text-timer.png)

--- /task ---

De tekst die wordt weergegeven moet worden bijgewerkt zodat deze continu het aantal seconden weergeeft sinds het spel is gestart.

--- task ---

Open je `SterSpeler` script en voeg code toe om een TMP_Text object met de naam `tijdTekst` te maken:

--- code ---
---
language: cs filename: StarPlayer.cs line_numbers: true line_number_start: 6
line_highlights: 10
---
public class StarPlayer : MonoBehaviour
{ public int stars = 0; // An integer whole number public TMP_Text starText; public TMP_Text timeText; --- /code ---

--- /task ---

--- task ---

`Time.time` geeft de tijd in seconden weer sinds de scène is gestart. `Mathf.Round` verandert een getal in een geheel getal.

Stel de tekst in om het aantal hele seconden bij elke update weer te geven:

--- code ---
---
language: cs filename: StarPlayer.cs - Update() line_numbers: true line_number_start: 18
line_highlights: 21
---

    void Update()
    {
        starText.SetText("Stars: " + stars);
        timeText.SetText("Time: " + Mathf.Round(Time.time));
    }
--- /code ---

Sla je script op en ga terug naar de Unity Editor.

--- /task ---

--- task ---

Selecteer de speler in het Hierarchy venster en ga naar het `Ster Speler` script component in het Inspector venster. Klik op de cirkel naast `Tijd Tekst` en kies je nieuwe 'Tijdtekst' object.

--- /task ---

--- task ---

**Test:** Speel je minigame en controleer of de tijd wordt bijgewerkt terwijl je speelt. Wat gebeurt er als je alle drie sterren verzamelt?

![Spelweergave met UI-tekst met drie sterren verzameld en een tijd van 45 seconden.](images/both-texts-updating.gif)

--- /task ---

De tijd moet stoppen wanneer alle drie de sterren worden verzameld, maar op dit moment zal hij blijven tellen zolang de minigame speelt.

--- task ---

Open het `SterSpeler` script en maak een if statement rond je tijdcode om alleen de seconden te tellen als de speler minder dan drie sterren heeft verzameld:

--- code ---
---
language: python filename: StarPlayer.cs - Update() line_numbers: true line_number_start: 18
line_highlights: 21-24
---

    void Update()
    {
        starText.SetText("Stars: " + stars);
        if (stars < 3)
        {
            timeText.SetText("Time: " + Mathf.Round(Time.time));
        }
    }
--- /code ---

Sla je script op en ga terug naar de Unity Editor.

--- /task ---

--- task ---

**Test:** Speel je minigame opnieuw. De timer stopt wanneer de speler drie sterren heeft:

![De spelweergave toont de timer die optelt vanaf 45 en stopt bij 47 wanneer er drie sterren worden verzameld.](images/timer-stops.gif)

--- /task ---

Na de reflectie kun je je project uitbreiden met functies die je belangrijk vindt.

--- save ---

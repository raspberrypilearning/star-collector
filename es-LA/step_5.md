## Controlando el tiempo

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Now that a player can collect stars, add a timer to show the amount of time taken to collect all three stars. 
</div>
<div>
![The Game view showing a 'stars' and a 'time' variable on the canvas with the timer stopping when the third star is collected.](images/timer-stops.gif){:width="300px"}
</div>
</div>

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
<span style="color: #0faeb0">**Game mechanics**</span> are a key part of game design. Son las reglas que controlan las acciones de un jugador. A **timer** is a game mechanic that adds a challenge to video games — in fact, there are many Guinness World Records based on how quickly players can complete challenges in games!
</p>

The player needs to keep track of how long they are taking to complete the minigame, you can do this with another variable.

--- task ---

In the Hierarchy window, right-click on your **Canvas** and from UI create another **Text - TextMeshPro GameObject**. You will see 'New text' written on your screen in Game view:

![La vista del juego con 'New Text' escrito en la pantalla.](images/new-timer.png)

--- /task ---

--- task ---

Right-click on the new **Text (TMP) GameObject** and select **rename**. Call it `Time Text` to easily identify it:

![Time GameObject renombrado en la ventana Hierachy.](images/time-gameobject.png)

--- /task ---

--- task ---

From the Inspector window, in the Text Input propery for the new TextMeshPro GameObject, change `New Text` to `Time: 0`.

Use the **Rect Transform** component to change the alignment to **Top Right**. Also change the position to `x = -60`, `y = -50`:

![La ventana Inspector con el menú desplegable de ajustes preestablecidos Anchor que se muestra en la parte superior derecha y los valores 'Pos x' = -60 y 'Pos y' = - 50 actualizados.](images/reposition-text-timer.png)

--- /task ---

The text that is displayed needs to update so that it continuously shows the number of seconds since the game started.

--- task ---

Open your `StarPlayer` script and add code to create a TMP_Text Object called `timeText`:

--- code ---
---
language: cs filename: StarPlayer.cs line_numbers: true line_number_start: 6
line_highlights: 10
---
public class StarPlayer : MonoBehaviour
{ public int stars = 0; // An integer whole number public TMP_Text starText; public TMP_Text timeText; --- /code ---

--- /task ---

--- task ---

`Time.time` gives the time in seconds since the Scene started. `Mathf.Round` turns a number into a whole number.

Set the text to show the number of whole seconds on each update:

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

Save your script and go back to the Unity Editor.

--- /task ---

--- task ---

Select the Player in the Hierarchy window and go to the `Star Player` script component in the Inspector window. Click on the circle next to `Time Text` and choose your new 'Time Text' object.

--- /task ---

--- task ---

**Test:** Run your minigame and check that the time updates as you play. What happens when you collect all three stars?

![Vista del juego con texto de interfaz de usuario que muestra tres estrellas reunidas y un tiempo de 45 segundos.](images/both-texts-updating.gif)

--- /task ---

The time needs to stop when all three stars are collected, but currently it will keep counting up for as long as the minigame is playing.

--- task ---

Open the `StarPlayer` script and create an if statement around your time code to only count the seconds if the player has collected less than three stars:

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

Save your script and go back to the Unity Editor.

--- /task ---

--- task ---

**Prueba:** Vuelve a ejecutar tu minijuego. El cronómetro se detendrá cuando el jugador tenga tres estrellas:

![La vista del juego que muestra el cronómetro contando desde 45 y deteniéndose en 47 cuando se recolectan tres estrellas.](images/timer-stops.gif)

--- /task ---

Después del paso de Reflexión, puedes actualizar tu proyecto con las funciones que consideres importantes.

--- save ---

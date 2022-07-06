## Collecting the star

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
La estrella debe desaparecer cuando la recojas. 
</div>
<div>
![La vista de Escena con tres estrellas ocultas al jugador por las paredes.](images/multiple-stars.png){:width="300px"}
</div>
</div>

In Unity, a Collider with a **Trigger** calls the `OnTriggerEnter` method when a collision happens, but it does not prevent a Player walking into the Collider.

--- task ---

Select the **Star** and in the Inspector window, click **Add Component**. Start typing `box` until you see **Box Collider** and click it. Se agregará un nuevo componente a la estrella en la ventana Inspector.

Check the **Is Trigger** box.

![Componente Collider con 'Is Trigger' marcado.](images/collider-trigger.png)

Click <kbd>Shift</kbd>+<kbd>F</kbd> to focus on the Star in the Scene view. Verás un contorno de cuadro verde alrededor de la Estrella: esto muestra el contorno del Colisionador. Si el Colisionador del jugador ingresa a esta área, habrá una colisión y se llamará `OnTriggerEnter`:

![Scene view with the focus on the star GameObject. Se muestra una línea verde alrededor del borde de la estrella en forma de caja.](images/collider-star.png)

--- /task ---

Solo quieres que se recoja la estrella si el GameObject que ha chocado con ella es el Jugador. Unity uses **Tags** to label GameObjects. Unity includes a Player tag.

--- task ---

Select your **Player** GameObject and set its Tag to `Player` using the drop-down menu:

![The Inspector window with the Tag drop-down menu showing the Unity default tags, including 'Player' tag.](images/tag-menu.png)

--- /task ---

--- task ---

Open your StarController script by switching to your code editor or double-clicking on the script in your **My Scripts** folder from the Project window.

Add a new `OnTriggerEnter` method under the closing `}` of the `Update` method but before the closing `}` of the `StarController` class:

--- code ---
---
language: cs filename: StarController.cs - OnTriggerEnter(Collider other) line_numbers: true line_number_start: 16
line_highlights: 20-27
---

    void Update()
    {
        transform.Rotate(Vector3.up * spinSpeed); // Rotate about the y (up) axis
    }
    void OnTriggerEnter(Collider other)
    {
        // Check the tag of the colliding object
        if (other.CompareTag("Player"))
        {
            gameObject.SetActive(false);
        }
    }
} --- /code ---

Guarda tu script.

--- /task ---

--- task ---

**Prueba:** Juega tu proyecto. Walk into the star to see it disappear.

**Debug:** Make sure you have added the Player tag to your Player GameObject and not to the Star!

![La vista del juego que muestra al jugador chocando con la estrella y la estrella desapareciendo.](images/collect-star.gif)

--- /task ---

Agregar un efecto de sonido hace que recolectar una estrella sea más satisfactorio para el jugador.

--- task ---

Add a public `collectSound` variable to your `StarController` script to store the sound that you want to play:

--- code ---
---
language: cs filename: StarController.cs line_numbers: true line_number_start: 5
line_highlights: 8
---
public class StarController : MonoBehaviour
{ float spinSpeed = 0.5f; public AudioClip collectSound;

--- /code ---

Hacer una variable `pública` significa que puedes asignarla en el Inspector y acceder a ella desde otros GameObjects.

--- /task ---

--- task ---

Agrega una línea al método `OnTriggerEnter` para reproducir el sonido en la ubicación de la estrella. El método `AudioSource.PlayClipAtPoint` reproducirá el sonido:

--- code ---
---
language: cs filename: StarController.cs - OnTriggerEnter(Collider other) line_numbers: true line_number_start: 21
line_highlights: 26
---

    void OnTriggerEnter(Collider other)
    {
        // Check the tag of the colliding object
        if (other.CompareTag("Player"))
        {
            AudioSource.PlayClipAtPoint(collectSound, transform.position);
            gameObject.SetActive(false);
        }
--- /code ---

Guarda tu código.

--- /task ---

--- task ---

Switch back to the Unity Editor and click on the **Star GameObject** in the Hierarchy window.

Find the **Collect Sound** property of the Star's StarController script component in the Inspector window.

Click on the circle to the right of the Collect Sound property and choose the **Collect** sound:

![Collect Sound property with Collect clip selected.](images/collect-sound-property.png)

--- /task ---

--- task ---

**Test:** Play your scene and collect the star to hear the sound.

--- /task ---

Tu juego necesita más estrellas.

--- task ---

Selecciona tu Estrella en la vista de Escena y duplícala con <kbd>Ctrl</kbd>+<kbd>D</kbd> (o <kbd>Cmd</kbd>+<kbd>D</kbd>). The Particle System is a child object so this will be duplicated in your new star:

![El menú emergente de la Estrella con el duplicado resaltado.](images/duplicate-star.png)

The new star will appear in the same position, so drag it to a new hiding position in the scene. El Sistema de Partículas secundario se moverá con la estrella.

To see your map in a top-down view, right-click where it says **Persp** in the top right of the Scene view and choose **Top**. To return to the normal view, right-click on **Top** and choose **Free**:

![Imágenes de lado a lado de la vista de escena en ángulos de visión de arriba hacia abajo y libres. El menú emergente se muestra sobre las palabras 'persp' y 'top'.](images/different-views.png)

You can use the arrow keys to move left and right and zoom. Hold the right mouse button down and drag to move and rotate.

Repite esto para que tengas tres estrellas escondidas en tu mapa:

![La vista Escena con tres estrellas colocadas en escondites en el mapa.](images/3-stars-added.png)

--- /task ---

--- task ---

**Test:** Play your scene and collect all the stars make sure they all disappear and play a sound when collected.

--- /task ---

--- save ---

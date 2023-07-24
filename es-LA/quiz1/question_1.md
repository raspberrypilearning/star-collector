## Quick quiz

Answer the three questions. There are hints to guide you to the correct answer.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
legend: Pregunta 1 de 3
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

- ( ) Agrega un componente de Activación en lugar de un componente Box Collider

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider.

  --- /feedback ---

- (x) Marca la casilla 'Is Trigger' para convertir el colisionador en un activador

  --- feedback ---

  Sí. Al marcar 'Is Trigger' convierte un colisionador en un activador. Esto significa que se llamará al `OnTriggerEnter` cuando se detecte una colisión.

  --- /feedback ---

- ( ) Seleccione la ventana Consola para que puedas ver la salida de depuración

  --- feedback ---

  No del todo, el mensaje de depuración se imprimirá en la ventana Consola, incluso si la ventana no es visible para ti. La salida también aparece en la barra en la parte inferior del editor de Unity.

  --- /feedback ---

- ( ) Desmarque la casilla 'Box Collider' para desactivar el colisionador.

  --- feedback ---

  No del todo, esto significará que el jugador puede acceder al GameObject coleccionable, pero no llamará al método `OnTriggerEnter`.

  --- /feedback ---

--- /choices ---

--- /question ---

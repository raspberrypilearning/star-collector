## Test rápido

Responda las tres preguntas. Hay pistas para guiarte hacia la respuesta correcta.

Cuando hayas respondido a cada pregunta, haz clic en **Revisar mi respuesta**.

¡Qué te diviertas!

--- question ---

---
legend: Pregunta 1 de 3
---

Un GameObject coleccionable tiene configurado este box collider: ![Los límites de Box Collider en la vista de Scene.](images/star-collider.png) ![Las propiedades del componente Box Collider con Box Collider habilitado y 'Is Trigger' deshabilitado. Las coordenadas se colocan para adaptarse al coleccionable.](images/inspector-collider.png)

Y este método `OnTriggerEnter` está en un script adjunto al GameObject:

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

El mensaje de depuración "Colisión detectada" no se imprime cuando el jugador choca con el GameObject coleccionable.

¿Cómo podrías arreglarlo?

--- choices ---

- ( ) Agrega un componente de Activación en lugar de un componente Box Collider

  --- feedback ---

No exactamente. Para crear un activador, primero debes agregar un colisionador.

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

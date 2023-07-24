
--- question ---

---
leyenda: Pregunta 3 de 3
---

Un proyecto usa esta línea de código para mostrar información en la interfaz de usuario sobre las estrellas recolectadas.

```
starText.SetText("Stars:" + stars);
```

El texto GameObject se agregó correctamente al script y el juego está listo para probarse.

![La vista Inspector que muestra el texto se ha conectado al script.](images/star-text-added.png)

¿Qué mostraría la pantalla después de que el jugador haya recogido una estrella y la variable `stars` esté configurada en `1`?

--- choices ---

- ( )

![La vista de Escena con texto que dice "Estrellas: 1".](images/stars-1.png)

  --- feedback ---

  No exactamente. Observa con cuidado la cadena de texto en el código.

  --- /feedback ---

- ( )

![La vista de Escena con texto que dice '"Stars:" + stars'](images/stars-full.png)

  --- feedback ---

  No exactamente. Las letras entre comillas dobles `"` forman una cadena de texto. El operador `+` une cadenas. Cuando agrega `+` una variable a una cadena, el valor de la variable se agrega a la cadena.

  --- /feedback ---

- (x)

![La vista de Escena con texto que dice 'Estrellas: 1'.](images/no-space.png)

  --- feedback ---

  Sí. No hay espacio después del `:` en la cadena de texto del código, por lo que no habrá ninguno en el texto que se muestra.

  --- /feedback ---

- ( )

![La vista de Escena sin texto.](images/no-text.png)

  --- feedback ---

  No, no hay errores en el código, por lo que el código generará un texto en la interfaz de usuario de la escena.

  --- /feedback ---

--- /choices ---

--- /question ---

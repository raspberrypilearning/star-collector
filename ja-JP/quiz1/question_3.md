
--- question ---

---
legend: 質問3/3
---

A project uses this line of code to display information in the UI about the stars collected.

```
starText.SetText("Stars:" + stars);
```

The text GameObject has been correctly added to the script and the game is ready to test.

![The Inspector view showing the text has been connected to the script.](images/star-text-added.png)

What would the screen show after the Player has collected one star and the `stars` variable is set to `1`.

--- choices ---

- ( )

![The Scene view with text saying 'Stars: 1'.](images/stars-1.png)

  --- feedback ---

  これだけではありません。 Look carefully at the text string in the code.

  --- /feedback ---

- ( )

![The Scene view with text saying '"Stars:" + stars'](images/stars-full.png)

  --- feedback ---

  これだけではありません。 The letters inside double quotes `"` make a text string. The `+` operator joins strings together. When you add `+` a variable to a string, the value of the variable gets added to the string.

  --- /feedback ---

- (x)

![The Scene view with text saying 'Stars:1'.](images/no-space.png)

  --- feedback ---

  できます。 There is no space after the `:` in the text string in the code so there won't be one in the text that is displayed.

  --- /feedback ---

- ( )

![The Scene view with no text.](images/no-text.png)

  --- feedback ---

  No, there are no errors in the code so the code will output some text to the scene UI.

  --- /feedback ---

--- /choices ---

--- /question ---

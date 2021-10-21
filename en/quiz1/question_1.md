## Reflection

You did it! You created your first Unity minigame and learned lots of new skills along the way.

Now it’s time to reflect - reflecting is an important part of learning because it helps make new connections in your brain.

Answer the three questions below to reflect on what you’ve learned.

After each question, press submit. You will be guided towards the correct answer. You can do this activity as many times as you want to.

--- question ---

---
legend: Question 1 of 3
---

A collectible GameObject has this box collider set up:
![The Box Collider boundaries in Scene view](images/star-collider.png)
![The Box Collider component properties with the Box Collider enabled and Is Trigger not enabled. The coordinates are positioned to ffit hte collectable. ](images/inspector-collider.png)

And this `OnTriggerEnter` method in a script that is attached to the GameObject:

```
void OnTriggerEnter(Collider other)
{
  Debug.Log("Collision detected");
}
```

The debug message "Collision detected" is not printing when the player collides with the collectible GameObject.

How could you fix this?

--- choices ---

- ( ) Add a Trigger component instead of a Box Collider component.

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider. 

  --- /feedback ---

- (x) Check the 'is Trigger' box to turn the Collider into a Trigger.

  --- feedback ---

  Yes. Checking 'is Trigger' turns a Collider into a trigger. This means the 'OnTriggerEnter' will be called when a collision is detected.

  --- /feedback ---

- ( ) Select the Console Window so you can see the debug output.

  --- feedback ---
  
  Not quite, the debug message will print to the Console window even if the window is not visible to you. The output also appears in the bar at the bottom of the Unity editor.

  --- /feedback ---

- ( ) Untick the 'Box Collider' box to disable the collider.

  --- feedback ---
  
  Not quite, this will mean that the player can walk into the collectable GameObject but it will not call the OnTriggerEnter.

  --- /feedback ---

--- /choices ---

--- /question ---

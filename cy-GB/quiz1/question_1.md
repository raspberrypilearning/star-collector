## Quick quiz

Answer the three questions. There are hints to guide you to the correct answer.

When you have answered each question, click on **Check my answer**.

Have fun!

--- question ---

---
legend: Cwestiwn 1 o 3
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

- ( ) Add a Trigger component instead of a Box Collider component

  --- feedback ---

Not quite. To create a trigger, you first need to add a collider.

  --- /feedback ---

- (x) Check the 'Is Trigger' box to turn the collider into a trigger

  --- feedback ---

  Iawn. Checking 'Is Trigger' turns a collider into a trigger. This means the `OnTriggerEnter` will be called when a collision is detected.

  --- /feedback ---

- ( ) Select the Console window so you can see the debug output

  --- feedback ---

  Not quite, the debug message will print to the Console window even if the window is not visible to you. The output also appears in the bar at the bottom of the Unity Editor.

  --- /feedback ---

- ( ) Untick the 'Box Collider' box to disable the collider.

  --- feedback ---

  Not quite, this will mean that the Player can walk into the collectable GameObject, but it will not call the `OnTriggerEnter` method.

  --- /feedback ---

--- /choices ---

--- /question ---

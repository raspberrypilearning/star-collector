## A spinning star

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
The collectibles in this game are stars that spin to attract attention.
</div>
<div>
![A star spinning with particle effect](images/star-particle.gif){:width="300px"}
</div>
</div>

--- task ---

Launch the Unity hub and open the project you created for [Explore a 3D world](https://projects.raspberrypi.org/en/projects/explore-a-3d-world){:target=blank}. 

--- collapse ---

---
title: I haven't got my Explore a 3D world project
---

If you are not able to open your 'Explore a 3d world' project you can download, unzip, and open this  [Star collector starter project](){:target=blank}. 

<mark>Add link to starter project (solution to Explore 1) when available</mark>
--- /collapse ---

--- /task ---

--- task ---

Right click on the '3D World' scene in the Hierarchy window and 'Save Scene As' `Star Collector`. 

This creates a new Scene file in the Project window. Scenes in a project can share Assets including Scripts. 

Your project now contains two scenes but you will only work on one scene at a time. 

--- /task ---

--- task ---

The star collector minigame needs a camera view that is high enough to view the layout of some of the map but not too high or it will reveal the position of the stars.  

In the Hierarchy window, click on 'Player' then select 'Main Camera' change the position in the Inspector window 'Transform' component to:

![The Transform component with position x = 0 , y = 4 and z = -2.5. The rotation x = 35.](images/camera-position.png)

--- /task ---

--- task ---

In the Project window go to the 'Models' folder and drag the 'Star' into the **Scene view**. 

--- /task ---

--- task ---

Make sure the Star GameObject is selected in the Hierarchy window and position it using either:
+ the arrows from the 'Transform' tool and the Scene view
+ the coordinates from the 'Transform' component in the Inspector window

Your star should be off the ground, 'Position' 'Y' = `0.7` is about right. 

You might want to hide the star behind a wall so it's harder for players of your game to find: 

![The scene view showing star game object hidden behind two walls](images/position-star.png)

--- /task ---

--- task ---

In the Inspector window, click 'Add Component' and choose 'New script' then name your new script `StarController`  

Double-click on `StarController` in the script component to launch your script in the editor. 

![The script component with the word 'Star Controller' and script icon annotated to show where to double-click.](images/star-script-open.png)

--- /task ---

In [Explore a 3D World](https://projects.raspberrypi.org/en/projects/explore-a-3d-world/){:target="_blank"} you used `transform.Rotate` to turn the Player. You can use the same method to spin the Star around the Y axis.

--- task ---
Create a variable called `spinSpeed` so you can control how fast your star spins:

```
public class StarController : MonoBehaviour
{
    float spinSpeed = 5.0f; 
```

Add code to spin your Star:

```
// Update is called once per frame
void Update()
{
    transform.Rotate(Vector3.up * spinSpeed); // rotate about the Y (up) axis
}
```

Save your script then return to the Unity editor. 

--- /task ---

--- task ---

**Test:** Play your scene and check that the Star is spinning: 

![The Game view with a spinning star](images/star-spin.gif)

**Debug:** Make sure you added the Script to the Star GameObject. If you accidentally added it to a different GameObject then you can click the three dots next to the Script component and choose 'Remove Component.'

--- /task ---

Time for a Particle System. 

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;">
A <span style="color: #0faeb0">**Particle effect**</span> uses lots of small images, or 'particles', to create a visual effect which adds life to a computer game. Next time you play a computer game, look out for all the places where particle effects are used. 
</p>

--- task ---
Right-click on the Star GameObject in the Hierarchy window and choose 'Create' then 'Effects' then 'Particle System'. This will add a ParticleSystem GameObject to the Star. 

Adding the ParticleSystem as a child object of the Star means that if you move the star in Scene view the particles will move with it. 

--- /task ---

--- task ---
**Test:** Play your Scene to see the default particle effect. It's spinning with the Star and it's not quite right for a sparkling star:

![desc](images/particle-star-default.gif)

Exit Playmode.

--- /task ---

There are lots of settings that you can use to customise the Particle System. 

--- task ---

Use these settings to create a sparkle effect that doesn't spin with the Star: 

![The Inspector particle system with settings: Start Lifetime = 1, Start Speed = 0.5, Start Size = 0.2. Start colour: Yellow ](images/particle-settings.png)

**Tip:** To close the colour picker, click on the 'X' or click elsewhere in the Unity editor. 

--- /task ---

--- task ---
**Test:** Click Play to see the effect. 

Adjust settings until you are happy with the particle effect. 

Remember, you can try things out in Playmode, but you need to exit Playmode to make changes that you want to keep:

![The spinning star with new particle settings in place](images/star-particle.gif)

--- /task ---

Now that Star is just asking to be collected! 

--- save ---
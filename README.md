# Roll-A-Ball
Easy tutorial to get familiar with the basics of Unity

## What is this going to teach you?
You're going to learn the basics of Unity from creating **GameObjects**, attaching the **Rigidbody** component and applying forces to an object through keyboard input.  No assets will be imported for this project, nor will there be models, sounds, textures, or animations.  This will be bare bones so you can focus on functionality over style!

**Let's begin!**

## The Steps
1. Create a new project.  If needed, you can do this by opening the file menu and clicking **New Project** then naming it and saving the project location. <--- Saving it to your desktop will allow for easy opening later on.  

2. Next, you should have a new project open so let's save our scene.  You can do this by opening file again, **Save Scene**, and save it in the assets file.  You can name it what you like.

3. Okay, after it's saved, let's begin making stuff.  First, create a floor for our player.  Go into **GameObject**, then **3DObject**, and click **Plane**.  This will give you a floor pane in your Hierarchy that you can adjust, or move around.  After setting it, clear the gear icon on the top right and click **reset** this sets the GameObject to 0,0,0 or **Origin**.  Origin is the centered coordinate where all other points are calculated from.  

4. Next, let's change the scale of the plane.  You can change the size of the scale by either clicking on the scale icon on the top left and dragging the correct axis icon, or by inputting a number directly into the **x, y, z** scales in the transform component.  **Note:** Planes GameObjects are only affected by the **x, and z** coordinates and attempting to change the **y** won't do anything unless you change it to negative.  Change the scale position to 2, 1, 2.

5. Now, let's create a player GameObject to use.  Go into **GameObjects** again, open **3DObjects** and create a **Sphere**.  Rename the sphere to "Player" so we know our objects in the Hierarchy.  After, reset it's position back to origin.  Notice that the sphere is actually **inside** the floor right now, this won't do.  Most primitive objects have a scale of **1,1,1** on x,y and z, so simply moving the y position on the sphere by **.5** will place the sphere perfectly on top of the floor.

6. Notice how the floor and the sphere are both a default *white* color and are hard to differentiate.  Let's add some color to the sphere so we can visually set them apart.  To do this, we will add a material to the object so that we may add color to it.  In the project view, create a new folder and rename it to **Materials**.  Hit create again but this time, let's create a new Material.  After creating one, rename the material to **Player**.  In the Inspector View, notice the first line called **Albedo**, Albedo simply adds a color to a surface as a parameter.  Change it to a nice color using the color menu and exit.  To apply this color, drag and drop it onto the object you want to apply it to.  In this case let's drag it to the player.  

7. Now, **we're going to make the player move**.  To do this, we're going to need to an an attribute, or **Component** to the Player called **Rigidbody**.  To attach it, we can do this multiple ways.  One way is to click the player Object, click the **Component** menu on the top, click on **Physics** and click **Rigidbody**.  Or from the Inspector menu, we can directly add a component by using **Add Component** on the bottom of the list, then choosing **Physics** and choosing **Rigidbody**. 

**Note:** Our player uses the Rigidbody component to allow our GameObject to act under the control of physics which is controlled by a built-in engine controlled by Unity. The Rigidbody can receive forces and torque to make your objects move in a realistic way. And GameObject's must contain a Rigidbody to be influenced by gravity or act under added forces via scripting.  

8. Next, we're going to write a script that we attach to the player object to take the keyboard input and apply it to the object as forces to get it to move.  *See why Rigidbody is important? Without Rigidbody, the object isn't interactable.*.  But first, let's create a new folder in the project view and rename it to **Scripts**.  Next we're going to make a new **C# Script**.  You can do this in two ways: You can highlight the scripts folder in the project view, click **Assets** in the top menu, click **Create**, and then click **C# Script**.  Alternatively, you can highlight game object you want to make a script for, click **Add Component**, and then scroll to the bottom to find **New Script**.  From this menu, we can name our script, choose the language we want to use, and attach it to our GameObject all-in-one step. Use either method and name the script **PlayerMove**.

**NOTE!** We're going to go more in depth into Scripts later on, but not for this assignment.  For now copy the code and make sure it's correct as syntax is everything and is quite unforgiving. 

9.  Now, let's open up our script by double-clicking the script in the project.  Doing so will open up the script in our script editor.  **Note:** The script editor may vary between Windows and Mac so don't worry if yours looks different, it should still function the same. Delete the original, default code as we won't be needing those.  

**Next, inside the open braces, type in:** 


void FixedUpdate ()

{
  
  float moveHorizontal = Input.GetAxis("Horizontal");
  
  float moveVertical = Input.GetAxis("Vertical");

}

**it should look like this...**

![ScreenShot](https://raw.githubusercontent.com/junior-devleague/roll-a-ball/master/assets/Screen%20Shot%202017-08-08%20at%2011.48.59%20PM.png)

**ATTENTION!** THE LIGHTENED OUT TEXT ARE SIDE NOTES TO EXPLAIN WHAT EACH PART IS STEP BY STEP SO YOU HAVE A BETTER UNDERSTANDING OF WHAT'S GOING ON.  IF YOU HAVE ANY QUESTIONS, ASK A INSTRUCTOR WHEN YOU CAN.

**Next, we're going to add in the Rigidbody component to our script so that we can apply forces to it.  It'll look like this:**

![ScreenShot](https://raw.githubusercontent.com/junior-devleague/roll-a-ball/master/assets/Screen%20Shot%202017-08-09%20at%2012.22.51%20AM.png)

Now, save what you have made (CMD + S for Mac or WIN + S for Windows) and go back to our interface.  Check at the bottom for any errors that might have been made, before you are able to test, the code is compiled and any errors will prevent it from starting.  No errors means that our code works and we can play it in our scene.  Press "Play" in the Toolbar and test it out!  **Congrats!** We've now got a rolling ball that responds to our input.  However, it's a little slow for our liking, so let's go back to our Code Editor one mroe time so we can adjust that.

**Here's what the code should look like:**

![ScreenShot](https://raw.githubusercontent.com/junior-devleague/roll-a-ball/master/assets/Screen%20Shot%202017-08-09%20at%2012.38.43%20AM.png)

Notice that we added a new public float variable above called "speed" and at the bottom, we multiplied our movement * speed.  Now, let's go to the interface and inside the player script component we see a new editable property called "speed".  Adjusting this will allow us to speed up or slow down our character to our liking.  

**Nice Job!** Now we are able to move our character at a faster pace and now we know how to apply forces to our GameObject.  If you have any questions, or need help debugging, please refer to Mark or Raymond for assistance.



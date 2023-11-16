# Unity-Cheat-Sheet
**UNITY-CHEAT-SHEET**

In this tutorial, you will find simple information on how some features in the Unity program work and how you can implement these features. Tutorial includes the headlines:

1. Locomotion

2. Grabbable objects

3. How to add balance?

4. Attachments

5. Adding haptic feedback

6. Adding audio source

7-8. Adding laser and sound to the remote

9. How to add a video to the screen?

10. How to make pop-up UI windows?

11. How to make a pop-up window disappear after pushing the button?

12. How to make a pop-up window appear when pushing another button?

13. How to make an UI window to pup-up when you teleport to an area?

14. How to get notifications from consol when something is touched or interacted?

15. How to get the data of rotation and position to the console and to a distinct file?

16. How to get the data of the exact time of grabbing an object?

![1](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/a0df3ef3-ad8c-4080-9e3f-960a5c3608a2)

**1. Locomotion Tutorial:** https://learn.unity.com/tutorial/vr-locomotion?pathwayId=627c12d8edbc2a75333b9185&missionId=62554983edbc2a76a27486cb#

Locomotion makes it possible for the user to move in a VR room. We have different options to use in Unity for locomotion. We are given the options of continuous turning or snap turning.

Motion sickness may cause people in VR feel nauseous and continuous turning may lead to that. Turning off continuous turning and turning on the snap tuning will fix that problem. To turn on snap turning you need to add the component to your XR rig. Here is a more detailed explanation on how to add snap turning to your XR Rig:

**1.1 Give your XR Rig locomotion capabilities:**

In the Hierarchy, select the XR Rig object and add a Locomotion System component.
For the XR Origin property, select and drag the XR Origin component from the Inspector onto the slot that says “None”.

Note: You can also select the object picker and double-click the XR Rig object.

**1.2 Allow your XR Rig to turn around:**

With the XR Rig object still selected, add a Snap Turn Provider (Action-based) component.
For the System property, drag and drop the Locomotion System component onto the slot.

![upload_c8a687e42467fb32f19935829ffcd2c8](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/22f46783-c1f1-4510-8976-92a30626bec6)

**2. Grabable objects:** https://learn.unity.com/tutorial/grabbable-objects?pathwayId=627c12d8edbc2a75333b9185&missionId=62554983edbc2a76a27486cb#

How to make an object grabbable?:

Before making an object grabbable first you’ll need hands. If you are already using the Unity tutorials and downloaded the preconfigured room then you can find hand options in the assets section. If not then it is possible to add them yourself.After being sure you have hand assets then, you can go the Project window, open Course Library > Prefabs > VR > Hands, then determine which VR_Hand option you prefer.
After doing that you should assign your hands. In order to do it you should go to the hierarchy. In the Hierarchy, select XR Rig > Camera Offset > LeftHand / RightHand Controller. In the XR Controller Component, for the Model Prefab property, drag and drop your hand prefab of choice to assign it.

Now that you have hands you are ready to interact with an object. To make an object grabbale you have to add the component to it. Add an XR Grab Interactable component to your object. This will also add a rigidbody to your object. You can not use the grabbing feature without the rigidbody. in order to interact with the object, movement type should be “kinematic”. Now you should be able to grab an object!

![upload_564ed73e2121878e295068316e9e5d95](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/6f530c66-6a25-44f9-a58f-d52fb197d724)

**Some Notes:**

Turning off “anchor control” turns off the pushing and pulling through the pointer feature. If you have this on then you will be able to push and pull an object in the air.

You can make your hands invisible when grabbing the hand controllers with “hinde controller on S” right under the XR Interactor

**IMPORTANT:** If you want to get the data that something was grabbed to the console or to another distinct file first you need to add your XR Grab interactable component an event. How you can add these events is : from the boxes in the component. Look for the boxes on “ Select’” and to select object box drag your game object, and for the function box choose your interaction. Only then your script will work.

![upload_6da52428f3911307e716a6e9a21556e2](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/be6c9cad-58a0-4c22-8368-e29a14708961)

**3. How to make an object bounce:**

In Unity you can also get to choose how an object behaves. For example you can make a ball bouncy. In order to do that you must locate the “Material” property in the Ball object’s “Sphere Collider” component. Then click the circular button to assign one of the provided “Physics Materials”. After doing that in order to prevent the ball from falling from the ceiling you should add a rigidbody if it is not already there and after that set the “Collision Detection” setting to “Continuous Dynamic”.

By doing this you can decide how bouncy you want your items to be and how smooth you want them to move.

**IMPORTANT NOTE:** Adding physical material (rigidbody) is important if not they may fall through the ceiling.

**4. In order to hold an object from the handle:**

By activating this feature you can see your objects not directly inside of your hand but as if you are holding them from their handle. This property makes grabbing objects look more realistic.
First attach transform (from XR Grab interactable) and add a child objet by right clicking to create empty. Reposition and rotate the object so that it matches the position and orientation your hand model should be when you grab the new object. After creating a child object with create empty button you need to drag and drop that child object in the attach transform box that is ib the XR Grab interactable.

**5. Adding Haptic Feedback:**

You can add haptic on hover enter and select enter to provide physical feedback to the player’s hands.

To edit both controller objects simultaneously, navigate to the Hierarchy, expand XR Rig > Camera Offset, then Ctrl/Cmd+select both the RightHand Controller and LeftHand Controller for simultaneous selection. Proceed to find the haptic events by expanding the Haptic Events fold-out at the bottom of the Controller objects’ XR Ray Interactor components, and enable subtle haptic feedback for when the user hovers over an object by clicking the On Hover Entered checkbox, setting the Intensity to a low value (e.g., 0.1-0.5), and configuring the Duration to a very short duration (e.g., 0.1 seconds)

![upload_75992bca5f685c5cce204f9143cddf8c](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/59df341b-d230-4dd6-8785-378e9e7ba221)

**6. Adding Audio Source to an object:** https://learn.unity.com/tutorial/2-1-audio-and-haptics?missionId=62554d88edbc2a76a2748758&pathwayId=627c12d8edbc2a75333b9185&contentId=625553bfedbc2a05aee4082b#62a0e082edbc2a2143645b35

If you want an object in your room to make a sound (for example a fireplace to make crackling sounds.)

First, add an audio source component and set its spatial blend to 1 with a minimum distance of 0.25; then, add a ‘Play Quick Sound’ component and select an audio from the library to be played when the object is interacted with, specifying that this action should be triggered by setting an object, using a click and drag remote, and calling the ‘Play Quick Sound’ function upon activation in the interactable events configuration

**7. Adding laser to remote:** https://learn.unity.com/tutorial/2-2-activation-events?missionId=62554d88edbc2a76a2748758&pathwayId=627c12d8edbc2a75333b9185&contentId=625553bfedbc2a05aee4082b#

You can see the laser when you want to turn on and off the tv on the remote. To do that you should:

First, add a component to the indicator light, then set the material color using a script, specifying the ‘Change Material Color’ function; next, make the indicator light interactable with XR Grabable, and upon activation of the object, change the material color to your preferred choice.

![upload_962532865640425d3d484bdb8797383b](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/e59a8a1f-f432-4d6d-8e97-b6f490681dd5)

**8. Adding sound to the remote:** https://learn.unity.com/tutorial/2-2-activation-events?missionId=62554d88edbc2a76a2748758&pathwayId=627c12d8edbc2a75333b9185&contentId=625553bfedbc2a05aee4082b#

By this way you can make your remote to make a “click” sound grabbing and pushing the button.
To enable the remote to emit sound, start by adding an AudioSource component to the Remote object and set the Spatial Blend property to ‘1’ for full 3D audio capability. Next, give the remote the ability to play a sound by adding a ‘Play Quick Sound’ component and assigning an audio clip from the Course Library > Audio folder to the Sound property. Locate the ‘Activated’ event at the bottom of the remote’s XR Grab Interactable component, expand the Interactable Events fold-out, and in the Activated event, add a new action by clicking the ‘+’ button. Drag and drop the Remote object into the empty Object slot to access its components, then select ‘Play Quick Sound > Play ()’ from the No Function drop-down menu to play a sound when the remote is activated.

**9. How to add a video to a screen:**

For example if you want to add a video to the tv. First you will need a video ready in your assets file. Here you should pay attention that the tv asset and screen asset are different so you need to add it to the screen and not to TV.

To enable the TV to emit 3D audio, first, select the ‘Screen’ child object of the Television in the Hierarchy, then add an Audio Source component and set the Spatial Blend property to ‘1.0’ for full 3D audio. Next, allow the TV to play video by adding a Video Player component to the ‘Screen’ child object, and change the Material Property to ‘_BaseMap’ (instead of ‘_MainTex’) to project the video to its material. To add additional video control functionality, add a ‘Play Video’ component to the ‘Screen’ child object, and select the ‘Play At Start’ checkbox to play the video automatically. Finally, in the ‘Play Video’ component, expand the Video Clips fold-out, set the list Size property to 1, press Enter to reveal an empty Video Clip slot, and assign one of the videos from the Course Library > Videos to the Video Clip property.

![upload_0e6b5bb93f430ea507a8e69ee548c69e](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/828650df-fabd-435f-8152-7b702ba93018)

![upload_19d6e3f463492f576b370c531ba65388](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/5403f79f-8e38-45ca-a189-83bb651be584)

**10. How to make pop-up UI windows:**

![upload_ad39b199458b71e788ef68a786af699c](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/e2fd6805-b56f-48cf-aead-c238440a204c)

UI windows are generally used at the beginning of games, when you want to provide information or for features such as moving from one scene to another. It is possible to use these windows within the Unity program. They can be created in many sizes, colors and shapes. These UI functionalities empower developers to generate content tailored for a range of device screen sizes while also ensuring that UI elements remain neatly arranged and visible within the Game view

https://learn.unity.com/tutorial/working-with-ui-in-unity - You can go to this link for more detailed information about UI Windows.

To create a canvas: Right click on your mouse. Select UI, then you will see the option “Canvas” you can create a canvas really quick from here. By repeating the same procedure you can also add “Text”, “Text Mesh Pro” and “Button” options to your canvas. Also you can play with the proportions.

**11. To make a pop-up window disappear after pushing the button**

Adding a button was described earlier. After adding it, go to “on click” and you can add events
When adding event drag the canvas to the select object window and from the function window select game object, now when the button is clicked it will be invisible.

![upload_871aabd0152a30d8fc4d649621c41869](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/5b76ac1d-23d8-44ed-83e9-9b12c9ad7fcf)

**12. To make a pop-up window appear when pushing another button or go near an object**

If you want to trigger the canvas when you push a button or go near a door etc. First it is very important to add colliders to both main camera ( you ) and the other game object that will be used to trigger the canvas. Let’s say our game object is the door now. You need to add the door your c# script. That script should have the information about colliders and when something will be triggered (you can see the code I used for that) and you can use a special command called “ OnTriggerTouched.Invoke();”’ this enables you to add events to the door. This basically means when you touch the door …… event will happen. You can add as many events as you like in my case I added the event “ On Trigger Touched” You should drag and drop your canvas to the select object button and you should select function “ game object —-> set active” Now when you get close to the door you should be able to see the canvas pop up. Be sure that the canvas is not active on inspector. And if any error happens watch out for the rigid bodies. One of your game objects should have a rigid body ( like my door has a rigid body) but not my main camera.

![upload_373961450b7d2c053bba292dad36d319](https://github.com/CNVPLab/UNITY-CHEAT-SHEET/assets/144914829/a30f0502-1b7a-4869-a0d9-2f51db4ff5eb)

Example script for the door:

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.Events;

public class DoorCheck : MonoBehaviour
{

public UnityEvent OnTriggerTouched;

private void OnTriggerEnter(Collider other)
{
    if (other.CompareTag("MainCamera"))
    {
        Debug.Log("MainCamera touched the door");

        OnTriggerTouched.Invoke();

    }

}
}

**NOTE:** If you want to have a pop-up window connected to another pop-up window:

Right click on canvas, then select UI and add another button, then make the initial canvas invisible. Now to make the invisible canvas visible when the new button is triggered, select the new button and assign it event, in event drag the old invisible canvas.

If you want to see the canvas once the VR has started then you should select world space on render mode! If not you will only see it in the game scene and not in VR.

**13. For something to pup-up when you teleport to an area**

Under teleportation area there is custom reticle. You can use the custom reticle for pop-up screens.

**14. In order to get notifications from consol when something is touched or interacted in someway**

Both the game object and the XR Rig and main camera should have colliders. You are supposed to add these colliders from the “Add component” feature. Also for these interactions at least one of these things should have a rigid body. But not both of them. Then you have to create a script. You should add this script to your game object. With a code similar to given below:

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RemoteInteraction : MonoBehaviour
{
// This variable will store whether the remote has been touched
private bool hasTouchedRemote = false;

private void OnTriggerEnter(Collider other)
{
    // Check if the object that entered the trigger zone has the "Remote" tag
    if (other.CompareTag("Remote"))
    {
        // Check if the remote hasn't been touched yet to avoid multiple messages
        if (!hasTouchedRemote)
        {
            Debug.Log("You touched the remote");
            hasTouchedRemote = true; // Set to true to prevent further messages
        }
    }
}

public void OnGrabbed()
{
    Debug.Log("You grabbed the remote.");
}

public void OnReleased()
{
    Debug.Log("You released the remote.");
}
}

After that you should add component - grab xr interactable - select to the game object, in this case it is remote. Doing this is helpful because you can add many events as you like. You should add select and do it run time only. Then you should drag the script you have to the none (object) part.

**15. To get the data of rotation and position:**

First you need to be able to see that information on console,you should write a script. To do that you need a code like this:

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PrintTransformData : MonoBehaviour
{
private Transform _transform;

private void Start()
{
    // Get the Transform component of the GameObject
    _transform = transform;
}

private void Update()
{
    // Get rotation and position data
    Vector3 rotationEulerAngles = _transform.rotation.eulerAngles;
    Vector3 position = _transform.position;

And to be able to save it to a distinct file:

// Create a formatted string with rotation and position data
string dataAsString = $“Rotation: {rotationEulerAngles}, Position: {position}”;

   // Write the data to a file
    System.IO.File.AppendAllText(@"C:\Users\bmsuser\Desktop\GetPositionData.txt", dataAsString + "\n");
}

You can just add the code for saving to the end of the code that is for the console.

**16. To be able to see when someone grabbed something ( with the exact timing):**

You need to have System.DateTime class in your code to get the current time and include it in your log message. For example there is a code to know if someone has grabbed / released the remote and when:

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using System;

public class RemoteInteraction : MonoBehaviour
{
// This variable will store whether the remote has been touched
private bool hasTouchedRemote = false;

private void OnTriggerEnter(Collider other)
{
    // Check if the object that entered the trigger zone has the "Remote" tag
    if (other.CompareTag("Remote"))
    {
        // Check if the remote hasn't been touched yet to avoid multiple messages
        if (!hasTouchedRemote)
        {
            DateTime currentTime = DateTime.Now;
            string logMessage = $"You touched the remote at {currentTime.ToString("HH:mm:ss")}";
            Debug.Log(logMessage);
            hasTouchedRemote = true; // Set to true to prevent further messages
            SaveInstructions(logMessage);
        }
    }
}

public void OnGrabbed()
{
    DateTime currentTime = DateTime.Now;
    string logMessage = $"You grabbed the remote at {currentTime.ToString("HH:mm:ss")}";
    Debug.Log(logMessage);
    SaveInstructions(logMessage);
}

public void OnReleased()
{
    DateTime currentTime = DateTime.Now;
    string logMessage = $"You released the remote at {currentTime.ToString("HH:mm:ss")}";
    Debug.Log(logMessage);
    SaveInstructions(logMessage);
}

private void SaveInstructions(string instruction)
{
    List<string> lines = new List<string>();
    lines.Add(instruction);
    System.IO.File.AppendAllLines(@"C:\Users\bmsuser\Desktop\score2.txt", lines);
}

**SOME SOLUTIONS TO SOME ERRORS:**

**If you cannot see your project via oculus but you can see other projects:**

Edit > Project Settings > XR Plug-in Management. Also enable Initialize XR on Startup in that same settings screen. If you are using OpenXR instead of Oculus, you may need to change the OpenXR Runtime (Editor Instance Only) value to use Oculus if your system default is another provider.

**If your colliders don’t seem to interact:**

Watch out for the rigid bodies!

- IRMAK KALKAN
- https://hackmd.io/@irmakkalkan

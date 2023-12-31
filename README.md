# Crime Scene Visualizing Through HoloLens

We suggest the application that novice user can replicate a crime scene by timeline
And Share it with other device users

## Motivation

Holograms offer more intuitive way for understanding the scene.
So by using this advantages with the Mixed Reality Hologram device HoloLens.
We suggest the application that novice user can replicate a crime scene by timeline
and Share it with other device users.

## Objective

We suggest the application that novice user can replicate a crime scene by timeline
And Share it with other device users.

![objective1](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/objective1.png)

## Functionality & Implementation

### Donwload the 3D object from web server

To Allow User to get the object they need at runtime. Runtime Object Loader is needed for user to download the 3D object in the server.
Previously when loading new data, User must upload the data to the Unity app directly and depoly a new one. To solve this problem, a function was added to dynamically download desired data at runtime and share it with users. By using Unity Asset Trilib 2, a Cross-Platfrom runtime 3D model importer, We allowed users to dynamically load FBX, OBJ files. after loading the 3D Object. a scripts was created to add features such as `Near Grabable`. Additionally, corresponding photon scripts are added to complement the functionality of the multi-user experience.

### Basic Figure of Scripting

### Set the 3D object position and add animation to create a scene

To manipulate the object position where user wanted position. and add animation at the targeted object we added these 5 c# scripts as soon as the loading of the object is finished

- Mesh & Colider

A script that finds the center of an object mesh and creates a collider that matches the size of the object.

- Grab Notice

Script that automatically detects when a ray emitted by the user's hand and an object collide

- Photon Transformview

A script that synchronizes size, rotation, position, etc. in real time when sharing an object through Photon

- Object Manipulation

Scripts that allow users to deform objects with one or two hands, such as moving and resizing them

- NearInteraction Grabbable

A script that detects if the user has grabbed or moved a point in space.

![basic_figure](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/basic_figure.png)

### Add Description of the screen and proceed the scene by order

To use the timeline function, it is first determined whether the object is in contact with the HoloLens user's hand. The contacted object will now be designated as the target to which animations will be added, and whenever the user dynamically adds an animation, the location of the object and the animation progress will be saved in the `Animation[Number].txt` file. In the order of user interactions sequence. And the .txt File is stored on the server. Afterwards, the timeline function can be executed by calling the .txt file at any time.

<img width="830" alt="스크린샷 2023-06-17 오후 6 32 47" src="https://github.com/Gachon-2022-23-Graduation-3-6/Crime-Scene-Visualizing-Through-HoloLens/assets/97601109/08bcf0be-2455-4317-a36f-6a43a5024df5">

#### Set the 3D object position and add animation to create a scene , Add Description of the screen and proceed the scene by order functionality

was accepted in SIGGRAPH ASIA poster section
https://youtu.be/hPORPrW5qts

### Multi Device Sharing

Using Unity Photon a multi a networking framework for realtime Unity multiplayer games and applications. We built a network to share the Crime Scene Visulization Space. Photon also supports RPC, or Remote Procedure Calls, to specify a separate address space for remote control. So every user can join the process of Moving, Scaling , Adding Animation. To use a remote request in the method, a photon view script must be added to the target object to detect RPC proximity candidates. Thus, photon view script was remotely added to 3D objects right after it has been downloaded.
<img width="864" alt="스크린샷 2023-06-17 오후 4 32 44" src="https://github.com/Gachon-2022-23-Graduation-3-6/Crime-Scene-Visualizing-Through-HoloLens/assets/97601109/052cc940-3ca8-45f5-9447-ada54d24e990">

### System UI

![system_ui](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/system_ui.png)

![system_ui2](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/system_ui2.png)

## Main Features

1. **Timeline**<br><br>
   We basically load the text file from server to read the text file that contains the event of case, and to each event, we show a brief animation with the according action. Furthermore, we can make a simple animation while running Hololens by action buttons.

<p align="center">
     <img src="https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/timeline.png" width="400">
   </p>

2. **Posting**<br><br>

<p align="center">
     <img src="https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/posting.png" width="400">
   </p>

3. **Highlighting**<br><br>
   We have implemented a highlighting feature that emphasizes the outline of the target object. This is accomplished by creating an additional object that is 1.1 times the size of the target, and overlapping it with the original object to highlight its outline.

   <p align="center">
     <img src="https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/highlight.png" width="400">
   </p>

## TEAM

<table align="center">
    <tr>
        <td align="center"><b>김한뫼</b></td>
        <td align="center"><b>박재준</b></td>
        <td align="center"><b>이도경</b></td>
        <td align="center"><b>이준혁</b></td>
        <td align="center"><b>한승일</b></td>
    </tr>
    <tr>
        <td align="center">201835441</td>
        <td align="center">201735833</td>
        <td align="center">202035359</td>
        <td align="center">201835499</td>
        <td align="center">201835544</td>
    </tr>
    <tr style="background-color: white;">
        <td align="center">
            <code>Functionality</code><br><code>Timeline Animation</code>
        </td>
        <td align="center">
            <code>Modeling</code><br><code>######</code>
        </td>
        <td align="center">
	    <code>Modeling</code><br><code>######</code>
        </td>
        <td align="center">
	    <code>Functionality</code><br><code>Posting</code>
        </td>
        <td align="center">
            <code>Functionality</code><br><code>Highlighting</code>
        </td>
    </tr>
</table>

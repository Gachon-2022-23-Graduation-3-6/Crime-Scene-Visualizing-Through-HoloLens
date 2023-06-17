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


### Multi Device Sharing 
Using Unity Photon a multi a networking framework for realtime Unity multiplayer games and applications. We built a network to share the Crime Scene Visulization Space. Photon also supports RPC, or Remote Procedure Calls, to specify a separate address space for remote control. So every user can join the process of Moving, Scaling , Adding Animation. To use a remote request in the method, a photon view script must be added to the target object to detect RPC proximity candidates. Thus, photon view script was remotely added to 3D objects right after it has been downloaded. 
<img width="864" alt="스크린샷 2023-06-17 오후 4 32 44" src="https://github.com/Gachon-2022-23-Graduation-3-6/Crime-Scene-Visualizing-Through-HoloLens/assets/97601109/052cc940-3ca8-45f5-9447-ada54d24e990">


### System UI

![system_ui](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/system_ui.png)

![system_ui](https://github.com/SevngIl/Crime-Scene-Visualizing-Through-HoloLens/blob/main/system_ui2.png)

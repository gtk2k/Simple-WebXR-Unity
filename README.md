![SimpleWebXR](/images/banner.png)


# What is SimpleWebXR ?
SimpleWebXR is a lightweight library that exposes the WebXR javascript API in your C# Unity code.
Thus, after a Unity WebGL build, your app can do augmented or virtual reality in the browser.

:warning::warning::warning: **This project is under development...** :warning::warning::warning:

---

# Compatible browsers
Works on :
- [Google Chrome](https://play.google.com/store/apps/details?id=com.android.chrome) on Android (:warning: a secure https connection is required)
- [Edge](https://docs.microsoft.com/fr-fr/windows/mixed-reality/new-microsoft-edge) on Windows 10 for Mixed Reality Headsets
- [Firefox Reality](https://www.microsoft.com/en-gb/p/firefox-reality/9npq78m7nb0r?activetab=pivot:overviewtab) on Hololens 2
- [Mozilla WebXR Viewer](https://apps.apple.com/fr/app/webxr-viewer/id1295998056) on iOS
- [Oculus Browser](https://developer.oculus.com/webxr/?locale=fr_FR) on Oculus Quest
- [Firefox emulator](https://addons.mozilla.org/fr/firefox/addon/webxr-api-emulator/) on desktop
- [Chrome emulator](https://chrome.google.com/webstore/detail/webxr-api-emulator/mjddjgeghkdijejnciaefnkjmkafnnje) on desktop

Work in progress for :
- [Firefox Reality](https://www.oculus.com/experiences/quest/2180252408763702/?locale=fr_FR) on Oculus Quest
- [Helio Browser](https://developer.magicleap.com/en-us/learn/guides/webxr-overview) on Magic Leap
- don't hesitate to tell me about browsers you've tried...

---

# Integration examples

## MRTK
[Mixed Reality Toolkit](https://github.com/microsoft/MixedRealityToolkit-Unity) is a Microsoft-driven project that provides a set of components and features, used to accelerate cross-platform MR app development in Unity. It supports Hololens, Windows Mixed Reality headset, OpenVR, Ultraleap, Mobile devices and now **WebXR** !

The files in directory [/Assets/SimpleWebXR/Scripts/MRTK-Providers](https://github.com/Rufus31415/Simple-WebXR-Unity/tree/master/Assets/SimpleWebXR/Scripts/MRTK-Providers) add WebXR capabilities to MRTK with the following functions: controller tracking, **hand** tracking, hand ray, index pointer, grip pointer and spatial pointer. Teleportation could be added.

LIVE DEMO : 
- Hand interaction : [▶️ https://rufus31415.github.io/webxr/MRTK-HandInteraction](https://rufus31415.github.io/webxr/MRTK-HandInteraction/)
- Color picker : [▶️ https://rufus31415.github.io/webxr/MRTK-ColorPicker](https://rufus31415.github.io/webxr/MRTK-ColorPicker/)
- Elastic menus : [▶️ https://rufus31415.github.io/webxr/MRTK-ElasticSystem](https://rufus31415.github.io/webxr/MRTK-ElasticSystem/)
- Hand coach : [▶️ https://rufus31415.github.io/webxr/MRTK-HandCoach](https://rufus31415.github.io/webxr/MRTK-HandCoach/)
- Hand menu : [▶️ https://rufus31415.github.io/webxr/MRTK-HandMenuLayout](https://rufus31415.github.io/webxr/MRTK-HandMenuLayout/)
- Material gallery : [▶️ https://rufus31415.github.io/webxr/MRTK-MaterialGallery](https://rufus31415.github.io/webxr/MRTK-MaterialGallery/)
- Scrolling menus : [▶️ https://rufus31415.github.io/webxr/MRTK-ScrollingObjectCollection](https://rufus31415.github.io/webxr/MRTK-ScrollingObjectCollection/)
- Solvers : [▶️ https://rufus31415.github.io/webxr/MRTK-Solver](https://rufus31415.github.io/webxr/MRTK-Solver/)

| Hololens 2 | Oculus Quest |
|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-hololens.gif">|  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-quest.gif" height="225px">|

| iOS | Emulator |
|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-ios.gif">|  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-simulator.gif" height="225px">|

Fun **simulation** features in browser, you can simulate your Hololens, like in Unity editor :

| Mouse interaction | Hand simulation (MAJ/SPACE and T/Y) | Scene navigation |
|:-------------------------:|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-mouse.gif"> |  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-hand-simulation.gif">|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/mrtk-move.gif">|


Unity version : 2018.4.21f1
MRTK version : 2.5

---

## Simple hand tracking
SimpleWebXR supports hand tracking. This example displays a sphere on each joint of the detected hands. The radius of this sphere is given by the device. It was tested on Hololens 2 and Oculus Quest.

You need to set flags to enable hand tracking. In firefox reality, open setting panel and set ```dom.webxr.hands.enabled``` to true. In Oculus Browser, visit chrome://flags/ and enable #webxr-hands.


LIVE DEMO : [▶️ https://rufus31415.github.io/webxr/HandDetectionExample/](https://rufus31415.github.io/webxr/HandDetectionExample/)

<p align="center"><img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/hand-tracking.gif" height="150px"/></p>


---

## Spectator view
When wearing a HoloLens, we often forget that a person who does not have it on is unable to experience the wonders that we can. Spectator View allows others to see on a 2D screen what a HoloLens user sees in their world.
[This Microsoft project](https://github.com/microsoft/MixedReality-SpectatorView) is a native spectator view app for iOS and Android. But here, the spectator view is in your browser. WebXR is optional because you can walk around the Hololens space with the keyboard and mouse.

LIVE DEMO : [▶️ https://rufus31415.github.io/sandbox/simple-webxr-spectator/](https://rufus31415.github.io/webxr/SpectatorViewWebXRClient/)

DOWNLOAD : [⏬ Hololens 2 ARM appx and dependencies](https://github.com/Rufus31415/Simple-WebXR-Unity/tree/master/Builds/SpectatorViewHololens2Server)
 
Scene for Hololens 2 (MRTK) : [/Assets/SimpleWebXR/Scenes](https://github.com/Rufus31415/Simple-WebXR-Unity/tree/master/Assets/SimpleWebXR/Scenes)/
SpectatorViewHololens2Server.unity. To compile, this scene, do not use UWP SDK 19041, it has socket server issues.

Unity scene for Mobile (WebGL) : [/Assets/SimpleWebXR/Scenes](https://github.com/Rufus31415/Simple-WebXR-Unity/tree/master/Assets/SimpleWebXR/Scenes)/
SpectatorViewWebXRClient.unity

Unity version : 2018.4.21f1

| Mobile | Move in Hololens space with mouse/keyboard or Follow user head |
|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/spectator-view-ios.gif" height="150px"/>|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/spectator-view-desktop.gif" height="150px"/>|

Comparison with Microsoft solution :

|| Simple WebXR Spectator view | Microsoft native spectator view |
|:-------------------------:|:-------------------------:|:-------------------------:|
| iOS | YES : WebXR Viewer, Safari or Chrome (move in Hololens space with touch screen) | YES (ARKit) |
| Android | YES (Chrome) | YES (ARCore) |
| Desktop | YES, you can move in hololens space with mouse and keyboard  | NO |
|Communication Mobile/Hololens| Websocket | WebRTC |
|FPS| 10 | 60 |
|Calibration| Touch the screen | Scan a QR Code |
|Experimental| YES | NO |


## Paint example
This is a very basic example on how to use Simple WebXR. It uses Unity Line Renderer to draw lines in space with your hands/controllers.

LIVE DEMO : [▶️ https://rufus31415.github.io/webxr/PaintExample/](https://rufus31415.github.io/webxr/PaintExample/)

| Android | Hololens 2 | iOS | Quest | Emulator |
|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-android.gif"> |  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-hololens.gif">|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-ios.gif">|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-quest.gif">  |  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-simulator.gif">|

<p align="center">
  <a href="https://youtu.be/cUkAdI4lJOA">
    <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/paint-youtube.png" height="150px"/>
  </a>
</p>

Sources are [here](https://github.com/Rufus31415/Simple-WebXR-Unity/blob/master/Assets/SimpleWebXR/Scripts/PaintExample/PenController.cs)

Unity version : 2018.4.21f1

---

## XR CAD file viewer
Opens 45+ 3D CAD formats in your browser (FBX, STEP, OBJ, Collada, GLTF, OnShape, ...) and now, view them in VR/AR with WebXR !

LIVE DEMO : [▶️ https://rufus31415.github.io/sandbox/3d-viewer](https://rufus31415.github.io/sandbox/3d-viewer)

<p align="center"><img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/3d-viewer.gif" height="200px"/></p>


[work in progress...](https://github.com/Rufus31415/react-webgl-3d-viewer-demo)

---


## XRTK
The [Mixed Reality Toolkit](https://github.com/XRTK/XRTK-Core)'s primary focus is to make it extremely easy to get started creating Mixed Reality applications and to accelerate deployment to multiple platforms from the same Unity project.

LIVE DEMO : [▶️ https://rufus31415.github.io/sandbox/simple-webxr-xrtk-solvers/](https://rufus31415.github.io/sandbox/simple-webxr-xrtk-solvers)
| iOS | Emulator |
|:-------------------------:|:-------------------------:|
|<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/xrtk-solvers-ios.gif" height="225px"> |  <img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/xrtk-solvers-simulator.gif" height="225px">|

[work in progress...](https://github.com/Rufus31415/WebXR)

---

## Unity XR Plugin
Unity has a unified plug-in framework that enables direct integrations or XR for multiple platforms Why not adding WebXR...

[Later...]

---

# How to use
# Installation
Just add these 3 files in your Unity Asset folder, then add SimpleWebXR MonoBehavior on a game object in your scene.
- [SimpleWebXR.cs](https://github.com/Rufus31415/Simple-WebXR-Unity/blob/master/Assets/SimpleWebXR/Plugins/SimpleWebXR.cs): Mono Behaviour that displays the "Start AR" button and communicates with javascript. This behavior should be in your scene.
- [SimpleWebXR.jslib](https://github.com/Rufus31415/Simple-WebXR-Unity/blob/master/Assets/SimpleWebXR/Plugins/SimpleWebXR.jslib): Javascript plugin that is included in the application and that makes the link between the Unity engine and the WebXR session. It displays the rendering and obtains the positions and characteristics of the camera.
- [SimpleWebXR.jspre](https://github.com/Rufus31415/Simple-WebXR-Unity/blob/master/Assets/SimpleWebXR/Plugins/SimpleWebXR.jspre): Javascript plugin executed before the application that initializes a number of things.

# Compilation
The project must be compiled in WebGL, otherwise SimpleWebXR will has no effect.
I've noticed that big scenes like MRTK don't work on mobile anymore when compiled with Unity 2019.4. That's why I recommend Unity 2018.4.
I haven't dug into the reason yet.

# Runtime
When compiled as a WebGL app, if the browser is WebXR compatible, it will display a "Start AR" button on your canvas.
You don't need a specific WebGL Template, so your can keep using yours.

# Get started
## SimpleWebXR MonoBehavior
To begin with, **it is recommended to have the SimpleWebXR component active in the scene** at all times. I recommend you to create a root game object "WebXR" which contains only the SimpleWebXR component.

This one will manage two things:
- It will display the "Start AR" or "Start VR" button at the bottom of the canvas, and will start the session if the user presses it.
- It will call to each frame the function ```SimpleWebXR.UpdateWebXR()```.

However SimpleWebXR may not be present as a component game object in the scene, but you will have to **call the static function ```SimpleWebXR.UpdateWebXR()``` by yourself at each frame**.

You can also add this component by code by calling the static method ```SimpleWebXR.EnsureInstance()```. The SimpleWebXR component does not exist, it will create it on a root game object "WebXR".

<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/monobehavior.png"/>

## Start/Stop immersive session
If the SimpleWebXR component is active in the scene, it will automatically display a button that allows the user to start an immersive WebXR session.

You can hide this button by checking the field ```Hide Start Button```.

In addition, you can at any time in the main thread start an immersive session from your code via the static method :

``` cs
SimpleWebXR.StartSession();
```

You can also end an immersove session by calling :
``` cs
SimpleWebXR.EndSession();
```

In addition, the following static events are raised when an immersive session starts or stops :
``` cs
⚡️ UnityEvent SimpleWebXR.SessionStart
⚡️ UnityEvent SimpleWebXR.SessionEnd

SimpleWebXR.SessionStart.AddListener(OnSessionStart); // OnSessionStart() is a method in your code called when a session starts
SimpleWebXR.SessionEnd.AddListener(OnSessionEnd); // OnSessionEnd() is a method in your code called when a session starts
```

## Check AR/VR supported
To find out if the current browser supports WebXR, you can call these static methods from anywhere in your code:
``` cs
bool isARSupported = SimpleWebXR.IsARSupported(); // 'immersive-ar' feature is supported
bool isVRSupported = SimpleWebXR.IsVRSupported(); // 'immersive-vr' feature is supported
```
Warning: the result of the request is asynchronous in javascript. It may be necessary to call these functions several times or to wait to get the result. For example, the SimpleWebXR component requests the capabilities at each frame in the OnGUI() function.

## Check if a WebXR Session is running
The static property ```SimpleWebXR.InSession``` indicates whether a WebXR immersive session is in progress.
``` cs
bool isInWebXRSession = SimpleWebXR.InSession;
```

## Eyes
On a smartphone and tablets, only one camera is required. But on HMD (head mounted headset), a different rendering is made for each eye, so there are two active cameras.

At the start of the session, the left eye is equal to ```Camera.Main```. If necessary a camera is created for the left eye. The characteristics of these cameras are modified at startup (clearFlags, background, clip planes, ...).

During a session, the pose and the projection matrix are updated when ```SimpleWebXR.UpdateWebXR()``` is called. 

The second camera (right eye) is destroyed at the end of the immersive session.

``` cs
Camera leftEye = SimpleWebXR.LeftEye; // == Camera.Main
Camera rightEye = SimpleWebXR.RightEye; // == null on smartphones and tablets
```

## Input controllers
The ```SimpleWebXR.LeftInput``` and ```SimpleWebXR.RightInput``` fields represent left and right controllers. On smartphones either of these input sources can be used (it depends on the browser) and corresponds to the place where the user touched the screen.

``` cs
WebXRInputSource leftInput = SimpleWebXR.LeftInput
WebXRInputSource rightInput = SimpleWebXR.RightInput
```

WebXRInputSource


## More documentation is coming...
<img src="https://raw.githubusercontent.com/Rufus31415/Simple-WebXR-Unity/master/images/bg.jpg"/>
...

# Useful WebXR content
- [https://immersive-web.github.io/](https://immersive-web.github.io/) : Many useful examples
- [https://www.w3.org/TR/webxr](https://www.w3.org/TR/webxr) : technical details of webxr
- [https://github.com/MozillaReality/unity-webxr-export](https://github.com/MozillaReality/unity-webxr-export) : a WebXR export plugin developed by Mozilla (much more complicated than this one, which is based on a js template and external js resources)
- [https://github.com/De-Panther/unity-webxr-export](https://github.com/De-Panther/unity-webxr-export) : A fork of Mozilla plugin that works in AR and VR (Btw, thanks to De-Panther for his useful help !).


# License: MIT 😘
[©Rufus31415](https://rufus31415.github.io)

See the [license file](https://github.com/Rufus31415/Simple-WebXR-Unity/blob/master/LICENSE) for details.

# Any questions ?
Feel free to contact me :
- Slack : https://holodevelopers.slack.com/team/U0120CVDUCV
- Discord : Rufus31415#2440
- Twitter : https://twitter.com/rufus31415
- Mail : rufus31415@gmail.com
- Open issue : https://github.com/Rufus31415/Simple-WebXR-Unity/issues


<details>
<summary></summary>
<img src="https://ga-beacon.appspot.com/UA-163892314-2/Simple-WebXR-Unity/">
</details>

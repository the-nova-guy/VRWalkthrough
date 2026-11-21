# VR Walkthrough (Meta Quest 3)

A basic VR environment built in Unity for Meta Quest 3. The user can explore a simple indoor space, move by teleportation, and pick up and drop objects using the controllers. Built with the XR Interaction Toolkit and OpenXR.

> Fill in the items in [square brackets] before you commit this file.

## Task checklist

| # | Requirement | Status |
|---|-------------|--------|
| 1 | Simple 3D indoor environment | Done: [room with N walls, furniture, baked lighting] |
| 2 | XR Origin set up with XR Interaction Toolkit | Done |
| 3 | VR controller tracking | Done: OpenXR with the Oculus Touch Controller Profile |
| 4 | Teleportation or continuous movement | Done: [teleportation / teleportation and continuous move] |
| 5 | Grab and release objects | Done: XR Grab Interactable on [number] objects |
| 6 | Test on Meta Quest 3 | Tested in the editor with a simulator; see **Testing** below |

## Deliverables

- **Unity project:** this repository
- **APK build:** see the [Releases page]([link to your release])
- **Screen recording:** [link to the release asset or Google Drive]

## Tech stack

- Unity **6000.0.51f1** (Unity 6), Universal Render Pipeline
- XR Interaction Toolkit **[version]** with Starter Assets
- XR Plugin Management and OpenXR Plugin **[version]**
- Target device: Meta Quest 3 (Android)

## What is in the scene

- An indoor room with a floor, walls, a ceiling, and furniture built from primitives, plus [second room / doorway if added]
- XR Origin (XR Rig) with a tracked headset and two tracked controllers, tracking origin mode set to Floor
- **Teleportation:** [floor / teleport areas] use a Teleportation Area, activated with the controller thumbstick
- [Optional] Continuous move and snap turn
- **Grab and release:** [number] props on the table with a Rigidbody, a Collider, and XR Grab Interactable, using velocity tracking, and thrown objects keep their momentum
- [Optional extras: haptics on grab, hover highlights, and so on]

## Controls

Defaults from the XR Interaction Toolkit Starter Assets. Adjust these if you changed the input actions.

| Action | Input |
|--------|-------|
| Teleport | [Push the thumbstick forward to aim, release to teleport] |
| Move | [Left thumbstick, if continuous move is enabled] |
| Turn | [Right thumbstick, snap turn] |
| Grab | Grip button |
| Release | Release the grip button |

## Testing

I did not have access to a Meta Quest headset while building this, so **the build has not been run on a Quest 3**. I tested in the Unity editor with the **XR Device Simulator**, which covered movement, teleportation, and grab and release. [Add this only if you used it: I also tried the Meta XR Simulator.]

The APK is configured for Quest 3:

- OpenXR enabled for Android, with the Oculus Touch Controller Profile
- Scripting backend IL2CPP, target architecture ARM64
- Minimum API level [29], graphics API [Vulkan / OpenGLES3]
- Project Validation passes with no warnings [confirm this]

If you have a Quest 3, you can install the APK with `adb install -r VRWalkthrough.apk`. The app appears in the library under Unknown Sources.

## How to open and run the project

1. Install **Unity 6000.0.51f1** with Android Build Support (OpenJDK, SDK, and NDK).
2. Clone this repository and open the folder in Unity Hub.
3. Open the scene `Assets/Scenes/[SceneName].unity`.
4. Press Play to test with the XR Device Simulator.
5. To build the APK, open **File > Build Profiles**, choose Android, and click **Build**.

## Project structure

```
Assets/
  Scenes/       Main scene
  Scripts/      [if any]
  Materials/    [if any]
  Samples/      XR Interaction Toolkit samples (Starter Assets, XR Device Simulator)
Packages/       Package manifest
ProjectSettings/
```

## Known limitations

- Not tested on a physical Quest 3 headset, so frame rate and comfort are unchecked
- Environment is built from primitives to keep the scene light for mobile hardware
- [Anything else you noticed]

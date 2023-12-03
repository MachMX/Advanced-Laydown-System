# Snek's Advanced Laydown System
A ChilloutVR's Laydown system. Animator based for maximum compatibility.
Mainly taken in mind for Desktop, 3-Point Tracking and 4-Point Tracking users to use as an extention for a laydown system that can dynamically change laydown animations, and even have more control for being able to sitdown and standup and for animations to change inbetween certain user defined threshold sets without relying 100% on mods while also being easily modifiable/expandable by anyone.

While this setup doesn't need mods at all, I recommend for 3 Point Tracking and 4 Point Tracking users the use of [Avatar Motion Tweaker](https://github.com/SDraw/ml_mods_cvr/tree/master/ml_amt#avatar-motion-tweaker) ([direct download link - can be outdated](https://github.com/SDraw/ml_mods_cvr/releases/download/r146/ml_amt.dll)) - with the use of the [CVRMelonAssistant](https://github.com/knah/CVRMelonAssistant/releases) a community and Developer moderated mod/plugin repository and mod installer - mainly to fix some IK issues and facilitating the usage of this package, but again not neccesary. On the future will release an even more involved setup that would address not needing mod usage with jsut aniamtor logic.

Setup compatible from the get-go with [Action Menu mod](https://github.com/dakyneko/DakyModsCVR/releases), for an easy Pie-Menu experience (make sure to read how to use it or will not work if you want to use this), also available on the [CVRMelonAssistant](https://github.com/knah/CVRMelonAssistant/releases) collection.

**Tldr**: Easy laydown for CVR.

# Requirements
- Unity 2021.3.23f1
- [The latest CCK available](https://developers.abinteractive.net/cck/setup/)

# Setup
ChilloutVR's doesn't have an overly involved setup addon such a VRCFury, but honestly it's not really needed for this. Still, many new users might have difficulty understanding or even not knowing where/how to setup this, so I will explain it the best as I can below. There are 3 Main Parts, the [Layer/Parameter Setup](https://github.com/MachMX/Sneks-Advanced-Laydown-System/tree/main#layerparameter-setup) - for the Animator setup, the [Advanced Settings Menu Setup](https://github.com/MachMX/Sneks-Advanced-Laydown-System/tree/main#advanced-settings-menu-setup) - for the ingame menu connection, and the [Parameter Stream Setup](https://github.com/MachMX/Sneks-Advanced-Laydown-System/tree/main#parameter-stream-setup) - for the dynamic Parameters to work.

## Layer/Parameter Setup
There's 3 Multiple ways to make the Layer/Parameter setup, I absolutely recommend the RATS Method, but it's not the only way.

### Lazy Method (Not Recommended, can cause issues with Parameter setups)
FYI- This way is fast and works with default Unity/CCK and no extentions, but I don't recommend it still due to how Unity Animator Editor can be buggy and not copy Parameters or Parameter Conditions within the Transitions between layers. So be warned.
- You start by going into Unity inside the included Animator Controller. ![Structure](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/c252ada0-6dbf-4393-8d69-5f06c6e60f9f)

- Go and copy the included Layers into your own Avatar's Animator Controller ![Copy Layer Type1 1](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/526ba8c7-4501-4054-bf05-d5d03d13e336)

- Seriously, make sure you copy both the Laydown and Laydown Compare layers only ![Copy Layer Type1 2](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/187b5179-616c-4ed1-85fc-9812a89d8b21)

- After copying them into your Avatar's Animator Controller, make sure the Parameters were also copied over, Unity is dumb and there is a coin flip it will or not copy these, so manually add them to make sure you have them right, it should fix most issues if they have the exact same name as exact Parameter type. ![Copy Layer Type1 3](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/bb586d15-fea6-426b-9330-fa00f97d0863)


### Simple AAS Method (Works and easy, can be destructive)
- Install [Simple AAS](https://github.com/NotAKidOnSteam/SimpleAAS/) (more info under the [Addons Recommendation](https://github.com/MachMX/Sneks-Advanced-Laydown-System/tree/main#addon-recommendation) section below).

- Make an empty game object on your scene, search for a component called **"SimpleAAS"**, and basically copy the setup on this image step and press *"Compile"*, after a short moment it will merge Controllers ![Copy Layer Type2 1](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/7cad7b18-9cc3-47b1-80f1-d189e911cb75)

- Now with your new Controller, just set it up correctly to your **CVR Avatar's** Animator/Animator Override sections. New controller found inside *Assets\NotAKid\SimpleAAS.Generated\Controllers* normally. ![Copy Layer Type2 2](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/22430e61-7c6e-4dc2-a460-429d783c5e7b)


### RATS Method (Recommended, simple, fast, failsafe, nondestructive)
- Install [RATS](https://github.com/rrazgriz/RATS/releases) Unity Package and [Harmony for Unity Editor!](https://github.com/rrazgriz/harmony-vpm/releases/) Unity Package into your project, works on Unity Editor 2021 without any issues. (more info under the [Addons Recommendation](https://github.com/MachMX/Sneks-Advanced-Laydown-System/tree/main#addon-recommendation) section below).

- Go to the included Animator Controller ![Structure](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/c252ada0-6dbf-4393-8d69-5f06c6e60f9f)

- Copy Layers from included Controller ![Copy Layer Type3 1](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/04ea8414-7433-4bc7-be45-313d3b938124)

- Paste Layers into your Avatar's Controller ![Copy Layer Type3 2](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/e360a22e-3427-4a2a-8bb6-e87f21f85226)

- Now it has copied both the layers and parameters

## Advanced Settings Menu Setup
- In order to have the ingame recognize the Laydown system, just drag the Example Setup into the scene ![Structure](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/c252ada0-6dbf-4393-8d69-5f06c6e60f9f)

- Under the *CVRAvatar/Advanced Settings there's gonna be a Triangle on the right side of the Inputs section, click on that and jsut copy/paste all of the settings into your own Avatar's Advanced Settings ![Copy 1](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/27bf9e1a-32d0-4b60-981b-eb515a6d0e28)

- ![Copy 2](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/3f0ec90c-110a-4d6b-a8de-29627b57ceae)


## Parameter Stream Setup
- Finally for the **#AUpright** parameter to be dynamically updated, we are gonna copy/add the included Parameter Stream from the Exampel Setup included. Just follow the images and you will get it. If you already have a Parameter Stream included on your Avatar, just add the value as it appears into your own Parameter Stream. ![Structure](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/c252ada0-6dbf-4393-8d69-5f06c6e60f9f)
- ![Copy PS1](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/d569442e-d7f9-49f5-bb03-a78f5ac1cb60)

- ![Copy PS2](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/e6932562-ecb0-42f6-afbf-52be419e29b2)

- ![Copy PS3](https://github.com/MachMX/Sneks-Advanced-Laydown-System/assets/15898823/3243c8de-1480-43ce-82f7-452f3fa80066)


# Addon Recommendation
You don't need this for the setup to work, but I highly recommend this addon's/extentions!

- [AASEmulator](https://github.com/NotAKidOnSteam/AASEmulator/) a simple in Editor ChilloutVR's Advanced Avatar Settings emulator that let's you test your animation's and your Animator Logic rapidly and easily.
- [CCK.BaseAnimatorPatch](https://github.com/NotAKidOnSteam/CCK.BaseAnimatorPatch) an alternative for ChilloutVR's base avatar animator that is easily extendable and with spot logic. (Also has some better animation configurations in my opinion :P )
- [SimpleAAS](https://github.com/NotAKidOnSteam/SimpleAAS/) a simple Unity Animator Controller merger, best used to combine multiple animators into 1! Also incredibly useful when porting avatars from other platforms into ChilloutVR!
- The unfortunately named [RATS](https://github.com/rrazgriz/RATS/releases), or (🐀 RATS - Raz's Animator Tweaks 'n' Stuff 🧀) for it's extention and bugfixes of the Unity Editor, can;t remark how useful this thing is, so use it! (specifically the Animator editor, which still hasn't been properly bugfixed by Unity even on Unity 2021...)
- [Harmony for Unity Editor!](https://github.com/rrazgriz/harmony-vpm/releases/) repacked by Rrazgriz and the [legend of Brrainz](https://github.com/pardeike/Harmony) for originally making it - without their help modding Unity Games (and Editor) wouldn't be the same as we know it now.


# Credit's and Inspirations:

- Dervali for their awesome [LaySitting Prefab](https://github.com/Dervali-git/VRC-Tips/blob/main/LaySittingPrefab.md) and animation resource!
- Lastation for their [NSFW GoLoco](https://github.com/LastationVRChat/NSFW-GoLoco) as inspiration and animation resource!
- Franada for their original [GogoLoco](https://github.com/Franada/gogoloco/releases) as an inspiration.

# License under MIT
"The MIT License is short and to the point. It lets people do almost anything they want with your project, like making and distributing closed source versions." -[https://choosealicense.com/](https://choosealicense.com/)

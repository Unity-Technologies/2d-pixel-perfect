# 2D Pixel Perfect

This repository contains samples of the 2D Pixel Perfect features to be used with Unity 2018.2b3 and newer.

## Getting Started

### Get the Unity Editor

To get started, download and install the latest Unity 2018.2 beta, here: https://unity3d.com/unity/beta-download

### Get the Package

These samples already include the necessary manifest in the Packages folder of the project.
If you want to activate these features in another project:

1. Find the manifest.json file in the Packages folder of your project.
2. Edit it to look like this:

```javascript
{
  "dependencies": {
    "com.unity.2d.pixel-perfect": "1.0.0-preview"
  },
  "registry": "https://staging-packages.unity.com"
}
```

1. Back in Unity, the package will be downloaded and imported. 
2. Done!

Find out more about packages here: **[Unity Package Manager](https://docs.unity3d.com/Packages/com.unity.package-manager-ui@1.8/manual/index.html)**

### Preview Feature Documentation
* **[Pixel Perfect Camera](https://github.com/Unity-Technologies/2d-pixel-perfect/blob/master/Documentation/2D%20Pixel%20Perfect%20Camera.md)**

## ❗️❗️❗️ Warning ❗️❗️❗️

**Project backward compatibility between Preview versions is NOT GUARANTEED. Always backup your project before updating the package. Preview features here are not production ready, please DO NOT use this package for your final production. Preview features may be discontinued/dropped.**


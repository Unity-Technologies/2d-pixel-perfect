2D Pixel Perfect 

# Overview

The **2D ****Pixel Perfect **package** **contains the **Pixel Perfect Camera **component which ensures your pixel art remains crisp and clear at different resolutions, and stable in motion.  

It is a single component that makes all the calculations needed to scale the viewport with resolution changes, removing the hassle from the user. The user can adjust the definition of the pixel art rendered within the camera viewport through the various component settings, as well preview any changes made directly in Scene view using the **Run in Edit Mode** function.

![image alt text](images/image_0.png)

The **Pixel Perfect Camera** gizmo in the Scene

Attach the **Pixel Perfect Camera **component to the main **Camera **GameObject in the Scene. The comears in **Game View**** **when the component is in effect; and the dotted boundiponent is represented by two green bounding boxes centered on the **Camera** gizmo. The solid green bounding box shows the visible area that appng box shows the **Reference Resolution.**

The **Reference Resolution** is the original resolution your Assets are designed for, its effect on the component's functions is detailed further in the documentation.

Before using with the component, first ensure your Sprites are prepared correctly for best results with the the following steps.

# Preparing Your Sprites

1. After importing your textures into the project as Sprites, set all Sprites to the same **Pixels Per Unit** value.

![image alt text](images/image_1.png)

2. In the Sprites' Inspector window, set their **Filter Mode** to 'Point'.

![image alt text](images/image_2.png)

3. Set their **Compression** to 'None'.![image alt text](images/image_3.png)

4. Follow the steps below to correctly set the pivot for a Sprite
 

    1. Open the Sprite Editor for the selected Sprite. 

    2. If Sprite Mode is set to Multiple and there are multiple Sprite elements, click on each of the elements to select it. The pivot point must be set for each Sprite element individually.

    3. Under the 'Sprite' settings, select *Custom* from the **Pivot **drop-down menu. Then select *Pixels* from the **Pivot Unit Mode **drop-down menu. This mode allows you to input pivot positions in pixels, and snaps the pivot point to pixel corners automatically when dragging the pivot into position.

![image alt text](images/image_4.png)

    4. Repeat step 4c for each individual Sprite element as needed.

# Snap Settings

To ensure the pixelated movement of Sprites are consistent with each other, follow the below steps to set the proper snap settings for your project.

![image alt text](images/image_5.png)

1. Open the **Snap Settings **(menu: Edit > Snap Settings...)

2. For **Move X/Y/Z**, set their values to 1/Asset Pixels Per Unit

3. Snap settings are not applied retroactively. If there are any pre-existing GameObjects in your Scene, select each of them and click *Snap All Axes* to apply the Snap settings

 

# Reference Table

![image alt text](images/image_6.png)
The component's Inspector window

<table>
  <tr>
    <td>Property</td>
    <td>Function</td>
  </tr>
  <tr>
    <td>Asset Pixels Per Unit</td>
    <td>Amount of pixels that make up one unit of the Scene</td>
  </tr>
  <tr>
    <td>Reference Resolution</td>
    <td>Original resolution Assets are designed for</td>
  </tr>
  <tr>
    <td>Upscale Render Texture
</td>
    <td>Enable to create a temporary rendered texture of the Scene close-to or at the Reference Resolution, which is then upscaled</td>
  </tr>
  <tr>
    <td>Pixel Snapping (unavailable when Upscale Render Texture is enabled)</td>
    <td>Enable this feature to snap Sprite Renderers to a grid in world space at render-time</td>
  </tr>
  <tr>
    <td>Crop Frame</td>
    <td>Crops the viewport with black bars, to match the Reference Resolution along the checked axis</td>
  </tr>
  <tr>
    <td>Stretch Fill
(available when both X and Y are checked)</td>
    <td>Enable to expand the viewport to fit the screen resolution while maintaining the viewport's aspect ratio.</td>
  </tr>
  <tr>
    <td>Run In Edit Mode</td>
    <td>Enable this to preview Camera setting changes in Edit Mode</td>
  </tr>
</table>


# Property Details

## Asset Pixels Per Unit

This value is the amount of pixels that make up one unit of the Scene. Match this value to to the **Pixels Per Unit **values of all Sprites** **within the Scene. 

## Reference Resolution

This is the original resolution your Assets are designed for. Scaling up Scenes and Assets from this resolution preserves your pixel art cleanly at higher resolutions.

## Upscale Render Texture

By default, the Scene is rendered at the pixel perfect resolution closest to the full screen resolution. 

Enable this option to have the Scene rendered to a temporary texture set as close as possible to the **Reference Resolutio****n**, while maintaining the full screen aspect ratio. This temporary texture is then upscaled to fit the full screen.

![image alt text](images/image_7.png)

The result is unaliased and unrotated pixels, which may be a desirable visual style for certain game projects.

## Pixel Snapping

Enable this feature to snap Sprite Renderers to a grid in world space at render-time. The grid size is based on the **Assets Pixels Per Unit** value. 

**Pixel Snapping **prevents subpixel movement and make Sprites appear to move in pixel-by-pixel increments. This does not affect any GameObjects' Transform positions.

## Crop Frame

Crops the viewport with black bars to match the Reference Resolution along the checked axis. Black bars are added to make the Game View fit the full screen resolution.

![image alt text](images/image_8.png)![image alt text](images/image_9.png)

Uncropped					     With only the Y axis checked

## Run In Edit Mode

Enable this to preview Camera setting changes in Edit Mode. This will cause constant changes to the Scene while active.

## Current Pixel Ratio

Ratio of the rendered Sprites compared to their original size. 


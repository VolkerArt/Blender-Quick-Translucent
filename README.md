# Blender-Quick-Translucent
A quick shader node group for adding translucent with some extra math for control

Examples
Hair cards, works for both Cycles and Eevee

![Ccyles](https://github.com/user-attachments/assets/8849cb13-aa9f-4cbf-889a-dd9c7b5404c0)

Cloth

Cycles with solidify. Seems faster to render than SSS and sometimes can offer more desireable results

![Cycles](https://github.com/user-attachments/assets/77ad4056-b0e0-44ad-bb86-bab539c5e4b0)

Eevee without solidify. Needs to be a plane for Eevee to work right.

![Eevee No Solidify](https://github.com/user-attachments/assets/e542d61c-e38d-4172-ae05-46678d4b69c1)

How it should be set up. **Value plugged into Thickness is extremely important for Eevee Next, make sure it's set to 0**

**IMPORTANT UPDATE** If you have a mesh with thickness you may want to try and set the value to the approximate thickness of the mesh, or try a very low value like 0.001. I tested this with clothes and the result was very good.

![2024-10-22_22-35](https://github.com/user-attachments/assets/38894c20-a655-4fa6-8366-c2563ec6e3de)

NOTE: It's using Add Shader instead of Mix Shader

![2024-10-22_23-21](https://github.com/user-attachments/assets/65ec6ace-465f-43ea-86e3-4d4fc9bc2f25)

The Map Range node is set there for control, but I personally haven't needed it yet. Either way it clamps the value so it should be fine.

So how is this meant to be used? 
You plug it just like in the example image. You can have different colors, alphas, normals, but I wouldn't recommend using different alpha and normal. 
Color is there in the event of black hair, you can set the value on the translucent's color to be 0.1 or 0.01 or something and get translucence either way. After that, you're supposed to use the "Translucent multiplier" value to control the strength. The Saturation value is there cause I initially thought that hair lost a bit of its color when there's a light behind it but it looks like I may have been wrong. Either way I let it stay cause it can be useful to reduce the saturation. I am not sure how normal affects the translucent, it's optional either way. Alpha is also optional, meant to be used for hair cards or torn clothing.

This shader should work best with hair cards, clothing, grass, or anything that's a plane mesh in Eevee, but also in Cycles. It can also replace SSS for clothing in Cycles in some situations, depending on whether you like the result.

Keep in mind this isn't meant to be the most realistic solution, we fake it till we make it here.

Add the node group in an asset library, mark it as asset, then just press F3 and search for "TranslucentGroup" to add it quickly in a shader.

That's about it. If you like this, you can help me out by heading over to my patreon and giving me a little tip.
https://www.patreon.com/Volker3DSFW

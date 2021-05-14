---
title: "Cyberpunk Bar Environment WIP #2"
header:
  teaser: /assets/images/001_cyberpunk/03.png
---

The roof is finally back in! The proportions are feeling a lot better and I still managed to keep the majority of the shapes and framing that I originally intended. What’s more, things snap together perfectly now.

I’ve re-exposed the right side a little more in the composition as I feel it makes the scene look a little more unique at the cost of a slightly bigger space. I’ve also added some vertical lighting strips as I think it creates some interesting highlights and symmetry across the entire space.

{% include figure image_path="/assets/images/001_cyberpunk/03.png" alt="" caption="" %}

I’ve also tweaked the colours around my lights. I felt they could use a lot more punch and vibrancy. One thing I’m trying to be very conscious of here is keeping the attention on the main focal point. Adding that vibrancy, while taking one slight step away from realism, I think brings in more life to the scene.

I’m pretty happy with the contrast and balance that I have. A good test is to remove all the saturation in the scene. Here I notice a good amount of midtones and highlights but not too many darks. I think I can definitely push the contrast a lot more however as the middle of the image appears quite bright, compared to the rest of the image. This is mostly due to the fog which is drawing a lot of attention to the middle.

{% include figure image_path="/assets/images/001_cyberpunk/04.png" alt="" caption="" %}

I scaled back a lot of the other shapes in the ceiling from the initial blockout as I felt that it was starting to get a little too noisy. As I plan for those areas of the ceiling to be heavily reliant on trim textures, I decided to keep the things as simple as possible. I plan to make use of height maps and parallax occlusion mapping in order to create interesting shapes and add more depth to areas that feel empty.

{% include figure image_path="/assets/images/001_cyberpunk/05.png" alt="" caption="" %}

There does seem to be some odd behaviour with regards to Unreal’s vert snapping accuracy and there doesn’t seem to be an elegant solution to resolve it’s precision. Luckily we have grid snapping!

In the example below, I’m attempting to snap to a vert on the second major gridline on the right but the snapping seems to pick be picking up a camera that’s hidden around that area as well. It also appears that the vert that I’m attempting to snap to doesn’t even pass the collision hit.

There seems to be a kind of hit test to determine the vertices a user would be able to snap an object to. My guess is this is based on the position of the mouse cursor in screen space and that position gets calculated against the hit test previously mentioned.

{% include figure image_path="/assets/images/001_cyberpunk/06.gif" alt="" caption="" %}

Notice how as soon as my mouse cursor is over the camera, camera actor’s vertices immediately comes into view?

A solution for this might be to explore a socketing system. A socketing system means I will have the flexibility for it to potentially scale to encompass not just modular pieces but to props, effects and mesh decals.

It will also mean that the snapping points will be based around setting up locators in an external DCC, with finer minor adjustments made in engine if needed.

One more oddity that I’ve encountered seems to be with single sided objects being hidden when selected in an orthographic view. I haven’t yet been able to narrow down the root cause but there is potential for it there to be something broken with the mesh normals during at export time.

I’ll have to experiment with several different export settings to get to the bottom of this. If anyone has any suggestions or ideas, I would love to hear your thoughts!

{% include figure image_path="/assets/images/001_cyberpunk/07.gif" alt="" caption="" %}

That’s it for today. There’s a couple of smaller shapes that I think I can add back to the bar area and to the ceiling around it. Those will help fill in the space a bit more and add some dimension to the scene. The next step after is to start planning out my trim sheets and material application. Stay tuned for that!

じゃね！！
## Minecraft Block Renderer in JavaScript
#### Made by [Chaos](http://static.chaofan.io/blockRenderer/), Modified by FlamingoBike#6228

---

## Description

This tool allows you to render custom minecraft blocks to 32x32 images (size customizable by modifying `index.html`).

---

## How to Use

- Serve the `index.html` page on a local web server (the easiest way to do this is to open the project with Visual Studio Code, and use the `Live Server` extension).
- Select a model from the dropdown menu.
- Select textures for the top, left, and right faces from the dropdown menus, or upload your own 32x32 texture.
- Click Save File when you are ready, and it will download a png of what you have created.

---

## What you can do

- It is very easy to add new models. Simply navigate to the `models` folder in the minecraft assets (accessible by opening any version's jar with something like 7zip), and look at the .json file of the model you wish to replicate. Then, go over to the `blockModel.js` file and create a new variable in the `models` variable (line 114). You can add cubes and planes according to the json model by looking at the coordinate vectors `from` and `to` (keep in mind they are in pixels, so you have to divide the values by 16). Once you're done, invert the x and z to rotate it like it is in game (at least, I've had to do this for the fence and wall inventory models).
- You can add more textures without uploading them, by placing them in the `presets` folder. Then, open that folder in a terminal, and run `ls` to get a list of all the files, and copy said list in the `presets.js` file, to make them actually show up in the texture dropdown selects.
- If you added a new model and you wish to append its name to the downloaded file (for example, fences, walls, slabs, and stairs block names always specify what they are, like `stone_slab`, `oak_fence`, etc...), you can add it to the hardcoded whitelist in the `shouldAddModelNameToFile()` function, in `index.html`.
- Play around with it! It was very fun to get into the various details, I'm sure it's also quite simple to add shaders to have more than just cubes and planes.
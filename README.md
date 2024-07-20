# Archived
I have not had the time/interest to keep working on this for a while. The last commits from myself were over a year ago. As a result, I am **archiving** the project.

Please take a look at [@scurest](https://github.com/scurest)'s fork [GLideN64-SceneRipper](https://github.com/scurest/GLideN64-SceneRipper) who has been actively developing this in my absence.

# GLideN64-SceneRipper

*A next generation* ***Graphics Plugin*** *for* ***N64*** *emulators.*

---

## About

Modified version of GLideN64 that allows for scene ripping from N64 games.

Features 34 different rip modes, vertex color, fog information, continuous ripping (for animations) and CSV export support.

Developed and used with RMG 0.3.0.

How to use
---

1. Build / Download the modified plugin for your OS (Currently Windows and Linux qt-mupen64plus support only)
2. Place the plugin into your emulator's gfx plugin folder
3. Launch the emulator, go into graphics settings
4. Go to the `Texture Enchancement` tab, enable `Use texture pack` and `Generate scene rip textures` options
5. Go to the `Hotkey` tab, enable `Toggle textures dump` and `Perform scene rip` options. Setup a different key for both.
6. Go to the `Scene Ripping` tab, enable `Enable Scene Ripping` and configure any additional options you want there

| Option        | Description                                                                              |
| ------------- | ---------------------------------------------------------------------------------------- |
| Rip Mode      | Default will work in most cases. Certain games need to make use of mode 0 or higher.     |
| Entire Scene  | Ripper will attempt to rip all loaded triangles. Recommended off during continuous rips. |
| Continuous    | Enables continuous scene rip mode.                                                       |
| Target Frames | Use with Continuous. Specifies number of frames to rip. Use 0 for infinite.              |
| Export CSV    | Self-explanatory. Useful for debugging/parsing information to other formats.             |

7. Save and close settings. Start the game you want to rip from. Go to the general area.
8. Press the hotkey to enable texture dumping, you should get a confirmation stating it's on.
9. Press the hotkey to perform a scene rip. You should see a confirmation that the scene was ripped based on your current OSD settings.
  - Note: If you don't see any confirmations of a succesful scene rip, double check the settings mentioned above.
10. Go into your `(configured texture dump folder)/(N64 Game Name)/GLideNHQ/scene_rips` folder
11. You should see all of the textures that the scene ripper dumped along with one or more scene_rip.*.glr files.
  - Note: Initial ripped file will be `scene_rip.glr`. All future files will be `scene_rip.*.glr` (where * is always a sequential number).
12. Use accompanying Blender addon ([blender-import-glr](https://github.com/Luctaris/blender-import-glr)) to import the ripped scene into an editable environment.

Building
---
Follow the GLideN64 compile instructions found on the main repos wiki
- Windows Guide: [Build From Source (Windows)](https://github.com/gonetz/GLideN64/wiki/Build-From-Source-(Windows))
- Linux Guide: [Build From Source (Linux)](https://github.com/gonetz/GLideN64/wiki/Build-From-Source-(Linux))

Make sure to add `-DDEBUG_DUMP=ON` option, otherwise you won't see or be able to use any scene ripping functions!

My cmake config: `cmake -DCMAKE_BUILD_TYPE=Release -DMUPENPLUSAPI_GLIDENUI=ON -DMUPENPLUSAPI=ON -DDEBUG_DUMP=ON ../../src/`

For Windows specifically, I personally use and recommend using the msys2 setup. Linux compilation works out of the box with cmake.

Issues
---
If you have an issue using this modified plugin please **DO NOT** report them under the main GLideN64 repository. Use the issue tracker of this repository instead.

Feature / Pull Requests are welcome.

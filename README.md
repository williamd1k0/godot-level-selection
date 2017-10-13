# Megaman-like Level Selection

## Demo
![Demo gif](https://media.giphy.com/media/xT1Ra0mQ16T9n1u63K/giphy.gif)

The demo simply demonstrate how to use the thumbnails together with the grid so it can create a Level Selection Screen where information about the level is displayed in as a text in a Label node, which basically formats the dictionary using the data as strings.

## Description
This module is composed by two components:
1. [The level thumbnail](https://github.com/pigdevstudio/godot-level-selection/blob/master/Thumbnail.tscn)
2. [The thumbnail grid](https://github.com/pigdevstudio/godot-level-selection/blob/master/ThumbnailGrid.tscn)

### Thumbnail
This component points to the path of the [**Scene**](https://github.com/pigdevstudio/godot-level-selection/blob/master/Thumbnail.tscn#L39) to be loaded in case it got pressed. It also carries the [**dictionary key**](https://github.com/pigdevstudio/godot-level-selection/blob/master/Levels/demo_data.json#L2-L9) which containers the data of the level.

When pressed it will emit a signal to its parent telling it to load the scene, when it gets the focus of the GUI inputs it will emit another signal telling its parent which key of the dictionary should be used to display the infos about the level and also the path to the **PackedScene** which will be loaded in case it got pressed.

### ThumbnailGrid
This is a container for the levels thumbnails. It must contain the `.json` file with the data of the levels, which will be loaded for further access. Every time a thumbnail got focused it receives the info about the refereed level and **emits a signal** with the dictionary relative to the info of the scene, so it can be used by other `Nodes`.

It also **changes the scene** to the path passed by the current selected thumbnail in case it got pressed.

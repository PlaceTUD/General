# General

The General takes the different images and puts them together to one big `output.png`.
The `output.png` will then be feeded into [Commander](https://github.com/PlaceTUD/Commander) to be sent to the [Soldats](https://github.com/PlaceTUD/Soldat)

This script is forked and based on [placeDE/pixel](https://github.com/placeDE/pixel)

## How to

1. `config.toml`

The config.toml contains information of where each structure is located and the corresponding image, which is used for the pixel values. This image has to be in the correct scale, that means not scaled up.

The format to add or change an entry in the config.toml (add as many blocks as you need):

```toml
[[structure]]
name = "tud"
file = "tud.png"
startx = 58
starty = 832
priority = 0
```

If you want to filter certain colors, e.g. as a mask, you can add them to the `ignore_colors`. These are matched to the exact RGB values in the image, if a contains an ignored color it is skipped.

2. `render.sh`

Running the `render.sh` will run two commands of the `scripts/` folder in order. First it will run `generate_json.py` to generate a big json file out of the different images in config 
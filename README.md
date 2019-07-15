# UNet CNN Semantic-Segmentation Inference plugin

## Docker distribution

This plugin is available on DockerHub from the WIPP organization

```
docker pull wipp/wipp-unet-cnn-inference-plugin
```

## Build Docker File
```bash
#!/bin/bash

version=0.0.1
docker build . -t wipp/wipp-unet-cnn-inference-plugin:latest
docker build . -t wipp/wipp-unet-cnn-inference-plugin:${version}
```

## Run Docker File

```bash
nvidia-docker run \
    -v "path/to/input/data/folder":/data/inputs \
    -v "path/to/output/folder":/data/outputs \
    -v "path/to/model/folder":/data/model \
    wipp/wipp-unet-cnn-inference-plugin \
    --outputDir /data/outputs \
    --imageDir /data/images
    --savedModel /data/model 
```

## UNet Inference Job Options
```bash
usage: inference [-h] 
                --savedModel SAVED_MODEL_FILEPATH 
                --imageDir IMAGE_DIR
                --outputDir OUTPUT_DIR
                 [--useTiling USE_TILING] 
                 [--tileSize TILE_SIZE] 


```
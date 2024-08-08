Retrained ssd-mobilenet to detect dream blocks in the video-game celeste.

To test, take a screenshot of a screen in the game and rename it to Screenshot. In the jetson nano, move this file to jetson-inference/data/images. Make sure it is a jpg image.

In the terminal, write:

```
cd jetson-inference/python/training/detection/ssd
```

```
IMAGES=<path-to-your-jetson-inference>/data/images
```

```
detectnet --model=models/celeste/ssd-mobilenet.onnx --labels=models/fruit/labels.txt --input-blob=input_0 --output-cvg=scores --output-bbox=boxes "$IMAGES/Screenshot.jpg" "$IMAGES/test/Screenshot.jpg"
```

Afterwards, a newly made image in jetson-inference/data/images/test named screenshot will have boxes around the dream blocks


# UpscalerJS Models

Pre-trained models for use with [UpscalerJS](https://github.com/thekevinscott/UpscalerJS).

The models include:

| Dataset | Scale |
| --- | --- |
| [DIV2K](https://data.vision.ee.ethz.ch/cvl/DIV2K/) | 2x |
| [DIV2K](https://data.vision.ee.ethz.ch/cvl/DIV2K/) | 3x | 
| [DIV2K](https://data.vision.ee.ethz.ch/cvl/DIV2K/) | 4x |

## Contributing

You'd like to contribute a new pretrained model? Awesome!

To do so, you'll first need a model that runs in Javascript. Generally, that means 1) that the model be trained in Tensorflow or be tensorflow-compatible, and 2) that the model is able to be converted using the [TFJS Converter](https://www.npmjs.com/package/@tensorflow/tfjs-converter) (this means avoiding things like custom layers). It's also good practice to quantize your model if doing so does not lead to a drastic change in accuracy, as quantization helps performance in the browser.

Once you've converted a model, you'll want to follow this checklist:

* Open a PR against this library. Make sure to include:
  * Your model's `model.json` and weights in a folder within the [models](https://github.com/thekevinscott/UpscalerJS-models/tree/master/models) folder.
  * An update to this README's models table including your model and its scale.
  * A `config.json` file that has a description of your model. Some helpful things to include are how you trained your model, what dataset you used, and any hyperparameters you used.
  * An entry in the [examples folder](https://github.com/thekevinscott/UpscalerJS-models/tree/master/examples/), copying the description from above and also including a sample image output for evaluation purposes.
  * Bump the version of [`package.json`](https://github.com/thekevinscott/UpscalerJS-models/blob/master/package.json). Do a minor bump (aka, `0.1.1` -> `0.1.2`)
  * Special kudos if you provide a one-click Colab or Dockerfile for reproducing your results.
* Open a PR against [UpscalerJS](https://github.com/thekevinscott/UpscalerJS)
  * Add your model to the [`MODELS` object](https://github.com/thekevinscott/UpscalerJS/blob/master/src/models.ts) so it can be loaded successfully.

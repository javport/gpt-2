# gpt-2

Code and samples from the paper ["Language Models are Unsupervised Multitask Learners"](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf).

For now, we have only released a smaller (117M parameter) version of GPT-2.

See more details in our [blog post](https://blog.openai.com/better-language-models/).

## Installation

Download the model data
```
sh download_model.sh 117M
```

The remaining steps can optionally be done in a virtual environment using tools such as `virtualenv` or `conda`.

Install tensorflow 1.12 (with GPU support, if you have a GPU and want everything to run faster)
```
pip3 install tensorflow==1.12.0
```
or
```
pip3 install tensorflow-gpu==1.12.0
```

Install other python packages:
```
pip3 install -r requirements.txt
```

## Usage

| WARNING: Samples are unfiltered and may contain offensive content. |
| --- |

### Unconditional sample generation

To generate unconditional samples from the small model:
```
python3 src/generate_unconditional_samples.py | tee samples
```
There are various flags for controlling the samples:
```
python3 src/generate_unconditional_samples.py --top_k 40 --temperature 0.7 | tee samples
```

### Conditional sample generation

To give the model custom prompts, you can use:
```
python3 src/interactive_conditional_samples.py --top_k 40
```

## GPT-2 samples

| WARNING: Samples are unfiltered and may contain offensive content. |
| --- |

While we have not yet released GPT-2 itself, you can see some samples from it in the `gpt-2-samples` folder.
We show unconditional samples with default settings (temperature 1 and no truncation), with temperature 0.7, and with truncation with top_k 40.
We show conditional samples, with contexts drawn from `WebText`'s test set, with default settings (temperature 1 and no truncation), with temperature 0.7, and with truncation with top_k 40.

## Future work

We may release code for evaluating the models on various benchmarks.

We are still considering release of the larger models.

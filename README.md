Transliteration related data files and/or models.

Contains:
  * Arabic-English transliteration dataset mined from Wikipedia.
  * Trained transliteration modules for Arabic-English, English-Japanese and English-IPA.

## How to use the trained models

If you want to use some of the models provided in this repository you can use [the clstm library](https://github.com/tmbdev/clstm). The binary `clstmfilter` can be used to use an already existing model to transliterate your data.

To build the binary, use the command below. For more on how to install clstm read [this](https://github.com/tmbdev/clstm#prerequisites). You can read more about scons [here](http://scons.org/).

```
scons clstmfilter
```

For example, if you have a list of Arabic words which you want to transliterate to English, you can run the following commands in your shell:

```
set -a
load="ar2en.clstm"
./clstmfilter your_data.txt

```

## How to train your own models

If you want to train a new model with your data, you can use the `clstmfiltertrain` binary.

To build the binary, run:

```
scons clstmsfiltertrain
```

To train the model:

```
set -a
lr=0.1
./clstmfiltertrain your_train_data.txt your_eval_data.txt

```

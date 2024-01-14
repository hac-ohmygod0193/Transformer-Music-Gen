# Data
You may to download data with abc notes from [google drive](https://drive.google.com/drive/folders/15rNfd10B2yEab-67CG5VAyVjvolJN-E4?usp=sharing), and unpack in project directory.
# Training
Firstly wee need to train tokenizer.

```
python3 train_tokenizer trainset/abc abc.yttm
```

Then make some cleaning of the data

```
python3 clean_data.py trainset/abc cleaned_data
```

And starts training the model

```
python3 train.py cleaned_data
```
You may to setup some parameters, like gradient accamulation, batch size and e.t.c.

## Generation 
```
python3 generate.py testset/abc ABCModel/trained_model.pth
``` 

## Predict abc
If you want to predict your own abc file(ex. input.abc), then run the command
```
python3 predict.py input.abc ABCModel/trained_model.pth
``` 

After that you gets a directory with generated abc notes. You can convert abc to midi with [abc2midi tool](https://www.systutorials.com/docs/linux/man/1-abc2midi/), or in [web service](https://www.abcjs.net/abcjs-editor.html).
```
sudo apt-get update
sudo apt-get install -y abcmidi
abc2midi input.abc -o out.midi
```


## Reference
[generating-music-with-ai-or-transformers-go-brrrr](https://alxmamaev.medium.com/generating-music-with-ai-or-transformers-go-brrrr-3a3ac5a04126)

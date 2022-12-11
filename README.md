# Simple_Elmo-Training

For the purposes of this project, we use various version of AllenNLP. For the sentiment analysis task, we use version 2.10.1 and for the question-answer task, we use version 0.9.0

## Word-to-Vector Task (simple task):
Given that the user has already trained a model, use the `dump_weight.py` program to convert the checkpoints to a HDF5 file with the following command:
`python3 dump_weights.py --save_dir $MODEL_DIR --outfile $MODEL_DIR/model.hdf5`. Save the `vocab.txt` file in the same directory. There should also be a `options.json` and potentially a `meta.json` file as well. More information on this can be found in the Simple Elmo Training documentation and also [this repo](https://github.com/allenai/bilm-tf). 

Then, the model can be loaded into test.py, in which the path in which the model is loaded from (line 7) should be changed depending on the user's current path names. The user can add sentences into the array and change batch sizes by editing line 7 to something like so: "elmo.load(PATH, max_batch_size=32)". The limit can also be added as a variable to the load command if the user wishes to adjust the limit as well.

To run the word-to-vector task, run the command "python test.py".

## Sentiment Analysis Task (complex task):

To run the sentiment analysis task simple change directories to the sentiment analysis directory and run `python3 main.py`. Within this file, you can change the `batch_size` and `epochs` in order to see how performance varies.

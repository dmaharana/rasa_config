## Install python version that supports tensorflow==1.12.0
conda install python==3.6.8

## install all the rasa requirements using pip
pip install -r requirements.txt

## the tensorflow version installed with pip gives an error so uninstall and install using conda package manager
pip uninstall tensorflow
### Error
python -m rasa_nlu.train -c config_spacy.json --data data/data.json -o models --fixed_model_name nlu --project current --verbose
2019-04-20 17:20:03.915545: F tensorflow/core/platform/cpu_feature_guard.cc:37] The TensorFlow library was compiled to use SSE4.1 instructions, but these aren't available on your machine.
Aborted (core dumped)

conda install tensorflow==1.12.0
python -m spacy download en

## train the rasa-nlu
python -m rasa_nlu.train -c config_spacy.json --data data/data.json -o models --fixed_model_name nlu --project current --verbose

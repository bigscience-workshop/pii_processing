To test your regex, first install the package and spacy models:
```git clone https://github.com/bigscience-workshop/pii_processing
cd pii_processing
pip install spacy==3.1  transformers datasets langid faker nltk sentencepiece fsspec tqdm
pip install -r requirements.txt
pip install datasets
python -m nltk.downloader punkt stopwords  wordnet
python -m spacy download en_core_web_lg
python -m spacy download zh_core_web_lg
python -m spacy download pt_core_news_lg
python -m spacy download fr_core_news_lg
python -m spacy download ca_core_news_lg
python -m spacy download es_core_news_lg
cd ..
```

Then craete your regex files under the pii_processing/regex folder of the form ``<initial>_<target_lang>.py``.

Then test your regex on a file of the form ``<target_lang>.jsonl`` and create a file ``predicted_<target_lang>.jsonl``, ``right_regex_<target_lang>.json`` and ``wrong_regex_<target_lang>.json``

```
python test_regex.py -initial <initial> -target_lang <target_lang>
```

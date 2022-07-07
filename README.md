# metaphor-psycho

This is to perform experiments on metaphor usage characterizing Russian speakers with different psychological traits.

## Materials for the paper 'Towards automatic conceptual metaphor detection for psychological tasks'

I've added the data for the paper _'Towards automatic conceptual metaphor detection for psychological tasks'_ by Polina Panicheva, Ivan Mamaev, and Tatiana Litvinova, submitted for review in June'22.

- [annotation](https://github.com/PolinaZulik/metaphor-psycho/tree/main/annotation/split1): **MetPersonality** texts annotated by 3 annotators. This is the first annotation attempt described in the paper.
- [code](https://github.com/PolinaZulik/metaphor-psycho/tree/main/code) on:
   - [pre-processing](https://github.com/PolinaZulik/metaphor-psycho/tree/main/code/pre-processing): [morpho-analysis with spaCy](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/pre-processing/spacy_proc0.ipynb), [sampling data stratified by main author and text characteristics](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/pre-processing/get-stratified_metaphor_sample.ipynb), [sampling relevant verbs with context](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/pre-processing/fpi_get_verbs_context.ipynb) for annotation;
   - [metaphor detection](https://github.com/PolinaZulik/metaphor-psycho/tree/main/code/metaphor%20detection) with [NLI](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/metaphor%20detection/nli_all.ipynb), [MelBERT](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/metaphor%20detection/MelBERT_Adapted.ipynb), [Edge Probing](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/metaphor%20detection/probing_corpora.ipynb);
   - [results post-processing](https://github.com/PolinaZulik/metaphor-psycho/tree/main/code/results-processing): [annotation inter-annotator agreement](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/results-processing/process_annotation.ipynb), [metaphor use correlation with gender and FPI](https://github.com/PolinaZulik/metaphor-psycho/blob/main/code/results-processing/corrs_metaphor.ipynb).


--------

### Project plan (outdated since April'22):
1. Choose a metaphoric-literal usage dataset in Russian:
   - https://github.com/yubadryzlova/metaphor_dataset_20_verbs - 20 verbs only, 7.169 contexts;
   - https://www.isi.edu/people/mics/corpus_rich_metaphor_annotation - all POSs, metaphoric expressions only, currently 6K contexts, only in economic domain;
   - ? http://www.lrec-conf.org/proceedings/lrec2016/pdf/1156_Paper.pdf ? - should be good: all POSs, 45Km all topics, but I don't know how to obtain it yet!?
2. Train and evaluate a BERT-based model of metaphor identification (MMI) - https://huggingface.co/docs/transformers/tasks/token_classification on the selected dataset(s);
   - don't forget to evaluate cross-lexical/cross-topic for a lower-bound quality estimation.
3. Apply the MMI to the dataset - https://rusidiolect.rusprofilinglab.ru/search with FPI-16 ratings, to get metaphorical words.
   - annotate a few texts manually to check quality on new data.
4. For metaphorical words (and probably contexts, depending on the training dataset), identify target (context) and source (first concrete meaning) domains, by finding a thesaurus or a topic model; preferably, choose domains from the list of target and source domains from the paper http://www.lrec-conf.org/proceedings/lrec2016/pdf/1156_Paper.pdf. 
5. Identify frequencies of source, target, and source-target domains for every author. Correlate them with FPI-16 ratings.

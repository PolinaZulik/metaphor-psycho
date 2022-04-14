# metaphor-psycho

This is to perform experiments on metaphor usage characterizing Russian speakers with different psychological traits.

The plan:
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

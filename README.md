# pclub_secy_task_04

First part of the task was to find 5 most relevant paragraphs based on the question, and then find the piece of text which best answered the question if it did.
Approach
1. Preprocessed the data removing some of the problems in the dataset like some columns were shifted to the right or broken off in between.
2. Used FAISS to find top k paragraphs which matched the question because it provides quick search on basis of similarity search.
3. Used cross encoder : ms-marco-MiniLM-L-6-v2 which reordered the top k paragraphs on basis of context.
4. Used ELECTRA + SQUAD 2.0 model to extract answers from the paragraph. This was chosen because lot of corpus of data was taken from the SQUAD dataset, so model was already trained on major of them.

This provides quick answer and search of queries across the big corpus.

Results: 

![image](https://github.com/aayush01x/pclub_secy_task_04/assets/153027947/687a89f4-5538-4838-a01f-a141bfef7422)

It is clearly visible how good results are FAISS + Cross Encoder giving in finding top paragraphs.

Final question answering from the retrieved paragraph:

![image](https://github.com/aayush01x/pclub_secy_task_04/assets/153027947/cdf164bc-fe00-40a0-aa4f-82a90fb4db33)

FineTuning the models on current data would have produced much much better results, but due to time and resource constraint, I wasn't able to do so.

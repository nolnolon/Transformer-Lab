# A complete pipeline for teaching a RoBERTa model to automatically sort open-ended questions into one of ten pre-defined categories. 

~5 000 single-sentence questions, each labeled with one of 10 question-type tags (e.g. “concept,” “procedural,” “judgmental,” etc). 
Some categories are much rarer than others.

**Data analysis:** check sequence lengths, measure annotator agreement, visualize the skewed label distribution.
**Preprocessing:** RoBERTa tokenizer, label encoding, apply oversampling so that each of the ten categories appears equally often in training.

**Model setup**: 
1) fine-tune a pretrained RoBERTa model on the balanced training split;
2) add evaluation metrics capturing performance on minority classes
  ! check literature for best metrics: Matthew's Correlation Coefficient (MCC) 
4) evaluate on a held-out validation set

**Results**: ~0.76 MCC and 0.75 balanced accuracy. While MCC is above the 68.0 benchmark, balanced accuracy should be analysed and improved. 

**Presentation**: confusion matrix and classification report.

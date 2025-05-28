# A complete pipeline for teaching a RoBERTa model to automatically sort open-ended questions into one of ten pre-defined categories. 

~5 000 single-sentence questions, each labeled with one of 10 question-type tags (e.g. “concept,” “procedural,” “judgmental,” etc). 
Some categories are much rarer than others.

**Data analysis:** check sequence lengths, measure annotator agreement, visualize the skewed label distribution. 

<img width="1147" alt="Screenshot 2025-05-28 at 16 51 58" src="https://github.com/user-attachments/assets/95ab5d51-8833-4325-ba3d-5040994bbb6a" />

**Preprocessing:** RoBERTa tokenizer, label encoding, apply oversampling so that each of the ten categories appears equally often in training.

**Model setup**: 
1) fine-tune a pretrained RoBERTa model on the balanced training split;
2) add evaluation metrics capturing performance on minority classes
  ! check literature for best metrics: Matthew's Correlation Coefficient (MCC) 
4) evaluate on a held-out validation set

**Results**: ~0.76 MCC and 0.75 balanced accuracy. While MCC is above the 68.0 benchmark, balanced accuracy should be analysed and improved. 

**Presentation**: confusion matrix and classification report.

<img width="989" alt="Screenshot 2025-05-28 at 16 52 21" src="https://github.com/user-attachments/assets/a2dcb484-0e6a-4508-b400-27e955ca5de6" />

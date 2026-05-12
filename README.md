# PROJECT TITLE

## Introduction

This repository reproduces the findings from “Investigating the Limitations of Transformers with Simple Arithmetic” by Rodrigo Nogueira, Zhiying Jiang, and Jimmy Lin. The paper investigates how different number representations affect transformer performance on addition and subtraction tasks. The authors train the T5 (Text-to-Text Transfer Transformer) models on synthetic arithmetic datasets using different tokenization schemes, including subword representation (e.g. “456”), character-level representation (e.g. “4 5 6”), and position-token representation (e.g. “4 10e2 5 10e1 6 10e0”).  

## Chosen Result
We specifically aimed to reproduce the finding that using position-token representations for addition and subtraction operations allowed the model to perform at a higher accuracy than subword and character-level representations. This result was the paper’s main contribution and demonstrates that model performance depends on numerical representation, rather than model scale or training size alone.
[INCLUDE FIGURE]

## GitHub Contents
This repository contains two .ipynb files. One notebook that contains the code, which reproduces the paper, specifically generating the datasets, converting inputs into their proper numerical representation, fine-tuning the model with training datasets, and computing model performance with testing accuracy. The other notebook contains code for testing how well the models generalize on addition problems using numbers of unseen lengths.

## Re-implementation Details


## Reproduction Steps
Models: HuggingFace [T5-Small](https://huggingface.co/google-t5/t5-small) and [T5-Base](https://huggingface.co/google-t5/t5-base) 

Training Set: Synthetically generate 1000 examples with operands of varying lengths using balanced sampling. 

Evaluation Set: Synthetically generate 1000 examples with operands of varying lengths using random sampling. 

Evaluation Metric: Exact accuracy between model prediction and label.

Re-implementation Approach:
* Fine-tune transformer model by training it on the training set.
* Evaluate model with testing set.

Challenges/Modifications: Because of Google Colab memory limts, we were constrained by our batch sizes and model input and output sequence length limits. We had to make modifications to the original approach by decreasing the batch size as well as model input and output max token sequence length.

## Results/Insights

## Conclusion

## References

## Acknowledgements

## Adversarial Attacks on Parts of Speech: An Empirical Study in Text-to-Image Generation

<p align="justify">
Recent studies show that text-to-image (T2I) models are vulnerable to adversarial attacks, especially with 
noun perturbations in text prompts. In this study, we investigate the impact of adversarial attacks on different 
POS tags within text prompts on the images generated by T2I models. We create a high-quality dataset for 
realistic POS tag token swapping and perform gradient-based attacks to find adversarial suffixes that mislead 
T2I models into generating images with altered tokens. Our empirical results show that the attack success rate 
(ASR) varies significantly among different POS tag categories, with nouns, proper nouns, and adjectives being 
the easiest to attack. We explore the mechanism behind the steering effect of adversarial suffixes, finding 
that the number of critical tokens and information fusion vary among POS tags, while features like suffix 
transferability are consistent across categories.</p>

<p align="center"><img src="/Images/Poster.jpg" width="512" height="768"></p>

💥🎉 The paper **"Adversarial Attacks on Parts of Speech: An Empirical Study in Text-to-Image Generation"** is accepted in [Findings of EMNLP 2024](https://2024.emnlp.org/), a top conference in Artifical Intelligence/Machine Learning/Computational Linguistics.

📂 **Paper PDF**: https://aclanthology.org/2024.findings-emnlp.753.pdf


## Key Findings



+ <p align="justify"><strong>Attack Success Rate (ASR):</strong> nouns, proper nouns, adjectives are easier to attack while verbs, numerals and adverbs are the hardest. </p>

+ <p align="justify"><strong>Correlation between ASR and the number of critical tokens:</strong> Adverbs, numerals, and verbs are more resistant to adversarial attacks due to their dependency on the high number of critical tokens in the adversarial suffix.</p>

+ <p align="justify"><strong>Ease of Content Fusion:</strong> We observe that while adversarial suffixes steer the generation of target attributes, they often fail to completely remove the original token. This results in images generated by the Stable Diffusion containing both the input and target attributes, a phenomenon we refer to as content fusion. In categories like nouns, proper nouns, and adjectives, where the number of critical tokens is relatively lower, fusion is easier. However, in categories with a higher number of critical tokens, such as verbs, numerals, and adverbs, fusion is not possible.</p>

<p align="center"><img src="/Images/Adjective_entanglement.jpg" width="512" height="912"></p>

+ <p align="justify"><strong>Suffix Transferability:</strong> We discovered a common feature across different POS categories: the transferability of adversarial suffixes. We observed that the identified adversarial suffixes can universally transfer to other input prompts within the same POS tag. This indicates that a single adversarial suffix can convert various input prompts with distinct attributes into images with the same target attributes.</p>

<p align="center"><img src="/Images/suffix_transfer.jpg" width="512" height="712"></p>

+ **Vulnerabilities Observed across POS Tags:** 

   - <p align="justify">We noticed that the Stable Diffusion inherently faces difficulty generating images from prompts that include numerals.</p>
   
	<p align="center"><img src="/Images/numeral_experiment.jpg" width="912" height="512"></p>
   
   - <p align="justify">Images generated by the model using prompts where the adverb tokens have shared linguistic structures, close semantic representation in the feature space, and unrelated to emotions generally have minimal impact on visual output.</p>
	
	<p align="center"><img src="/Images/vulnerability_explored.jpg" width="712" height="242"></p>
	
   - <p align="justify">We also observed that Stable Diffusion struggles to generate images involving logos.</p>
   
## Repository Structure

The repository has three folders:

+ **Codes**: Contains the implementations in three subfolders.
	
	- **attack**: contains codes for the adversarial attack and attack success mechanism 
	- **dataset creation**: contains code for dataset construction
	- **evaluation**: contains code for attack success rate and semantic shift rate calculation

+ **Dataset**: Contains the data for the experiment in two subfolders.
	
	- **data for attack**: contains processed jsonl files for adversarial attack
	- **data for asm**: contains processed jsonl files for attack success mechanism 

+ **Results**: Contains the experimental results in two subfolders.
    
	- **attack performance**: contains the attack evaluation results
	- **attack success mechanism**: contains the results of average ASR by removing critical and non-critical tokens

## Citation
If you use the dataset or code, please cite the following:
```
@inproceedings{shahariar-etal-2024-adversarial,
    title = "Adversarial Attacks on Parts of Speech: An Empirical Study in Text-to-Image Generation",
    author = "Shahariar, G M  and
      Chen, Jia  and
      Li, Jiachen  and
      Dong, Yue",
    editor = "Al-Onaizan, Yaser  and
      Bansal, Mohit  and
      Chen, Yun-Nung",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2024",
    month = nov,
    year = "2024",
    address = "Miami, Florida, USA",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.findings-emnlp.753",
    pages = "12874--12890"
}
```
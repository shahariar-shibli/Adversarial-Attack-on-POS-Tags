# Adversarial Attack on POS Tags

Recent advances in text-to-image (T2I) models have shown remarkable progress in generating images from text 
descriptions. However, these models remain vulnerable to adversarial attacks, with prior work mainly focusing 
on attacking nouns in the text prompts. In this study, we evaluate an existing gradient-based attack aimed at 
generating adversarial prompts for T2I models (particularly Stable Diffusion), targeting different parts-of-speech 
(POS) tags. We experiment with six POS tags - \textit{noun, adjective, verb, adverb, numeral,} and \textit{proper noun} 
and investigate the effectiveness of such attack in restricted and unrestricted settings. Our findings reveal that 
nouns, proper nouns, and adjectives are more prone to adversarial manipulation, with verbs, adverbs, and numerals 
being the hardest due to their reliance on the high number of critical tokens.

# Repository Structure

The repository has three folders:

+ Codes: Contains the implementations in three subfolders.
	
	- attack: contains codes for the adversarial attack and attack success mechanism 
	- dataset creation: contains code for dataset construction
	- evaluation: contains code for attack success rate and semantic shift rate calculation

+ Dataset: Contains the data for the experiment in two subfolders.
	
	- data for attack: contains processed jsonl files for adversarial attack
	- data for asm: contains processed jsonl files for attack success mechanism 

+ Results: Contains the experimental results in two subfolders.
    
	- attack performance: contains the attack evaluation results
	- attack success mechanism: contains the results of average ASR by removing critical and non-critical tokens
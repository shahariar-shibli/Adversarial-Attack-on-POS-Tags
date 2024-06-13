# Adversarial Attack on POS Tags
 
Recent advances in text-to-image (T2I) models have shown remarkable progress in generating images from text descriptions. 
However, these models remain vulnerable to subtle modifications in the input text, known as adversarial attacks. 
Prior woks have primarily focused on perturbing objects (specifically nouns) in the text prompt to generate adversarial 
images, neglecting the impact of attacking other parts-of-speech associated with the object. In this study, we introduce 
POS-Attack, a gradient-based method aimed at generating adversarial prompts for T2I models (particularly Stable Diffusion), 
targeting different parts-of-speech (POS) tags. We experiment with six POS tags - \textit{noun, adjective, verb, adverb, numeral,} 
and \textit{proper noun} and investigate the effectiveness of our approach in both restricted and unrestricted settings. 
Our findings reveal that nouns, proper nouns and adjectives are more prone to adversarial manipulation, with verbs, adverbs, 
and numerals being the hardest due to their reliance on high number of critical tokens.
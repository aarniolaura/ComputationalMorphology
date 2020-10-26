### Computational Morphology LDA-T3101 (spring 2020) 

# Verb Derivation from Nominal Stems in Finnish

The aim of this project was to analyze noun-to-verb and adjective-to-verb derivation in Finnish. I wanted to create a morphological analyzer-generator that would be able to detect the original nominal stem of a derived verb, and tell what kind of derivational suffixes have been added to the stem. On the other hand, it should be able to generate different verbs from nominal stems. 

The final analyzer-generator  consists of a lexc file (derivation_lexicon.lexc) and an xfst file (derivation_rules.xfst). The lexc file contains the noun and adjective stem lexicons, and all the suffixes. The xfst file contains rules for sound changes that happen when suffixes are added, either in the suffixes themselves or in the stems. They also contain Finnish vowel harmony rules.

To start the analyzer-generator type  
`hfst-xfst`  
and then type  
`source derivation_rules.xfst`  

When using the generator, the following tag options can be added to a stem:  
- POS tags: +N (noun stem) or +A (adjective stem) 
- Noun-to-verb derivational tags: +Caus (causative suffix) or +Transl (translative suffix) 
- Verb-to-verb derivational tags: +Freq (frequentative suffix, can be added after +Caus) 
- Ending tags: +Inf (A-infinitive suffix, must be added after derivational tags) 

Ex 1. Generating word forms:  
`down kala+N+Caus+Inf`
Output:  
`kalastaa   
kalattaa   
kaloittaa`  

Ex 2. Analyzing word forms:  
`up harrastella`  
Output:  
`harras+A+Caus+Freq+Inf `  

# CS CM124 - Machine Learning Applications in Genetics, Challenge 2  
This is code for a project done in UCLA class CS CM124 - Machine Learning Applications in Genetics.  

This project had the following specification:  
Phenotype prediction is considered as the "holy grail" of genetics as it requires (good) modeling of the underlying genetic mechanism. Barring some Mendelian traits (such as the sickle-cell disease or Huntington's disease in humans), most traits have highly complex genetic architectures, making it difficult to infer the true models. Such complexity includes epistasis, gene-by-environment interactions, or non-linear effects, to name a few. In this project, you will predict the phenotype of test individuals based on their genotype and your model trained on the train individuals' genotype and phenotype. There are 200 SNPs for 2000 training individuals and 3000 test individuals.

The general idea is the same as the linear models we discussed in class: each (or pairs of) SNP has some weight on the phenotype, and you want to learn these parameters based on your model assumptions. However, the phenotype we have here has some of the aforementioned complexities involved. Here are some hints on what these complexities might be:  
- Non-infinitesimal. Unlike the linear model discussed in class, where all SNPs carry some non-zero weights, there may be some SNPs that are not causal.  
- Non-linear effects. Some SNPs may not behave linearly, meaning their effects don't increase by the same amount when having 2 of that SNP compared to having 1 of that SNP (recall the GWAS box plot problem in PS2). In research settings, people often use the quadratic function or exponential function (RBF) to model nonlinear effects. Here, you can assume all non-linear SNPs come from the same type of function.  
- Epistasis. There also may be some interaction between a pair of SNPs. This means that a SNP on its own may not be causal (zero weight), but if its partner SNP is also present for that individual, the pair might have some effect on that person's phenotype.
An external study on this phenotype has also informed us that fortunately, a causal SNP falls into one of the three categories and won't have two or more of these properties (e.g., a SNP with epistatic effect won't have a linear weight or nonlinear weight).

The goal of the project was to train a model on the training genotype and phenotype datasets and then use the model to predict a phenotype set based on the given test genotype dataset.  

In order to do this, my code features a few different models that I tried. 

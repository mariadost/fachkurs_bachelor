# Exercise SBML databases

In this exercise we will model the phosphorylation of fructose-6-phosphate (F6P), which is the third step of glycolysis, catalyzed by the enzyme [phosphofructokinase](https://en.wikipedia.org/wiki/Glycolysis#Preparatory_phase). F6P is phosporylated to fructose-1,6-bisphosphate (FBP) under the consumption of ATP. The organism we are working with is the yeast *Saccharomyces cerevisiae*.

<img src="https://raw.githubusercontent.com/tbphu/Fachkurs_Bachelor_WS1617/master/sbml_databases/pfk.jpg" alt="pfk" width="400px">

We already have an SBML file which describes this reaction, but without MIRIAM annotations or a kinetic law. 

1. Download the SBML file of the phosphofructokinase reaction [here](https://raw.githubusercontent.com/tbphu/Fachkurs_Bachelor_WS1617/master/sbml_databases/phosphofructokinase.xml) and import the model to Copasi. You will not be able to simulate it yet, because a kinetic law and initial concentrations for the species are missing. Have a look at the species and the reaction of the model.

2. Use Copasi to annotate the species and the reaction of the model. First search for the different species in the [KEGG](http://www.genome.jp/kegg/) compound database and identify their KEGG identifiers. The KEGG compound identifier for water is C00001 for example. For all compounds use the `is` relation. The PFK species is the enzyme catalyzing the reaction and cannot be found in KEGG compount. Instead annotate it with its EC number, which can also be found in KEGG (the resource for EC numbers is Enzyme Nomenclature). 

3. Annotate the reaction with the KEGG reaction identifier.

4. We are still missing concentrations for the species in our model. Search online databases for suitable concentration values and update them in Copasi. Relevant resources here are [bionumbers](http://bionumbers.org), the [Yeast Metabolome Database](http://www.ymdb.ca/) or [yeastgfp](http://yeastgfp.yeastgenome.org/) for protein amounts. [SGD](http://yeastgenome.org) can be helpful to identify gene names for enzymes. Also update the compartment volume to a realistic value.

5. Once the initial values of the species are established, we still need a kinetic law in order to simulate our reaction. For simplicity we assume for now that the reaction only occurs in the forward direction (irreversible reaction). The irreversible "Bi" kinetic law in Copasi describes an enzymatic reaction with two substrates. Use this kinetic law and search the kinetic information databases [Brenda](http://www.brenda-enzymes.de) and [sabio-rk](http://sabio.villa-bosch.de/) for Michaelis-Menten constants (Km-values) and maximal enzyme velocity (Vmax).

6. Plot a time-course simulation of the finished one-reaction model.
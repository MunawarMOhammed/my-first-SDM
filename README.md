Bradypus GLM — My First Species Distribution Model
A species distribution model (SDM) for Bradypus variegatus (three-toed sloth) built using a Generalised Linear Model (GLM) in R, following the standard protocol by Zurell et al. (2020).

📌 Overview
This project predicts the habitat suitability of the three-toed sloth across South America using climate data from WorldClim and occurrence records from the dismo R package. The final output is an interactive map showing predicted probability of sloth presence across the region.

🗺️ Output

📊 ROC Curve with AUC = 0.90 
🗺️ habitat suitability map 
📈 Effect size plot and species response curves

nceptualiseDefine species, study area and objectives2. DataLoad occurrence records and environmental predictors3. Model fittingVIF check → 80/20 split → Logistic GLM4. EvaluationAUC/ROC curve, effect sizes, response curves5. MappingPredict and visualise habitat suitability

📦 Libraries Used
LibraryPurposedismoSpecies distribution modelling toolsterraRaster map loading and processingggplot2Charts and visualisationsdplyrData manipulationpROCROC curve and AUC evaluationcarVIF multicollinearity checkleafletInteractive zoomable map

📁 Dataset

Bradypus.csv -- dismo package.  

bio1,bio5,bio6...  WorldClim  bioclim climate variable --dismo package.

biome Biome type map of South America.

Pseudo-Absence   116 randomly generated absence points.


🔬 Key Results 

Significant Variables (after VIF cleaning)

VariableCoefficientp-valueMeaningbio16+0.00210.0005 ***Wetter wet season → more suitablebio17+0.00070.517Not significantbiome-0.0940.081Weak effect

Model Performance

MetricValueAUC0.90  Null deviance256.42Residual deviance210.50Deviance explained18%AIC218.5

VIF Results (after cleaning)

VariableVIFbio161.42 ✅bio171.29 ✅biome1.18 ✅

🚀 packages:

"dismo", 
"terra", 
"ggplot2", 
"dplyr", 
"pROC", 
"car", 
"leaflet"

📂 Project Structure

```
my-first-SDM/
├── Bradypus_GLM.qmd        # Source Quarto notebook
├── Bradypus_GLM.html       # Rendered HTML output
├── my_first_SDM.Rproj      # RStudio project file
└── README.md               # This file
```

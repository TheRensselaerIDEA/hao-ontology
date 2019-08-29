This folder prototypes how the semantically-targeted analytics (STA) framework allows for precision risk analysis. We give example results of an analysis that sought to discover subpopulations within NHANES for which increased concentrations of environmental risk factor in blood and urine have significant associations with increases in total cholesterol.


Four types of input cartridge:

* `response` cartridges -- these provide the analysis concepts and background domain axioms necessary to model a given disease such as total cholesterol in the given example. Based on a published research study, the cartridge suggests controlling for age, BMI, socioeconomic status, smoking and drinking habits, sex, marital status, and education level.
* `cohort` cartridges -- these list the inclusion criteria used to determine if a given subject may be included in the user’s study. In the given example, we use all available NHANES subjects. This cartridge describes how to use the entire valid survey population as the study cohort.
* `risk factor` cartridges -- these describe categories of semantically similar risk factors and detail how they should be modeled. The given example is for heavy metals. This cartridge suggests log-transforming risk factor exposure measurements.
* `parameter` cartridges -- these contain rules to complete the chosen analysis workflow. In this cartridge, the SCM regularization strength hyperparameter lambda_W is allowed to search between 0.001, 0.01, and 0.1 for its value during model selection.




Three types of output cartridge:

* `model` cartridges -- SCM objects are serialized in `.pkl` format. The `model` cartridge associated with a `.pkl` file gives the 
parameters and hyperparameters of the associated SCM. The SCM class contains methods to assign observations to new cadres.
* `results` cartridges -- these describe a single study’s statistical findings and constituent input cartridges. In the example here, for one of the discovered subpopulations, the association between blood lead (LBXBPB) and total cholesterol has a regression coefficient of 3.0665. The association was significant, with a p-value of 0.0003.
* `subopopulation` cartridges -- these give "Table 1s" (cohort-description tables) of both discovered subpopulations and the overall study cohort. In this example, the subpopulation for which a significant association between blood lead and total cholesterol was found had a lower mean age than the overall study cohort (37.4 years vs. 46.7 years).

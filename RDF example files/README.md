This folder prototypes how  semantically-targeted analytics (STA) framework allows for precision risk analysis. We give example results of an analysis that sought to discover subpopulations within NHANES for which an environmental risk factor has a significant association with increases in total cholesterol.


Four types of input cartridge:

* `response` cartridges -- these provide the analysis concepts and background domain axioms necessary to model a given disease such as total cholesterol in the given example.
* `cohort` cartridges -- these list the inclusion criteria used to determine if a given subject may be included in the user’s study. In the given example, we use all available NHANES subjects.
* `risk factor` cartridges -- these describe categories of semantically similar risk factors and detail how they should be modeled. The given example is for heavy metals. 
* `parameter` cartridges -- these contain rules to complete the chosen analysis workflow.




Three types of output cartridge:

* `model` cartridges -- SCM objects are serialized in `.pkl` format. The `model` cartridge assocatiated with a `.pkl` file gives the 
parameters and hyperparameters of the associated SCM. The SCM class contains methods to assign observations to new cadres.
* `subopopulation` cartridges -- these give "Table 1s" (cohort-description tables) of discovered subpopulations.
* `results` cartridges -- these describe a single study’s statistical findings and constituent input cartridges.

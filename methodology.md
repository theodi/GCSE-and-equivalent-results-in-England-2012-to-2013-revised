GCSE and equivalent results in England, 2012 to 2013 (revised)
==============================================================

##Methodology

###Introduction

This dataset was prepared after most of the work for its 'sibling' ["GCSE and equivalent attainment by pupil characteristics: 2012 to 2013"](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013) was completed. 

Although you can tell that the two datasets were issued by different DfE teams (e.g. you can see in the PDF release notes that their work was lead by different statisticians) there is some degree of similarity in the style. This means that many of the considerations we made in the [methodology document for the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013/blob/master/methodology.md) apply to this, too. Although your focus may be on this dataset only, we suggest you read the other dataset's methodology document, too, before starting work.

Data processing and cleansing developed through the two stages described below:

***********
- [Stage 1](#stage-1): choice of which of the original files to further process and semantic analysis
- [Stage 2](#stage-2): normalisation and identification of missing data

Below is a description of the contents in this project, by folder.
- *data*
    - *raw*: the source publication webpage, dataset and documentation as found at the source web address
    - *preprocessed*: selected datasets from the 'raw' folder, cleansed and homogenised according to data science best practices
    	- *01_stage_1* this folder collects the parts of the raw data that the team selected as worth further processing 
    	- *02_stage_2* this folder is the result of the first stage of processing, mainly aimed at making the contents of *01_stage_1* onto a canonical form according to the team's interpretation of the data. 
- *images*: all images used for this documentation
- *scripts*
	- *stage_2*: the [OpenRefine](http://openrefine.org/) operation history and [R](http://www.r-project.org/) scripts used for the processing of stage 2.

###Stage 1

Differently from [the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013), this has no 'key'. Moreover, what the other team called "the underlying data", made of a collection of csv files, is not made available. This means that the four Microsoft Excel files that make the source package for this dataset are unfortunately our *raw* source.

[![Giacecco asking for the raw data on Twitter](images/twitter1.png "Giacecco asking for the raw data on Twitter")](https://twitter.com/giacecco/status/427743908047884288)

In stage 1 we then transformed the Excel data onto open and fully machine-readable formats. This is a time-consuming 'reverse engineering' work that is far from being ideal. Because of the limited time, only a few of the source Excel files and their sheets were processed. The list is described below:

- *SFR01_2014_NT.xlsx*
	- Table 1a
	- Table 1b
	- [ONGOING]

We also took the opportunity of doing so by using the Open Knowledge Foundation's [Simple Data Format](http://dataprotocols.org/simple-data-format/) (SDF) as our reference (read also ODI Jeni Tennison's ["2014: The Year of CSV"](http://theodi.org/blog/2014-the-year-of-csv) explaining the need for context in csv data). Any information related to the data that the Excel files express in the formatting was captured in the SDF [*datapackage.json*](/data/processed/01_stage_1/datapackage.json) file.





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

Differently from [the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013), this has no 'key'. Moreover, what the other team called "the underlying data", made of a collection of csv files, was not made available. This means that the four Microsoft Excel files that make the source package for this dataset are unfortunately our *raw* source.

[![Giacecco asking for the raw data on Twitter](images/twitter1.png "Giacecco asking for the raw data on Twitter")](https://twitter.com/giacecco/status/427743908047884288)

In stage 1 we then transformed the Excel data onto open and fully machine-readable formats. This is a time-consuming 'reverse engineering' work that is far from being ideal. Because of the limited time, only a few of the source Excel files and their sheets were processed. The list is described below and the result is in the [data/01_stage_1](data/01_stage_1) folder.

Source file | Destination file | Converted tables
------------|----------|-----------------
*SFR01_2014_NT.xls* | *table_1a.csv* | National tables - Table 1a: Time series of GCSE and equivalent entries and achievements. Years: 1995/96 to 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_1b_by_gender.csv* | National tables - Top section of table 1b: The English Baccalaureate - By gender.
*SFR01_2014_NT.xls* | *table_1b_by_subject.csv* | National tables - Bottom section of table 1b: The English Baccalaureate - By subject.
*SFR01_2014_NT.xls* | *table_1c.csv* | National tables - Table 1c: Percentage of pupils making expected progress in English and in mathematics between key stage 2 and key stage 4 by gender. Years: 2007/08 to 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_1d.csv* | National tables - Table 1d: Percentage of pupils making expected progress1 in English and mathematics between key stage 2 and key stage 4 by key stage 2 attainment level and key stage 4 outcome. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_4a.csv* | National tables - Table 4a: Average point scores and achievement of GCSE English and mathematics at grades A* to C by pupils at the end of key stage 4 by type of school and gender. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_8.csv* | National tables - Table 8: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of pupils **entering the subject**). Year: 2012/132 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_9.csv* | National tables - Table 9: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of **all** pupils). Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_17_incl_e_and_m.csv*| Local Authority tables - Table 17: GCSE and equivalent results of pupils at the end of key stage 4 for each local authority1 and region, including English and Mathematics GCSEs. Year: 2005/06 to 2012/132 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_18.csv*| Local Authority tables - Table 18: The English Baccalaureate by local authority and region. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_19_english.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in English between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.
*SFR01_2014_AT.xls* | *table_19_mathematics.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in Mathematics between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.




We also took the opportunity of doing so by using the Open Knowledge Foundation's [Simple Data Format](http://dataprotocols.org/simple-data-format/) (SDF) as our reference (read also ODI Jeni Tennison's ["2014: The Year of CSV"](http://theodi.org/blog/2014-the-year-of-csv) explaining the need for context in csv data). Any information related to the data that the Excel files express in the formatting was captured in the SDF [*datapackage.json*](/data/processed/01_stage_1/datapackage.json) file.





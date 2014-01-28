GCSE and equivalent results in England, 2012 to 2013 (revised)
==============================================================

##Methodology

###Introduction

This dataset was prepared after most of the work for its 'sibling' ["GCSE and equivalent attainment by pupil characteristics: 2012 to 2013"](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013) was completed. 

Although you can tell that the two datasets were issued by different DfE teams (e.g. you can see in the PDF release notes that their work was lead by different statisticians) there is some degree of similarity in the style. This means that many of the considerations we made in the [methodology document for the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013/blob/master/methodology.md) apply to this, too. Although your focus may be on this dataset only, we suggest you read the other dataset's methodology document, too, before starting work.

Data processing and cleansing developed through one single stage, described further down in this page.

Below is also a description of the contents in this project, by folder.
- *data*
    - *raw*: the source publication webpage, dataset and documentation as found at the source web address
    - *preprocessed*: selected datasets from the 'raw' folder, cleansed and homogenised according to data science best practices
    	- *01_stage_1* this folder collects the first transformation of the original Excel files into machine-readable CSV files, according to the SDF specifications

###Stage 1

Differently from [the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013), this has no 'key'. Moreover, what the other team called "the underlying data", made of a collection of csv files, was not made available. This means that the four Microsoft Excel files that make the source package for this dataset are unfortunately our *raw* source.

We enquired DfE and Jovita Lebednykaite, Statistical Officer there, kindly called Giacecco back and offered to find out more. In the meantime we'll have to work with what we got. 

[![Giacecco asking for the raw data on Twitter](images/twitter1.png "Giacecco asking for the raw data on Twitter")](https://twitter.com/giacecco/status/427743908047884288)

[![Giacecco thanking after being called back by DfE](images/twitter2.png "Giacecco thanking after being called back by DfE")](https://twitter.com/giacecco/status/427824518275825665)

Stage 1 then is about transforming the Excel data onto open and fully machine-readable formats. This is a time-consuming 'reverse engineering' work that is far from being ideal. Because of the limited time, only a few of the source Excel files and their sheets were processed. The list is described below and the result is in the [data/01_stage_1](data/01_stage_1) folder.

Source file | Destination file | Converted tables
------------|----------|-----------------
*SFR01_2014_NT.xls* | *table_1a_time_series_of_GCSE_and equivalent_entries_and_achievements.csv* | National tables - Table 1a: Time series of GCSE and equivalent entries and achievements. Years: 1995/96 to 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_1b_the_english_baccalaureate_by_gender.csv* | National tables - Top section of table 1b: The English Baccalaureate - By gender.
*SFR01_2014_NT.xls* | *table_1b_the_english_baccalaureate_by_subject.csv* | National tables - Bottom section of table 1b: The English Baccalaureate - By subject.
*SFR01_2014_NT.xls* | *table_1c_pupils_making_expected_progress_in_english_and_in_mathematics_between_ks2_and_ks4_by_gender* | National tables - Table 1c: Percentage of pupils making expected progress in English and in mathematics between key stage 2 and key stage 4 by gender. Years: 2007/08 to 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_1d_pupils_making_expected_progress_in_english_and_mathematics_between_ks2_and_ks4_by_ks_attainment_level_and_ks_outcome.csv* | National tables - Table 1d: Percentage of pupils making expected progress1 in English and mathematics between key stage 2 and key stage 4 by key stage 2 attainment level and key stage 4 outcome. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_4a_scores_and_achievement_by_pupils_at_the_end_of_ks4_by_type_of_school_and_gender.csv* | National tables - Table 4a: Average point scores and achievement of GCSE English and mathematics at grades A* to C by pupils at the end of key stage 4 by type of school and gender. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_5a_pupils_achieving_level_2_at_the_end_of_ks4_by_qualification_families_type_of_school_and_gender.csv* | National tables - Table 5a:  Percentage of pupils achieving level 2 at the end of key stage 4 by qualification families, by type of school and gender. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_8_gcse_entries_and_achievements_in_selected_subjects_of_pupils_at_the_end_of_ks4_in_schools_-_perc_of_pupils entering_the_subject.csv* | National tables - Table 8: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of **pupils entering the subject**). Year: 2012/132 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_9_gcse_entries_and_achievements_in_selected_subjects_of_pupils_at_the_end_of_ks4_in_schools_-_perc_of_all_pupils.csv* | National tables - Table 9: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of **all pupils**). Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_NT.xls* | *table_10a_gcse_entries_in_selected_subjects_by_pupils_at the_end_of_ks4_by_school_type.csv* | Table 10a: GCSE entries in selected subjects by pupils at the end of key stage 4 by school type (percentage). Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_17_gcse_results_of_pupils_at_the_end_of_ks4_for_la_and_region_including_english_and_mathematics.csv*| Local Authority tables - Table 17: GCSE and equivalent results of pupils at the end of key stage 4 for each local authority1 and region, including English and Mathematics GCSEs. Year: 2005/06 to 2012/132 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_18_english_baccalaureate_by_la_and_region.csv*| Local Authority tables - Table 18: The English Baccalaureate by local authority and region. Year: 2012/13 (Revised). Coverage: England.
*SFR01_2014_AT.xls* | *table_19_pupils_making_expected_progress_in_english_between_ks2_and_ks4_by_local_authority_and_region.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in English between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.
*SFR01_2014_AT.xls* | *table_19_pupils_making_expected_progress_in_mathematics_between_ks2_and_ks4_by_local_authority_and_region.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in Mathematics between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.

We also took the opportunity of doing so by using the Open Knowledge Foundation's [Simple Data Format](http://dataprotocols.org/simple-data-format/) (SDF) as our reference. Read also ODI Jeni Tennison's ["2014: The Year of CSV"](http://theodi.org/blog/2014-the-year-of-csv) explaining the need for context in CSV data. 

Any information related to the data that the Excel files express in the formatting was captured using SDF's [*datapackage.json*](/data/processed/01_stage_1/datapackage.json) file. As this was prepared manually, please be forgiving in case of mistakes and feel free to submit any fixes. 

"Not applicable" values are represented using "NA", according to R's convention.



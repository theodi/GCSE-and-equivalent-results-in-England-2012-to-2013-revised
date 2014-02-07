GCSE and equivalent results in England, 2012 to 2013 (revised)
==============================================================

##Methodology

###Introduction

This dataset was prepared after most of the work for its 'sibling' ["GCSE and equivalent attainment by pupil characteristics: 2012 to 2013"](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013) was completed. 

Although you can tell that the two datasets were issued by different DfE teams (e.g. you can see in the PDF release notes that their work was lead by different statisticians) there is some degree of similarity in the style. This means that many of the considerations we made in the [methodology document for the other dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013/blob/master/methodology.md) apply to this, too. Although your focus may be on this dataset only, we suggest you read the other dataset's methodology document, too, before starting work.

### 7th February 2014 update

While working on this dataset I wrote to the publishers to understand why the [attainments dataset](https://github.com/Digital-Contraptions-Imaginarium/GCSE-and-equivalent-attainment-by-pupil-characteristics-2012-to-2013) included the underlying raw data but this dataset did not. Jovita Lebednykaite, Statistical Officer at the DfE, was so kind to get back to me and commit to investigate. Below is her update, including juicy new data: 

> Dear Gianfranco,
>  
> RE: GCSE statistical first release underlying data
>  
> We spoke on the phone about a week ago. I explained the difference between the GCSE results and GCSE results by pupils characteristics publications. You asked why there is no underlying data available for GCSE results, but is available for GCSE results by pupil characteristics.
>    
> Two different teams produce GCSE and GCSE by characteristics statistics and the way they publish the data differs. GCSE results by pupil characteristics underlying data is published nationally and at local authority level, while GCSE results underlying data is published at school level by qualification, subjects and grade. GCSE results underlying data is available at the link below:
>    
> [http://www.education.gov.uk/schools/performance/download_data.html](http://www.education.gov.uk/schools/performance/download_data.html)
>    
> Please click on the “KS4 qualification and subject data” link in the middle of the page, then open the “ZIP” file and then the “EXCEL” file.
>    
> I hope that you will find this information helpful. If you have any further questions, please do not hesitate to contact me.
>    
> Kind Regards,
>     
> Jovita

What you find below is the original documentation I wrote before these news.

####No raw data! :-(

A major difference from the other dataset is that what the other team named "the underlying data" (a collection of raw CSV files + a key) was **not** made available here. This means that the four Microsoft Excel files that make the source package for this dataset are unfortunately everything we've got.

The four Excel files are designed to be used interactively by humans and are not 'machine-readable'. Lots of information is captured by visual formatting, and in a few cases you cannot even access some of the data unless you use an Excel macro via a drop-down list.

Data processing and cleansing developed through one single stage, described further down in this page.

Below is also a description of the contents in this project, by folder.
- *data*
    - *raw*: the source publication webpage, dataset and documentation as found at the source web address
    - *preprocessed*: selected datasets from the 'raw' folder, cleansed and homogenised according to data science best practices
    	- *01_stage_1* this folder collects the first transformation of the original Excel files into machine-readable CSV files, according to the SDF specifications

###Stage 1

We enquired DfE and Jovita Lebednykaite, Statistical Officer there, kindly called Giacecco back and offered to find out more. In the meantime we'll have to work with what we got. 

[![Giacecco asking for the raw data on Twitter](images/twitter1.png "Giacecco asking for the raw data on Twitter")](https://twitter.com/giacecco/status/427743908047884288)

[![Giacecco thanking after being called back by DfE](images/twitter2.png "Giacecco thanking after being called back by DfE")](https://twitter.com/giacecco/status/427824518275825665)

Stage 1 then is about transforming the Excel data onto open and fully machine-readable formats. This is a time-consuming 'reverse engineering' work that is far from being ideal. Because of the limited time, only a few of the source Excel files and their sheets were processed. The list is described below and the result is in the [data/01_ stage_ 1](data/01_ stage_ 1) folder.

Source file | Destination file | Converted tables
------------|----------|-----------------
*SFR01_ 2014_ NT.xls* | *table_ 1a_ time_ series_ of_ GCSE_ and equivalent_ entries_ and_ achievements.csv* | National tables - Table 1a: Time series of GCSE and equivalent entries and achievements. Years: 1995/96 to 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 1b_ the_ english_ baccalaureate_ by_ gender.csv* | National tables - Top section of table 1b: The English Baccalaureate - By gender.
*SFR01_ 2014_ NT.xls* | *table_ 1b_ the_ english_ baccalaureate_ by_ subject.csv* | National tables - Bottom section of table 1b: The English Baccalaureate - By subject.
*SFR01_ 2014_ NT.xls* | *table_ 1c_ pupils_ making_ expected_ progress_ in_ english_ and_ in_ mathematics_ between_ ks2_ and_ ks4_ by_ gender* | National tables - Table 1c: Percentage of pupils making expected progress in English and in mathematics between key stage 2 and key stage 4 by gender. Years: 2007/08 to 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 1d_ pupils_ making_ expected_ progress_ in_ english _ and_ mathematics_ between_ ks2_ and_ ks4_ by_ ks_ attainment _ level_ and_ ks_ outcome.csv* | National tables - Table 1d: Percentage of pupils making expected progress1 in English and mathematics between key stage 2 and key stage 4 by key stage 2 attainment level and key stage 4 outcome. Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 4a_ scores_ and_ achievement_ by_ pupils_ at_ the_ end_ of_ ks4_ by_ type_ of_ school_ and_ gender.csv* | National tables - Table 4a: Average point scores and achievement of GCSE English and mathematics at grades A* to C by pupils at the end of key stage 4 by type of school and gender. Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 5a_ pupils_ achieving_ level_ 2_ at_ the_ end_ of_ ks4_ by_ qualification_ families_ type_ of_ school_ and_ gender.csv* | National tables - Table 5a:  Percentage of pupils achieving level 2 at the end of key stage 4 by qualification families, by type of school and gender. Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 8_ gcse_ entries_ and_ achievements_ in_ selected_ subjects_ of_ pupils_ at_ the_ end_ of_ ks4_ in_ schools_ -_ perc_ of_ pupils entering_ the_ subject.csv* | National tables - Table 8: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of **pupils entering the subject**). Year: 2012/132 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 9_ gcse_ entries_ and_ achievements_ in_ selected_ subjects_ of_ pupils_ at_ the_ end_ of_ ks4_ in_ schools_ -_ perc_ of_ all_ pupils.csv* | National tables - Table 9: GCSE entries and achievements in selected subjects of pupils at the end of key stage 4 in schools (percentage of **all pupils**). Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ NT.xls* | *table_ 10a_ gcse_ entries_ in_ selected_ subjects_ by_ pupils_ at the_ end_ of_ ks4_ by_ school_ type.csv* | Table 10a: GCSE entries in selected subjects by pupils at the end of key stage 4 by school type (percentage). Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ AT.xls* | *table_ 17_ gcse_ results_ of_ pupils_ at_ the_ end_ of_ ks4_ for_ la_ and_ region_ including_ english_ and_ mathematics.csv*| Local Authority tables - Table 17: GCSE and equivalent results of pupils at the end of key stage 4 for each local authority1 and region, including English and Mathematics GCSEs. Year: 2005/06 to 2012/132 (Revised). Coverage: England.
*SFR01_ 2014_ AT.xls* | *table_ 18_ english_ baccalaureate_ by_ la_ and_ region.csv*| Local Authority tables - Table 18: The English Baccalaureate by local authority and region. Year: 2012/13 (Revised). Coverage: England.
*SFR01_ 2014_ AT.xls* | *table_ 19_ pupils_ making_ expected_ progress_ in_ english_ between_ ks2_ and_ ks4_ by_ local_ authority_ and_ region.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in English between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.
*SFR01_ 2014_ AT.xls* | *table_ 19_ pupils_ making_ expected_ progress_ in_ mathematics_ between_ ks2_ and_ ks4_ by_ local_ authority_ and_ region.csv*| Local Authority tables - Table 19: Percentage of pupils in state-funded mainstream schools making expected progress in Mathematics between key stage 2 and key stage 4, by local authority and region. Year: 2008/09 to 2012/13. Coverage: England.

We also took the opportunity of doing so by using the Open Knowledge Foundation's [Simple Data Format](http://dataprotocols.org/simple-data-format/) (SDF) as our reference. Please read ODI Jeni Tennison's ["2014: The Year of CSV"](http://theodi.org/blog/2014-the-year-of-csv) to better understand the need for context in CSV data. 

Any information related to the data that the Excel files express in the formatting was captured using SDF's [*datapackage.json*](/data/processed/01_stage_1/datapackage.json) file. As this was prepared manually, please be forgiving in case of mistakes and feel free to submit any fixes. 

"Not applicable" values are represented using "NA", according to R's convention.



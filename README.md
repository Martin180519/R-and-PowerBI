# R-and-PowerBI

As stated in the project notes we had to follow a number of steps in order to produce the final report using R and PowerBI in conjunction
First step: R

•	Initial Exploratory Analysis 
•	Clean the data
•	Exploratory Data Analysis
•	Export Data 

Second step: PowerBi

•	Client brief and Data request for dashboard
Initial Exploratory Analysis
The first stage was to check the data via the link to visually see what information we were looking at before importing it into R, to then compare.
I started with R  by loading datafile (DF) via the link we were provided with, once the load string was run the data appeared in the Environment as shown on the right screen ( on the screen shot. Note: In the environment window you can see that the rows and columns as stated, by clicking on table it will bring up a table view of the df).
#Load data 
•	df<- read.csv("https://public.tableau.com/app/sample-data/HollywoodsMostProfitableStories.csv")

In order to execute a command you must select run after each string input.

![SC1](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/f04528c1-1813-4c0d-9e62-a47f5efc55aa)

![sc2](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/3b88524b-5f4a-43be-bdd3-f3d57f7b99f0)

#Take a look at the data: 

View(df)

This request opened up the DF tab window showing out data file info – here we can compare it with out original final source.

![sc3](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/ef43ad89-bfce-437b-9d5e-096488772c9a)

#Load library: 

install.packags("tidyverse")

We install and run the tidyvers e package in R as we need  visual software to process the data file.

![sc4](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/b1b0e554-9628-4f4c-ad99-831cb950680e)

As you can see the prompt command, history action and result show in the console window. This area will also show any errors  that come up after the command is run.

![sc5](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/5285521d-1132-429b-9184-d2a908c9fbaf)

#Import library 

library(tidyverse)

![sc6](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/1d414134-c747-464f-bfc4-6346db5fb364)

Clean the data:

•	# Check data types: 

str(df)  - The str() is used  to look at the structure of the data.


![sc7](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/9ade7c9d-1af8-447a-8d72-a2fbc098031b)


Clean the data:
•	# Check for missing values: 

•	colSums(is.na(df))

•	#Drop missing values 

•	df <- na.omit(df) or df <- df %>% drop_na()

•	# check to make sure that the rows have been removed 

•	colSums(is.na(df))

The above steps are done in order to clean the data brfore producing a fins csv file in order to transfer over to powerbi.


![sc8](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/d4003878-2daa-4033-bd9a-d5184aad5b54)

Exploratory Data Analysis 

•	#Summary Statistics: 

summary(df) – the summary function returns the minimum, maximum, mean, median, and 1st and 3rd quartiles for a numerical vector.

•	#scatterplot 

ggplot(df, aes(x=Lead.Studio, y=Rotten.Tomatoes..)) + geom_point()+ scale_y_continuous(labels = scales::comma)+coord_cartesian(ylim = c(0, 110))+theme(axis.text.x = element_text(angle = 90))

Produces a requested scatter chart in the Plot tab window.

![sc9](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/ddbca904-1568-4e55-9289-089ac49ad185)


Export Data 

•	#Export clean data 

write.csv(df1, "clean_df.csv")

Once we are happy with the clean we can run the above request to export the new cleaned data file, we can the retrieve this new data file with the clean amendments and transfer it to powerbi.


![sc10](https://github.com/Martin180519/R-and-PowerBI/assets/156096889/630b308b-75d1-46be-b322-f6732202cd38)









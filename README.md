# DATA 512 Final project - Exploring the racial disparities in police killings in the US

## Project proposal

### Motivation

The issue of racial bias in policing system in the US has been a widely discussed and debated topic not only in the US, but across nations. The shooting of Michael Brown in Ferguson, Missouri in 2014 and more recently the use of excessive force that resulted in the death of George Floyd triggered protests across the globe and the rise of Black Lives Matter movement that called for various measures ranging from law enforcement reforms to defunding the police departments. Although efforts have been taken in the past few years to gather data from law enforcement agencies and officers on a voluntary basis, data are still limited, which pose challenges to making policy reforms.

For the final project, I would like to analyze police killings in the US between 2013 and till date, explore racial disparities, if any, in these killings and how the different racial and ethnic groups are affected at a nation level and across states/cities. Understanding how these police killings affect different racial groups and the extent of racial bias in these killings is therefore an important topic that has a very strong human-centered outlook. Any insights on police violence and racial equity in these killings will serve as an evidence that will support changes to policies and reforms around training and hiring of law enforcement officers, thereby resulting in reduced number of fatalities among both civilians and police officers. These serve as motivators for me to perform this analysis and while the human-centered nature makes it a difficult problem to analyze (since we have to look at both sides of the coin), I hope my analysis and insights carry minimal bias, accounting for any confounding factors during the process. 

### Data:

In order to understand the effect of police killings on different racial groups in the US, I will be using the following data sources 
* [mappingpoliceviolence.org](https://mappingpoliceviolence.org/aboutthedata) – a research collaborative that collects comprehensive data on police killings nationwide in the US (~ 8,500 killings starting from 2013 till date). Mapping police violence meticulously sources information from the three largest, most comprehensive, and impartial crowdsourced databases on police killings in the country: [FatalEncounters.org](https://fatalencounters.org/), the [U.S. Police Shootings Database](http://homicidecenter.org/services/resources/police-shootings/) and [KilledbyPolice.net](https://killedbypolice.net/). The site also performs extensive original research to further improve the quality and completeness of the data; searching social media, obituaries, criminal records databases, police reports and other sources to identify the race of 90 percent of all victims in the database. Any case where a person dies as a result of being shot, beaten, restrained, intentionally hit by a police vehicle, pepper sprayed, tasered, or otherwise harmed by police officers, whether on-duty or off-duty is defined as a police killing in the database.

Following are the attributes found in the police killings data

| Attributes                                                                        |
|-----------------------------------------------------------------------------------|
| Victim's name                                                                     |
| Victim's age                                                                      |
| Victim's gender                                                                   |
| Victim's race                                                                     |
| URL of image of victim                                                            |
| Date of Incident (month/day/year)                                                 |
| Street Address of Incident                                                        |
| City                                                                              |
| State                                                                             |
| Zipcode                                                                           |
| County                                                                            |
| Agency responsible for death                                                      |
| ORI Agency Identifier (if available)                                              |
| Cause of death                                                                    |
| A brief description of the circumstances   surrounding the death                  |
| Official disposition of death (justified   or other)                              |
| Criminal Charges                                                                  |
| Link to news article or photo of official   document                              |
| Symptoms of mental illness?                                                       |
| Unarmed/Did Not Have an Actual Weapon                                             |
| Alleged Weapon (Source: WaPo and Review   of Cases Not Included in WaPo Database) |
| Alleged Threat Level (Source: WaPo)                                               |
| Fleeing (Source: WaPo)                                                            |
| Body Camera (Source: WaPo)                                                        |
| WaPo ID (If included in WaPo database)                                            |
| Off-Duty Killing?                                                                 |
| Geography                                                                         |
| MPV ID                                                                            |
| Fatal Encounters ID                                                               |

* [US Census Bureau](https://www.census.gov/en.html) – provides population and median income estimates for demographic profiles such as age, gender and race at state and nation level.
* [Uniform Crime Reporting](https://www.fbi.gov/services/cjis/ucr/) - The FBI’s Uniform Crime Reporting (UCR) Program counts one arrest for each separate instance in which a person is arrested, cited, or summoned for an offense. The UCR Program collects arrest data on 28 offenses for each year. The arrests data will be used as an alternative benchmark to analyze racial disparity in the killings.


While the license for the datasets are not explicitly mentioned on the website, they are available for the public to download freely.

### Research questions and/or hypotheses

I am interested in exploring the data to answer the following research questions

* How do the police killings vary across the racial/ethnic groups? 
    * Are individuals in a particular racial group disproportionately killed by the police compared to the others?
    * What are the odds of an individual belonging to a racial group being killed based on a)population proportion and b) arrests proportion?
        * Null Hypothesis: There is no difference between the proportion of arrests/population and the proportion of victims of police killings across the races. 
* How do the police killings vary across states/cities? 
    * Are individuals of a particular racial/ethnic group in certain states/ cities more likely to be killed by the police than others?
* How do the police killings vary across the age for the racial groups?
* How do the police killings vary across the perceived threat of the victims(armed/un-armed) for the racial groups? 
 
### Background and Related Work

About ~1000 civilians are killed each year by law enforcement officers in the United States. Rates of police killings in the United States have been much higher than comparable countries ([Guardian report](https://www.theguardian.com/us-news/2015/jun/09/the-counted-police-killings-us-vs-other-countries)), though to an extent this could be attributed to the fact that the police in the US often contend with much more violent situations and more heavily armed individuals than the police in other developed societies. Databases such as Fatal Encounters, Mapping Police Violence and The Washington Post’s Fatal Force project have tracked the killings year after year. Many works have been conducted in the past that looked for patterns in the police killings across different races and ethnic groups. The article from [J.Nix et al.](https://onlinelibrary.wiley.com/doi/abs/10.1111/1745-9133.12269) analyzed 990 police shootings compiled by *The Washington Post* in 2015 for evidence of implicit bias, and the [mapping fatal police violence](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7313728/) article analyzed police killings from *Fatal Encounters* for overall rates of police violence across the US as well as racial inequities. The [article](https://www.nature.com/articles/d41586-019-02601-9) in *nature* talks about how racial biases play into deadly encounetrs with the police. A recent [analysis](https://fivethirtyeight.com/features/police-are-killing-fewer-people-in-big-cities-but-more-in-suburban-and-rural-america/) from *FiveThirtyEight* observed that police are killing fewer people in big cities, but more in suburban and rural America. While some of the works have used data from Washington post, I have chosen to use the data from mapping police violence as it is extensive and also includes cases where police kill someone through use of a chokehold, baton, taser etc. Based on the findings informed from these works as well as the data sources at my disposal, I hope to perform an extensive exploratory analysis to answer my research questions

### Methodology:

#### Preprocessing:
* Since the data provided by the mapping police violence requires some data cleaning and munging, pandas and numpy will be used for data preprocessing. For attributes with missing values such as age and gender, depending on the variable importance/ information gain provided by the attribute, either missing value imputation will be performed or the record will be dropped. If the race associated with a victim is "Unknown" or "null", the record will be dropped from the analysis, and the corresponding data loss will be reported.

### Exploratory Analysis:
* In order to answer the aforementioned research questions, an exploratory analysis of the underlying mapping violence data, census data and UCR data will be performed at various levels of aggregtion. In addition to population estimates that are widely used as a benchmark to identify racial disparities, I will also be using the arrests data as an alternative benchmark. The idea of population estimates assumes that every person within each group is equally likely to be exposed to an encounter which may not necessarily be an exact representation, as mentioned in this [study](https://journals.sagepub.com/doi/full/10.1177/1948550618775108) by Cesario et al.  Pandas will be predominantly used to perform the aggregations and the subsequent analysis, and for the visual analysis, matplotlib and searborn will be used.

### Statistical significance:
* To compare the proportion of arrests/population vs. proportion of victims, a chi-square goodness-of-fit test will be performed to see if the expected and observed frequencies based on the proportions are statistically different. A significant p-value would likely indicate racial bias in the police killings. The [scipy.stats.chisquare](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.chisquare.html) function from the scipy library will be used to conduct the test.


## Licenses:

This project is licensed under the terms of the [MIT license](https://github.com/Pradeepprabhakar92/data-512-final/blob/main/LICENSE)

# Data Science Project (currently under construction)
<font size='5'>I wanted to show how data science could create positive impact, addressing a serious problem.  For my first project, I chose to study the Opioid Crisis.</font>

# Table of Contents

<font size='5'>

[Project Overview](#project-overview) <br>
[The Data](#the-data)<br>
[The Opioid Crisis](#the-opioid-crisis) <br>
[Opioid Dependence](#opioid-dependence) <br>
[Study Endpoints](#study-endpoints) <br>
[References](#references) <br>

# Project Overview
<font size='5'>I will create a dataset from scratch that will observe a patient population with approximately 1300 patients receving treatment for 24 weeks, from 8 treatment centers.  They will be receiving treatment through medication.  I will evaluate the efficacy of treatment, using FDA guidelines<sup>[1](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/opioid-use-disorder-endpoints-demonstrating-effectiveness-drugs-treatment-guidance-industry)</sup>.  I will use machine learning to make predictions about treatment outcomes.  <br>
<br>
Machine learning will provide meaningful insight in helping us 
1) Draw statistical inference, identifying risk signals for relapse in patients individually 
2) Make dynamic predictions during treatment, to improve patient outcomes, also addressing patient risk individually</font>

# The Data
<font size='5'> I approached Dr. Sean Luo, who is an addiction psychiatrist and subject matter expert in machine learning.  Dr. Luo advised me to work on a dataset that is part of the Clinical Trial Network study CTN0027 <sup>[2](https://datashare.nida.nih.gov/study/nida-ctn-0027)</sup>.  This dataset is a subset of a larger active study that has received federal funding<sup>[3](https://www.cuimc.columbia.edu/news/opioid-disorder-treatment-first-three-weeks-forecast-success)</sup> </font>



# The Opioid Crisis
<p>
    <img src="images/oud.png" alt="Opioid Crisis in America" width="700" height="360" style="float:right">
</p>

<font size='5'>The US is currently experiencing an Opioid Crisis.  In 2021 107,000 people died from fatal drug overdose.  The number of deaths from drug overdose in 2021 is 6 times greater than the total in 1999<sup>[2](#2)</sup>. The rise in overdose death is directly related to consumption of Fentanyl, a synthetic opioid that is 100x stronger than morphine that's made it's way into the illicit drug supply<sup>[3](#3)</sup>. People who develop problmematic use of opioids, unknowingly get exposed to fentanyl and die tragically.<br>
</font>

# Opioid Dependence
<font size='5'> People who develop Opioid Use Disorder (OUD) experience biological changes to specific brain systems, which make treatment and recovery very difficult<sup>[4](#4)</sup>.  In early phases of abuse, over stimulation of the brains reward system creates compulsion to take opiods repeatidly.  Once dependence develops, other brain systems that regulate wakefulness, breathing, blood pressure, and general alertness, become hyperactive, causing painful withdrawal syndrome.  The distress from withdrawal can only be remediated by taking opioids, which overides rational thinking, leading to high risk behavior, resulting in serious adverse events. There is no cure for Opioid Use Disorder, but there is opportunity for remission, if people can reduce patterns of problematic consumption, they will avoid death/suffering and restore quality of life to reasonable levels.</font>

# Study Endpoints
| Topic | Link | Description | Release Date |
| --- | --- | --- | --- |
| Statistical Analysis | https://huggingface.co/axiong/PMC_LLaMA_13B | Measuring Study Outcomes | 2023/09/01 |
| Machine Learning | https://huggingface.co/chaoyi-wu/MedLLaMA_13B | Interpret ML Models to Understand Predictors | 2023/05/01 |


___
## References
<a id="1">[1]</a>
The Common Wealth Fund: [Mental Health Conditions and Substance Use: Comparing U.S. Needs and Treatment Capacity with Those in Other High-Income Countries](https://www.commonwealthfund.org/sites/default/files/2020-05/Tikkanen_mental_hlt_intl_comparison_db.pdf)<br> 

<a id="2">[2]</a>
Centers for Disease Control: [Drug Overdose Deaths in the United States, 2001–2021](https://www.cdc.gov/nchs/products/databriefs/db457.htm)

<a id="3">[3]</a>
Centers for Disease Control: [Deaths involving illicitly manufactured fentanyl are on the rise](https://www.cdc.gov/opioids/basics/fentanyl.html#:~:text=Rates%20of%20overdose%20deaths%20involving,times%20the%20rate%20in%202013.)

<a id="4">[4]</a>
National Library of Medicine: [The Neurobiology of Opioid Dependence: Implications for Treatment](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851054/)

<a id="5">[5]</a>
National Library of Medicine: [The Effectiveness of Medication-Based Treatment for Opioid Use Disorder](https://www.ncbi.nlm.nih.gov/books/NBK541393/)

<a id="6">[6]</a>
National Library of Medicine: [A Literature Review Examining Primary Outcomes of Medication Treatment Studies for Opioid use Disorder: What outcome should be used to measure opioid treatment success?](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7377168/)
# This page is in the process of being updated.

<font size='5'> If you're interested in looking at the code, you can access the notebooks at [Jupyter Notebooks](https://github.com/DanHerman212/oud_treatment_outcome/tree/main/notebooks) and the [data directory](https://github.com/DanHerman212/oud_treatment_outcome/tree/main/data/clean_data) 

These notebooks need a few editorial cycles, which will be completed within the next 2 months.

</font>

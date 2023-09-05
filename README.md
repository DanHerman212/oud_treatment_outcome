### Individual Level Predictive Modeling for Opioid Use Disorder Treatment Outcome
Jul 2023 - Present

I'm currently working on a personal project, where the goal is to show how machine learning can improve outcomes for treatment of Opioid Use Disorder (OUD).   I received guidance from Dr. Sean Luo, who designed the protocol for the project.

There is an Opioid Crisis in the united states, where close to 1,500 Americans are dying every week from Fentanyl.  Fentanyl is an artificially manufactured Opioid that is 100 times stronger than morphine.  Fentanyl has been increasingly prevalent in the illicit drug supply.  The DEA estimates that 6 out of 10 illicit pain pills are cut with Fentanyl.  People who are dying from Fentanyl are mostly working class people who suffered from chronic pain and were wrongly prescribed opiates, which are not designed for long term use.  If you are a veteran, you are disproportionately affected and are twice as likely to die from Fentanyl.  When people can't get pain meds through pharmacies, they will go through illicit channels and risk death from exposure to Fentanyl.

![CFR Stats](images/o.jpg)

There is strong evidence indicating the effectiveness of opioid agonist treatment.  Mediations such as Methadone, Buprenorphine and Extended Release Naltrexone, can help prevent death from Fentanyl.  However, the prescription of these meds is mostly arbitrary, not backed by sound scientific evidence, mostly done for convenience, based on opinions.  Also, people who recover do so in different trajectories.  This creates a challenge and opportunity for precision medicine.  Personalized risk scores can promote patient centered care, similar to cancer treatment.

![Treatment outcome and Patient Population](images/p.png)

To address this problem, we observed dataset NIDA-CTN-0027 from the CTN.  This dataset includes data for about 1300 patients receiving treatment at 8 different centers.  We monitored medication doses, urine toxicology and self reported use, within the first 30 days of treatment.

# Preliminary Results from running an XGBoost Classifier
![SHAP Values-Top 15 for Feature Importance](images/s.png)

There were 1315 patients
910 (69%) completed treatment

Of those that completed treatment
521 (57%) patients relapsed
389 (43%) patients did not relapse

For the context of this project, the most important metric is to reduce false positives for treatment outcomes.

I saw that after the 3rd iteration there was only 1 false positive in the confusion matrix.  I saw that it decreased with every iteration, which is ideal.  However the total number of positive outcomes predicted should be higher.

There were 389 potential positive outcomes, but the prediction only got 111 correct on the last iteration.  I did an 80/20 split with the training and testing data, so I expected there would be higher than 111 positive predictions.  

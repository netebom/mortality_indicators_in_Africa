
This project is about uncovering trends in health records sourced from World Health Organization.  
As infant, child, and maternal mortality rates continue to bedevil Africa, we hope to uncover trends  
in health records, and profer viable solutions to the problems that health data holds.

### DATA UNDERSTANDING

The columns in the original datasets contain health-related indicators and demographic information used in global health datasets like those from the **World Health Organization (WHO)** about all countries, regions, and locations of the world.  
However, the dataframe 'dn' presents the same information but limited to African countries only because the focus of this project is on Africa.  
Here is a brief description of each column:

#### **Entity**  
   - This refers to the name of the country or region in the dataset. It represents the geographical or political entity where the data is collected from (e.g., "Algeria", "Rwanda", "Nigeria").

#### **Code**  
   - This is likely a unique identifier or code for each country or region in the dataset (e.g., a country code like "USA" for the United States or "IN" for India). It is used for referencing the entity more efficiently.

#### **Year**  
   - This column indicates the year in which the data was collected or reported (e.g., "2020", "2021"). This is important for time series analysis to track changes over time.

#### **Births attended by skilled health staff (% of total)**  
   - This percentage represents the proportion of births in a specific country or region that are attended by skilled health personnel (doctors, nurses, midwives) during delivery. It is an important indicator of maternal health services. For the purpose of this project, the column was renamed as 'Births attended'.  

#### **Observation value - Indicator: Under-five mortality rate - Sex: Total - Wealth quintile: Total - Unit of measure: Deaths per 100 live births**  
   - This indicator shows the under-five mortality rate, which is the probability of a child dying before reaching the age of five, per 100 live births. It is an important health metric used to measure child health and development. The column also suggests that this is a general estimate for all sexes and wealth quintiles.
It was renamed as 'Under five mortality (per 100 live births)' for this project.  

#### **Cause of Death**  
   - This column indicates the specific cause of death (e.g., "Malaria", "Pneumonia", "Heart Disease") for which the data is being reported. This can be used for analyzing the leading causes of death in different regions or populations.

#### Immunization Indicators  
   These columns contain the percentage of one-year-olds who are vaccinated with specific vaccines:

   - **BCG (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the **Bacillus Calmette-Guérin (BCG)** vaccine, which is primarily used to protect against tuberculosis (TB).
   
   - **HepB3 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the third dose of the **Hepatitis B** vaccine, which prevents Hepatitis B infection.

   - **Hib3 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the third dose of the **Haemophilus influenzae type b (Hib)** vaccine, which helps prevent infections like meningitis and pneumonia.

   - **IPV1 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the first dose of the **Inactivated Polio Vaccine (IPV)** to prevent polio.

   - **MCV1 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the first dose of the **Measles Containing Vaccine (MCV1)**, which is important for measles prevention.

   - **PCV3 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the third dose of the **Pneumococcal Conjugate Vaccine (PCV3)**, which helps prevent pneumonia, meningitis, and other infections caused by Streptococcus pneumoniae.

   - **Pol3 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the third dose of the **Polio** vaccine, which protects against polio virus infection.

   - **RCV1 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the first dose of the **Rotavirus vaccine (RCV1)**, which prevents severe diarrhea caused by rotavirus.

   - **RotaC (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with a **rotavirus vaccine**. This is sometimes denoted as **RotaC** for a particular version of the vaccine.

   - **YFV (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the **Yellow Fever Vaccine (YFV)**, which is essential in regions with risk for yellow fever transmission.

   - **DTP3 (% of one-year-olds immunized)**:  
     Percentage of one-year-olds immunized with the third dose of the **Diphtheria, Tetanus, and Pertussis (DTP3)** vaccine. This vaccine prevents these three serious diseases.

### **Share of population covered by health insurance (ILO (2014))**  
   - This percentage represents the proportion of the population in a given country or region that is covered by **health insurance**, based on data from the **International Labour Organization (ILO)** in 2014. It provides insights into access to healthcare services and social protection.

### **Deaths - Sex: all - Age: 0 - Variant: estimates**  
   - This column contains the estimated number of **deaths among all sexes for individuals aged 0** (i.e., infant and child mortality) based on available data. This measure is often used to assess child mortality trends.

### **Estimated maternal deaths**  
   - This represents the estimated number of **maternal deaths**, typically defined as deaths resulting from complications during pregnancy, childbirth, or within a certain period after childbirth. This indicator is crucial for assessing maternal health and the quality of healthcare available to women during pregnancy and childbirth.

### **959828-annotations**  
   - This column contains special annotations/metadata associated with the dataset, such as notes, comments, additional references. This column was dropped as it didn't hold useful information that could guide this project.

### **Under-fifteen mortality rate**  
   - This represents the **under-fifteen mortality rate**, which is the number of deaths of children under 15 years of age per 1,000 live births. This is another key indicator of child health and overall health system effectiveness.



### DATA PRE-PROCESSING
The various datasets were loaded and subset for African countries after importing the various dependencies needed for data wrangling. It is important to note that duplicated records were found and dropped while cleaning each dataset. After data cleaning was done, the individual dataframes were all concatenated into one dataframe.  
A summary of the dataframe column names, number of records per column, each column datatype and a few more information were brought up using the '.info()' method. The '.describe()' method was transposed in order to give a better view of the summary statistics related to all numeric columns in the dataframe.  
A check for missing values was conducted, and their respective percentages relative to each column were also computed.  Due to the nature of the dataset, it was decided that no missing value would be filled seeing as they would result in very misleading information. Missing values were mostly found in numeric columns. Categorical columns had very few missing records. However, the methods employed in data wrangling guaranteed that no missing value would affect the analytical process.

### EXPLORATORY DATA ANALYSIS
The summary statistics of the concatenated dataframe (mentioned earlier) revealed the various count of records, mean, standard deviation, minimum, median, and maximum values of each numerical column. 
![Descriptive Statistics](screenshots/descstats.jpg)


The following visuals were plotted to show trends in the data:  
- Bar chart of Top five African countries by Child mortality rate

![Bar chart](screenshots/cmtop5.jpg)


- Column (vertical bar) chart of Years by highest Child mortality rate in Africa
![Column Chart](screenshots/cmtyears.jpg)
  
- Treemap of African countries by Infant mortality

![Treemap](screenshots/im.jpg)
  
- Line chart of Years with highest infant mortality records in ?Africa

![Line Chart](screenshots/imyears.jpg)

- Scatterplot of Total Maternal Deaths by African countries
![Scatter plot](screenshots/mmc.jpg)
  
- Line chart showing Trend of Maternal mortality over Years in Africa
![Line plot](screenshots/matmortline.png)


- Column chart of African countries with highest occurence of Youth mortality
![Column chart](screenshots/u15mc.jpg)

- Correlation Heatmap of infants vaccinated with all the vaccines described above along with subplots of pairplots that show how the percentage of infants vaccinated against one vaccine correlates with others
![Heatmap](screenshots/corrmat.jpg)

![Pairplot](screenshots/pairplot.jpg)

- Stacked Bar chart of Infant immunization rates over the years
![Stacked Bar chart](screenshots/vaccrateyears.jpg)

- Stacked Column chart of Mean Infant immunization rates by African countries
![Stacked Column chart](screenshots/vacrcountries.jpg)

### FACTORS AFFECTING HIGH MORTALITY RATES IN AFRICA
The contrasting patterns of immunization rates and mortality rates across African countries, such as Gambia, Sao Tome and Principe, Seychelles, Ghana, and Sierra Leone having high immunization rates, while Somalia, Chad, and South Sudan are among the poorest, and the links to high infant mortality rates, child mortality rates, under-fifteen mortality records, and maternal mortality rates in countries like Nigeria, Ethiopia, Egypt, Guinea, Burkina Faso, Togo, and Niger, point to a range of interrelated factors. The reasons behind these disparities are not limited to:
##### Healthcare Infrastructure and Access to Services
•	Gambia, Seychelles, Ghana, and Sierra Leone have better healthcare infrastructure and more accessible immunization programs. Countries like Gambia and Sierra Leone have made significant strides in providing universal immunization, supported by international health organizations like GAVI (Global Alliance for Vaccines and Immunization), UNICEF, and WHO.
•	In contrast, Somalia, Chad, and South Sudan face significant challenges in their healthcare systems due to conflict, political instability, and underdeveloped infrastructure, leading to difficulties in reaching children with vaccines. The lack of infrastructure makes it harder for health systems to effectively distribute vaccines and provide routine immunization.
##### Political Instability and Conflict
•	Countries like Somalia, South Sudan, and Chad have been affected by long-standing conflict, instability, and displacement, which severely disrupt health systems and make it difficult to carry out vaccination campaigns.
•	In Sierra Leone, Guinea, and Liberia, while the countries were affected by Ebola outbreaks, post-crisis recovery and international aid, including immunization efforts, have led to relatively better immunization coverage compared to conflict-affected countries where instability hinders public health efforts.
•	Nigeria and Ethiopia have faced challenges in reaching remote or conflict-prone regions, despite improvements in healthcare services in urban centers. Nigeria’s Boko Haram insurgency in the north has complicated immunization efforts in some areas.
##### Economic Factors
•	Wealthier nations like Seychelles and Ghana can better afford to implement comprehensive immunization programs. These countries typically receive more international aid and have better-funded healthcare systems.
•	Poorer countries like South Sudan, Somalia, and Chad face economic constraints that limit their ability to invest in healthcare infrastructure, including the purchase and distribution of vaccines. Lack of funds for health programs, transportation, and personnel means that even if vaccines are available, they may not reach remote or rural areas.
##### Government Commitment and Health Policy
•	Countries like Ghana and Sierra Leone have made strong commitments to improving child health through vaccination, child health campaigns, and national immunization days. In Seychelles, government prioritization of health programs ensures that immunization rates remain high.
•	On the other hand, in countries like Somalia, Chad, and South Sudan, the lack of government stability or inconsistent policies may result in poor delivery of healthcare services, including immunization. Where political will is weak or compromised, healthcare systems struggle to perform adequately.
##### Cultural and Social Factors
•	In some regions, cultural beliefs and misinformation can influence the acceptance of vaccines. In South Sudan and Somalia, traditional beliefs or religious objections may affect the willingness to vaccinate children, which contributes to lower immunization coverage. Additionally, social norms may prioritize home births or traditional medicine over modern healthcare practices, including vaccination.
•	However, in Gambia, Seychelles, and Ghana, public health education campaigns often promote vaccination as an essential part of childcare and are more widely accepted within society.
##### Health Workforce and Training
•	Gambia, Seychelles, Ghana, and Sierra Leone have made strides in training healthcare workers and improving the capacity of their healthcare systems to handle immunization campaigns. Strong healthcare worker presence and community outreach programs play a key role in these countries’ high immunization rates.
•	Conversely, countries like Somalia, Chad, and South Sudan face challenges related to shortages of skilled healthcare workers, lack of trained personnel, and insufficient health workers in rural or conflict-affected regions, which hinders the delivery of vaccination services.
##### Maternal Health and Child Mortality Correlation
•	High maternal mortality rates and poor maternal healthcare often correlate with high infant mortality rates in countries like Nigeria, Ethiopia, and Egypt. The absence of skilled birth attendants, limited access to prenatal care, and poor nutrition among pregnant women contribute to birth complications and the death of newborns.
•	In countries like Guinea, Burkina Faso, and Sierra Leone, poor maternal health often contributes to poor child health outcomes. These countries face poor sanitation, limited access to clean water, malnutrition, and a lack of skilled birth attendants, all of which are major factors contributing to high child mortality.
##### Under-15 Mortality and Health Conditions
•	Niger, Togo, and Guinea are plagued by high levels of malnutrition, poor sanitation, infectious diseases like malaria and diarrheal diseases, and lack of clean water, all of which contribute to under-fifteen mortality.
•	Countries with high under-15 mortality rates often struggle with preventable diseases, and poor access to healthcare for children. While immunization can reduce mortality rates, other factors, such as health systems weaknesses, poverty, poor maternal health, and inadequate nutrition, also play a role in higher child mortality rates.
##### Global Health and Aid Support
•	Countries like Gambia, Seychelles, Ghana, and Sierra Leone often benefit from strong international aid and support programs, including vaccine donations and technical assistance from organizations like the World Health Organization (WHO) and GAVI. These programs often contribute significantly to the higher immunization rates in these countries.
•	On the other hand, countries like Nigeria, Ethiopia, and Botswana, while receiving international support, often struggle to effectively implement health programs due to logistical challenges, corruption, or political instability, which can hinder aid distribution.
##### Impact of Global Health Crises
•	In countries like Guinea, Burkina Faso, and Sierra Leone, outbreaks of Ebola or malaria can lead to increased child mortality due to the disruption of health services and the strain on healthcare systems. These outbreaks also affect immunization campaigns, especially if resources are redirected to deal with an emergency crisis.
•	Similarly, countries that have faced the COVID-19 pandemic have also seen disruptions in immunization schedules, especially in low-income and war-torn regions, leading to backlogs in vaccination.

The disparities in immunization rates and mortality outcomes across African countries are due to complex interactions between healthcare infrastructure, economic factors, political stability, cultural beliefs, and access to international aid. High immunization rates in countries like Gambia, Seychelles, and Ghana are largely due to strong health systems, government commitment, and successful international cooperation, while countries like Somalia, Chad, and South Sudan face ongoing challenges due to conflict, poverty, and weak health infrastructure. These differences also contribute to high rates of maternal and child mortality in certain countries, despite efforts to improve health systems and services.

### PROPOSED RECOMMENDATIONS
To address the multifaceted health challenges faced by African countries, particularly those with high maternal mortality rates, infant mortality rates, poor immunization coverage, and high under-15 mortality rates, a comprehensive, practical approach is needed. This approach should combine improvements in healthcare infrastructure, policy reforms, community engagement, economic development, and international cooperation. Below are realistic solutions that can be implemented to help curb these problems:  
##### Strengthening Healthcare Infrastructure
•	Invest in healthcare facilities: Governments should prioritize building and upgrading hospitals, health clinics, and maternity wards, particularly in rural and underserved areas. This includes ensuring access to basic medical equipment, medications, and emergency obstetric care.
•	Expand transportation networks: Develop and improve road networks, ambulance services, and transportation systems to ensure timely access to healthcare, especially in remote or conflict-prone regions.
•	Improve healthcare delivery: Provide mobile health units and community health centers that can reach out to rural populations for routine immunization, maternal care, and basic medical services.
##### Increasing Access to Skilled Health Personnel
•	Expand training programs for doctors, nurses, and midwives, with a focus on maternal and child health, especially in underserved regions. This should include subsidized medical education and continuing education opportunities for healthcare workers.
•	Incentivize healthcare professionals to work in rural or conflict-affected regions by providing housing allowances, higher salaries, and professional development opportunities.
•	Train community health workers (CHWs) in maternal and child health care to enhance community-level health education, disease prevention, and early detection of complications.
##### Improving Maternal Health and Family Planning
•	Promote antenatal care (ANC): Ensure that all pregnant women have access to free or subsidized antenatal care. Health services should include screening for complications, nutritional support, and regular check-ups throughout pregnancy.
•	Improve family planning: Increase access to contraceptives and family planning education to reduce unplanned pregnancies and provide for birth spacing, reducing risks for both maternal and child health.
•	Expand postnatal care services to monitor both newborns and mothers during the critical post-delivery period, addressing complications such as postpartum hemorrhage and infection.
##### Enhancing Immunization Coverage
•	Expand vaccination programs: Increase vaccine availability and coverage through national immunization programs. This includes reaching hard-to-reach communities with mobile vaccination teams and community health workers.
•	Strengthen immunization education: Launch large-scale education campaigns to increase awareness of the importance of routine immunizations and reduce vaccine hesitancy, especially in areas with high cultural resistance or misinformation.
•	Use technology: Utilize digital tools and SMS reminders to keep families aware of immunization schedules and track vaccine coverage.
•	Integrate immunization into other health services: Ensure that immunization is part of regular maternal and child health services, such as antenatal visits and child health check-ups.
##### Addressing Socio-Economic Factors
•	Increase government spending on health: Allocate more government resources to healthcare, ensuring equitable distribution to low-income areas. Investment should focus on basic health services, maternal and child health, and immunization programs.
•	Improve poverty alleviation programs: Strengthen social safety nets, including cash transfers, nutrition programs, and health insurance schemes, to reduce the economic barriers to accessing healthcare services.
•	Strengthen education systems: Educating women and girls is one of the most effective ways to improve maternal health and child health outcomes. Ensuring universal access to education for girls, as well as providing vocational training and economic opportunities for young women, can empower them to make better health decisions.
##### Improving Nutrition
•	Promote maternal nutrition: Ensure that pregnant women receive nutritional support, such as iron supplements, folic acid, and balanced diets to prevent complications like anemia and low birth weight.
•	Address child malnutrition: Improve access to nutrition programs for children, especially under-5s, by providing supplemental feeding programs, micronutrient supplementation, and improving access to clean water and sanitation.
•	Community-based nutrition education: Promote local farming initiatives, food security programs, and breastfeeding as well as food fortification with essential nutrients.
##### Promoting Clean Water and Sanitation
•	Improve access to clean water: Ensure that communities, especially those in rural areas, have access to safe drinking water through water treatment plants, rainwater harvesting systems, and community wells.
•	Enhance sanitation: Develop sanitation infrastructure such as toilets, waste management systems, and handwashing stations to prevent waterborne diseases like diarrhea, which is a leading cause of child mortality.
##### Strengthening Disease Prevention and Control
•	Expand malaria prevention: Distribute insecticide-treated bed nets, provide malaria treatment, and implement malaria vaccination programs to reduce the high malaria burden in many African countries, which significantly contributes to both infant and child mortality.
•	Prevent and treat infectious diseases: Focus on preventing and treating other infectious diseases such as HIV, tuberculosis, pneumonia, and diphtheria through early detection, vaccination, and effective treatment programs.
##### Increasing Political Will and Government Commitment
•	Government commitment to health: Strengthen the political commitment to improving maternal and child health by making health a priority in national development plans. This includes healthcare reforms, increased budget allocation, and stronger political leadership in addressing the health needs of vulnerable populations.
•	Effective governance and accountability: Improve governance in healthcare systems to ensure that resources are used effectively. This can be achieved through transparent budgeting, accountable healthcare institutions, and anti-corruption measures to prevent misuse of funds.
##### Collaboration with International Organizations and NGOs
•	Partner with global health organizations: Strengthen partnerships with WHO, UNICEF, GAVI, and other international health organizations to access funding, expertise, and technical support for maternal and child health programs.
•	NGO involvement: Encourage NGOs to work at the community level to increase health awareness, implement vaccination campaigns, and provide essential health services.
•	International aid and support: Engage international donors to support healthcare initiatives, especially in post-crisis countries and low-income regions.
##### Promote Gender Equality
•	Empower women: Ensure gender equity by empowering women through education, economic independence, and political participation. When women have more decision-making power in the household, they are more likely to prioritize maternal and child health.
•	Support gender-sensitive health policies: Create policies that address the specific health needs of women, adolescents, and girls, particularly in terms of maternal health and sexual and reproductive rights.

The challenges facing countries like Nigeria, Ethiopia, and Botswana (with high maternal and infant mortality rates), and countries like Guinea, Togo, and Niger (with poor under-15 mortality records) require comprehensive and sustained solutions. These solutions must address both the supply side (healthcare infrastructure, training, policy support) and the demand side (education, economic empowerment, community engagement). By focusing on strengthening healthcare systems, improving nutrition, increasing access to family planning, promoting gender equality, and ensuring international collaboration, it is possible to reduce maternal and child mortality rates and significantly improve health outcomes across the continent.


#### APPRECIATION  
Special thanks to [Mr Dayo Dada](https://github.com/Deewhy254) and the Regonet Team for all the new things they taught me while taking the Data Analytics course with them.  
I also want to thank you for taking your time to go through this project.

#### Author
[Etebom Ntuk](https://github.com/netebom)  


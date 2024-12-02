Data Inference Iteration 1:

## Data Input:

Source                    | Headline                                   | Content                                                                                | Date
--------------------------|--------------------------------------------|----------------------------------------------------------------------------------------|------------
"Cape Town News"          | "Malaria cases rising in northern regions" | "Recent reports indicate a significant rise in malaria cases in northern Cape Town."   | 2024-12-01
"Durban Health Advisory"  | "Cholera outbreak in coastal towns"        | "Local hospitals have reported an outbreak of cholera in Durban’s coastal areas."      | 2024-11-15

## Data Output:

Content: "Recent reports indicate a significant rise in malaria cases in northern Cape Town."  
Risk Classification: High  

Content: "Local hospitals have reported an outbreak of cholera in Durban’s coastal areas."  
Risk Classification: Moderate

Data Inference Iteration 2:
Δ in Features Implemented:

	1.	Add APIs: Use APIs (e.g., CDC, WHO) to fetch structured data dynamically.
	2.	Enhance NLP Models: Train or fine-tune a model for more nuanced classifications (mocked for this demonstration).
	3.	User Feedback Loop: Include mock feedback data to adjust and refine risk levels.

 ## Data Input:

Source       | Headline              | Content                                                      | Date
-------------|-----------------------|--------------------------------------------------------------|------------
"CDC API"    | "Dengue Fever outbreak" | "CDC reports dengue fever cases surging in tropical regions." | 2024-11-30
"WHO API"    | "Influenza alert"      | "WHO warns of influenza strains spreading in colder climates." | 2024-11-28

## Data Output:

Content: "CDC reports dengue fever cases surging in tropical regions."
Risk Classification: High  

Content: "WHO warns of influenza strains spreading in colder climates."
Risk Classification: Moderate

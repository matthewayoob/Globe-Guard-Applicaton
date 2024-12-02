# **GlobeGuard: Technical Documentation**

## **Algorithm Overview**

- **Risk Evaluation**: Combines keyword detection, NLP sentiment/context analysis, and user feedback to classify risks as High, Moderate, or Low.  
- **Dynamic Thresholds**: Adjusts classifications over time based on confirmed user feedback.

---

## **Web Scraping Process**

- **Source Identification**: Extracts data from trusted sources (e.g., CDC, WHO) using structured scraping rules tailored to each site.  
- **Data Collection**: Utilizes `BeautifulSoup` to extract headlines, content, and dates from dynamically queried URLs.  
- **Error Handling and Validation**: Handles HTTP errors (404, 500) and validates the consistency of extracted data.  
- **Real-Time Updates**: Automates scraping at scheduled intervals (e.g., daily) and stores results in JSON or a database for app integration.

---

## **Iteration History**

### **Data Inference Iteration 1**

#### Data Input:

| Source                  | Headline                                   | Content                                                                                | Date       |
|--------------------------|--------------------------------------------|----------------------------------------------------------------------------------------|------------|
| "Cape Town News"        | "Malaria cases rising in northern regions" | "Recent reports indicate a significant rise in malaria cases in northern Cape Town."   | 2024-12-01 |
| "Durban Health Advisory" | "Cholera outbreak in coastal towns"        | "Local hospitals have reported an outbreak of cholera in Durban’s coastal areas."      | 2024-11-15 |

#### Data Output:

- **Content**: "Recent reports indicate a significant rise in malaria cases in northern Cape Town."  
  **Risk Classification**: High  

- **Content**: "Local hospitals have reported an outbreak of cholera in Durban’s coastal areas."  
  **Risk Classification**: Moderate  

---

### **Data Inference Iteration 2**

**Δ in Features Implemented:**

1. **API Integration**: Used APIs (e.g., CDC, WHO) for structured data ingestion.  
2. **Enhanced NLP Models**: Fine-tuned a model for more nuanced classifications.  
3. **User Feedback Loop**: Incorporated mock feedback to refine risk levels.

#### Data Input:

| Source                  | Headline                | Content                                                      | Date       |
|--------------------------|-------------------------|--------------------------------------------------------------|------------|
| "CDC API"               | "Dengue Fever outbreak" | "CDC reports dengue fever cases surging in tropical regions." | 2024-11-30 |
| "WHO API"               | "Influenza alert"       | "WHO warns of influenza strains spreading in colder climates." | 2024-11-28 |

#### Data Output:

- **Content**: "CDC reports dengue fever cases surging in tropical regions."  
  **Risk Classification**: High  

- **Content**: "WHO warns of influenza strains spreading in colder climates."  
  **Risk Classification**: Moderate  

---

### **Data Inference Iteration 3**

**Δ in Features Implemented:**

1. **Advanced Web Scraping**: Scraped multiple sources dynamically using `requests`, `BeautifulSoup`, and `Scrapy`.  
2. **Real-Time Risk Categorization**: Integrated a fine-tuned NLP model for dynamic risk assessments.  
3. **Actionable Output**: Generated JSON output for app integration.  
4. **Error Handling**: Enhanced reliability with robust error checks.

#### Data Input:

| Source                      | Headline                   | Content                                                      | Date       |
|------------------------------|----------------------------|--------------------------------------------------------------|------------|
| "https://www.cdc.gov/travel" | "New Malaria Strain Detected" | "CDC warns of new malaria strain spreading rapidly."           | 2024-12-01 |
| "https://www.who.int/emergencies" | "Mild Flu Cases on the Rise" | "WHO notes mild increase in flu cases globally."             | 2024-11-28 |

#### Data Output:

- **Content**: "CDC warns of new malaria strain spreading rapidly."  
  **Risk Classification**: High  

- **Content**: "WHO notes mild increase in flu cases globally."  
  **Risk Classification**: Moderate  

---

## **Evaluation of Danger / Classification Threshold**

The algorithm evaluates danger levels (e.g., High, Moderate, Low) through:

1. **Keyword Detection**:
   - Keywords such as “malaria,” “outbreak,” or “cases rising” indicate risk levels.  
   - Risk thresholds:
     - **High**: Severe, rapidly spreading diseases.
     - **Moderate**: Seasonal illnesses with less severity.
     - **Low**: Routine advisories or minimal health impact.

2. **NLP Sentiment/Context Analysis**:
   - Evaluates urgency and severity based on frequency of risk words, tone, and context (e.g., "spreading rapidly").

3. **User Feedback Loop**:
   - Real-world feedback adjusts predictions (e.g., overriding initial risk levels).

4. **Dynamic Thresholds**:
   - Learns over time by recalibrating thresholds based on feedback data.

---

## **Future Iteration Improvements**

1. **Enhanced Risk Classification**: Use deep learning models for nuanced predictions and probabilistic scoring.  
2. **Geographic Context**: Add geotagging and GIS for precise location mapping.  
3. **Dynamic Language Support**: Scrape non-English sources with translation APIs.  
4. **API Integration**: Shift to CDC/WHO APIs for scalable, structured data.  
5. **Feedback Incorporation**: Build a dashboard for real-time updates and reinforcement learning.  
6. **Edge Deployment**: Optimize models for offline functionality on mobile devices.  
7. **Data Visualization**: Introduce interactive maps and filters for better user insights.

---

This document outlines the technical features, iteration history, and roadmap for future improvements to enhance GlobeGuard's functionality and user experience.

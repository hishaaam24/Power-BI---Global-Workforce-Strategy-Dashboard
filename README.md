# 🌍 Global Workforce Strategy Dashboard (Power BI)


**A strategic decision-support tool designed for Global Recruitment Managers to identify high-value, low-cost talent hubs across 100+ countries.**

---



## 💼 Business Problem
**The Challenge:**
A remote-first tech company needs to hire 10 Senior Developers but has a limited budget. Hiring solely in the US/Western Europe is too expensive. The Head of Talent needs to find "hidden gem" markets—countries with a high supply of specific technical talent (e.g., Python, React) but lower average salary expectations.

**The Goal:**
Build a dynamic dashboard that allows the recruitment team to:
1.  **Locate** global talent hotspots for niche skills.
2.  **Compare** average salaries across different regions.
3.  **Assess** candidate seniority (Junior vs. Senior) to ensure quality hires.

---

## 🛠 The Solution
I developed an interactive **Power BI Dashboard** using the [70k+ Job Applicants Dataset](https://www.kaggle.com/datasets/ayushtankha/70k-job-applicants-data-human-resource/data). This tool transforms raw survey data into actionable market intelligence.

### **Live Interactive Demo**
👉 **[View the Live Dashboard Here]([Insert_Your_Fabric_or_NovyPro_Link_Here])**

---

## ❓ Key Business Questions Answered
This dashboard guides the user through a 3-step decision framework:

| Category | Business Question | Metric / Visual |
|:---|:---|:---|
| **1. Geo-Arbitrage** | *"Which countries offer the best balance of talent supply vs. cost?"* | **Global Talent Map:** Bubble size = Candidate Volume, Color = Avg Salary. |
| **2. Feasibility** | *"If we target Brazil for 'Python', is the talent pool deep enough?"* | **Skills Bridge Chart:** Filters the entire report by specific tech stacks. |
| **3. Pricing** | *"What is the fair market rate for a Senior Dev (10+ YOE) in this region?"* | **Salary Trend Line:** Correlates `YearsCodePro` with `PreviousSalary`. |

---

## ⚙️ Data Modeling & Technical Implementation
### **1. The "Many-to-Many" Challenge**
The raw data contained a `Skills` column with multiple values per row (e.g., "Python;Java;SQL").
* **Problem:** Power BI cannot filter by individual skills in this format.
* **Solution:** I implemented a **Bridge Table Architecture**.
    * Created a separate `Skills_Bridge` table using Power Query to split the delimited text into unique rows.
    * Established a **One-to-Many Relationship** with **Bi-Directional Filtering** enabled.
    * *Result:* Users can now slice the entire report (Salaries, Experience, Map) by a single skill like "Rust" or "Go."

### **2. DAX Calculations**
Key measures created for the analysis:
* **`Avg Market Salary`**: Calculates the average `PreviousSalary` while handling currency outliers.
* **`Talent Density`**: A distinct count of `Respondent_ID` to measure market depth.


### **3. Data Cleaning (Power Query)**
* **Null Handling:** Imputed missing `EdLevel` values with "Not Specified" to maintain data integrity.

---

## 📸 Dashboard Preview
<img width="1438" height="807" alt="image" src="https://github.com/user-attachments/assets/78ecb7f8-61c2-4a6c-b3da-42bc3e5d5cb2" />

---

## 🚀 Key Insights from Analysis
* **The "Hidden Gem" Strategy:** Eastern Europe (specifically **Poland**) offers a high density of **Python/Java** developers with 5+ years of experience at **~40% lower cost** than Western Europe.
* **The Experience Premium:** In the US, salaries plateau after 15 years of experience, whereas in emerging markets (India/Brazil), the salary curve remains linear, suggesting high competition for senior talent.
* **Education vs. Skills:** Data shows that for **Web Development** roles, candidates with a Bachelor's degree earn nearly the same as those with a Master's, indicating that "Degree Inflation" does not correlate with market value in this specific sector.

---



---


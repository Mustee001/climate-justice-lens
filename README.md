# 🌍 Climate Justice Lens  
### *Who Suffers Most from a Crisis They Didn’t Create?*  
**An AI-driven tool for UN SDG 13: Climate Action**

![Climate Justice Plot](climate_justice_plot.png)

This project reveals **global climate injustice** by combining historical vulnerability data with modern emissions to identify countries that face the highest climate risks despite contributing the least to the crisis.

Built with **Python, scikit-learn, and open data** — 100% free and reproducible.

---

## 🔍 Problem Addressed (SDG 13)

Climate change impacts are deeply unequal:  
- The **top 10% of emitting nations** caused over **50% of historical CO₂**  
- Yet the **most vulnerable nations** — often low-emitting — suffer the worst floods, droughts, and heatwaves  

This tool helps **NGOs, educators, and policymakers** prioritize support for those who need it most.

---

## 🧠 Methodology & Innovation

### **Data Sources**
- **ND-GAIN Index (1995–2014)** → [Official Download](https://gain-new.crc.nd.edu/about/download)  
  - Overall vulnerability, GDP, population (scaled 0–1 scores)
- **Our World in Data (1990–2023)** → [CO₂ Dataset](https://github.com/owid/co2-data)  
  - Cumulative national emissions

---

### **Key Innovation: Climate Justice Score**

```python
justice_score = vulnerability / (cumulative_co₂ + 1)
```

- **High score** = High vulnerability + Low historical emissions → **Priority for global support**  
- **Low score** = High emitter + Low vulnerability → **Should fund adaptation**

---

### **ML Technique**

- **Unsupervised Learning**: K-Means clustering to group countries into:  
  - 🔴 **Low Emitter, High Vulnerability** (e.g., Grenada, Seychelles)  
  - 🔵 **High Emitter, Low Vulnerability** (e.g., USA, Germany)  
  - 🟢 **Balanced**

---

## 📤 Outputs

- `climate_justice_lens.ipynb` → Full analysis with interactive plot  
- `climate_justice_priority.csv` → Ranked list of priority countries for action  

---

### ▶️ How to Run

1. **Download the ND-GAIN dataset**  
   Go to [https://gain-new.crc.nd.edu/about/download](https://gain-new.crc.nd.edu/about/download) and download the ZIP file (e.g., `ND-GAIN_2022.zip`).

2. **Open the notebook in Google Colab**  
   Upload `climate_justice_lens.ipynb` to [Google Colab](https://colab.research.google.com).

3. **Upload and extract the ZIP in Colab**  
   - Run the first code cell, which will prompt you to upload the ZIP file.  
   - After uploading, Run the second cell, the notebook **automatically extracts** it into a folder named `Resources/` (with a capital "R").  
   - All data files (e.g., `Resources/resources/Vulnerability/vulnerability.csv`) are then loaded from this extracted structure.

4. **Run all cells**  
   The rest of the notebook will:
   - Load vulnerability, GDP, and population scores from the `Resources/` folder  
   - Fetch modern CO₂ data from Our World in Data  
   - Compute the Climate Justice Score and generate the priority list  

> 💡 **No local setup needed** — everything runs in the free Google Colab cloud environment.

---

## ⚖️ Ethical Reflection

- **Bias Awareness**: ND-GAIN data ends in 2014; newer conflicts or infrastructure changes may not be reflected.  
- **Data Gaps**: Urban heat and rural vulnerability may be underrepresented.  
- **Fairness Focus**: Prioritizes **support over blame** — empowering vulnerable nations with actionable insights.  

---

## 🌟 Why This Matters

> “AI can be the bridge between innovation and sustainability.” — UN Tech Envoy  

This project turns data into **justice** — ensuring climate action is **equitable, transparent, and human-centered.**

---

**Built for the PLP Academy AI for Sustainable Development Assignment — Week 2**  
*Code for a better world 🌍*
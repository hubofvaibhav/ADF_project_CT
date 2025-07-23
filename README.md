# Azure Data Factory (ADF) Project

This repository contains Azure Data Factory pipelines, datasets, and linked services designed for the following workflows:

## 🔧 Features

### 1. **Country Data Fetch Pipeline**
- Fetches data for 5 countries (`india`, `us`, `uk`, `china`, `russia`) from a public REST API.
- Stores each country’s data as a separate JSON file in Azure Data Lake Storage (ADLS).
- Scheduled to run **twice daily** at **12:00 AM** and **12:00 PM IST**.

### 2. **Customer Data Copy Pipeline**
- Connects to a SQL database and checks the count of customer records.
- If the count is greater than **500**, it copies data to ADLS.
- Passes the count as a parameter to a child pipeline.

### 3. **Product Data Copy (Child Pipeline)**
- Triggered by the parent pipeline.
- Copies product data only if customer count exceeds **600**.

---

## 📁 Directory Structure

```
ADF_Project/
├── Pipelines/
│   ├── CountryData_Pipeline.json
│   ├── CustomerCopy_Pipeline.json
│   └── ProductCopy_Pipeline.json
├── Datasets/
│   ├── REST_Country_API_Dataset.json
│   ├── ADLS_JSON_Output_Dataset.json
│   ├── SQL_Customers_Dataset.json
│   └── SQL_Products_Dataset.json
├── LinkedServices/
│   ├── REST_LinkedService.json
│   ├── ADLS_LinkedService.json
│   └── SQL_DB_LinkedService.json
```

---

## 🚀 Deployment

### GitHub
1. Clone the repository.
2. Upload JSON templates to Azure Data Factory via Git Integration.
3. Ensure all linked services are correctly configured with credentials.

### ADF Studio
- Go to **Manage > Git Configuration**
- Connect your GitHub repository
- Publish from collaboration branch

---

## 🔐 Notes
- Replace placeholder values like `<your_storage_account>`, `<your_server>`, `<your_db>` with actual values.
- Add secure authentication settings as needed.

---

## 👤 Author

**Vaibhav Saxena**  
Data Engineering Intern | Celebal Technologies

---

## 📄 License

This project is intended for educational and demonstration purposes.
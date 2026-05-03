# Alstom Assessment 2026 #

**Author:** Thanarat Ponpanasak

- **Jenkins:** https://www.jenkins-thanarat.com
- **GitHub:** https://github.com/ohlalapoy

---

## 1. How did you test your pipelines?

### Task B

**Steps:**

1. Navigate through **Alstom Assignment 2026** → Click **TaskB**
![alt text](Jenkinsproject.png)
2. After the job has been completed successfully, `doc.tar.gz` will appear and be ready to download.
![alt text](TaskB.png)
3. Extract the file, then open the `.html` file from the output folder.
![alt text](DownloadFile.png)

The Doxygen-generated HTML documentation was successfully produced, including:
![alt text](Doxygen-Demo.png)


![alt text](Demo2.png)

---

## 2. How did you test repoC python?

### Task C

**Steps:**

1. Navigate through **Alstom Assignment 2026** → Click **TaskC**
![alt text](TaskC.png)
2. After the job has been completed successfully, the following artifacts will be available to download:
![alt text](ResultTaskC.png)

> **Note:** These logs are automatically generated from TaskB, so you don't have to upload them yourself.

---

### Parse and Reverse to .csv

The Python script in TaskC parses the raw compiler warning log and converts it into a structured `.csv` file.
![alt text](CSV.png)

**Example warning types found in the raw log:**
![alt text](Rawlog.png)

---
## 3. What is the advantage to use LFS?


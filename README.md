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

Git LFS comes to support when you have to push or pull a large file changes to the repo e.g. video or any files more than 100MB,
instead of pulling everything but git will refer to its pointer which is reduce time and be able to amend what it really needs.

---
## 4. How to adjust this repository to support LFS?
Refer : https://github.com/git-lfs/git-lfs#installing

from my understanding, we just have to mark them as track to what we need to skip instead of directly pull them. 
$ git lfs track "*.mp4" or if you don't need lfs, you can simply add unnecessarily to .gitignore or separate large file to different location.
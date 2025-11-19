I'm testing he push event.
Test 2
You're looking for a cheat sheet specifically covering all the topics in your syllabus for the exam. Here is a concise summary of the essential concepts, commands, and expected outcomes for each syllabus section.

---

# 📝 SE Exam Syllabus Cheat Sheet (KMIT B.Tech III Year I Sem)

## I. UML Diagrams (The Definite Question)

| Diagram | Purpose | Key Elements & Flow | Lab Source |
| :--- | :--- | :--- | :--- |
| **Use Case Diagram** | [cite_start]Maps system functionality to **actors** (users)[cite: 234]. | [cite_start]**Actors** (Users, Admin, Student, Professional) [cite: 125, 127, 129, 132, 135] [cite_start]and **Use Cases** (e.g., Upload Document, Ask Question, View Answer)[cite: 238, 240, 244]. | Page 17 |
| **Class Diagram** | [cite_start]Shows the static structure: **classes**, **attributes**, **operations**, and their relationships[cite: 251]. | [cite_start]Classes include **DocumentManager**, **VectorDB**, **QuestionProcessor**, **AnswerGenerator**, **MemoryManager**, and **FeedbackManager**[cite: 253, 255, 264, 257, 267, 260]. | Page 18 |
| **Sequence Diagram** | [cite_start]Shows the **time-ordered** flow of interactions for a single task[cite: 271]. | Vertical lifelines for objects (**User**, **UI**, **VectorDB**, **GeminiAPI**). [cite_start]Messages include `Ask Question`, `search Embedding`, and `return Answer`[cite: 272, 273, 280, 285]. | Page 19 |
| **Component Diagram**| [cite_start]Shows the physical **structure** and grouping of code components[cite: 291]. | [cite_start]Components include **Frontend UI React**, **Backend API Flask**, **Vector Database**, and **Gemini API**[cite: 295, 300, 296, 299]. | Page 20 |

***

## II. Jenkins CI/CD (2, 3 Pipelines, Script, Webhooks, Email)

| Topic | Key Commands / Configuration Steps | Lab Reference |
| :--- | :--- | :--- |
| **2/3-Pipeline (Freestyle)** | [cite_start]**Upstream Job** (`Build`): SCM $\to$ Goals: `clean install` [cite: 3454] [cite_start]$\to$ Post-build: **Build other projects** (`Test`)[cite: 3456]. | Page 116, 118 |
| **Scripted Pipeline** | [cite_start]Define in one job under the **Pipeline** section[cite: 3480]. [cite_start]Commands run in `steps { sh 'command' }`[cite: 3480]. [cite_start]**Key stages:** `clone`, `install`, `test`, `package`[cite: 3480, 3481]. | Page 139 |
| **GitHub Webhooks** | 1. [cite_start]**Jenkins Job:** Check **GitHub hook trigger for GITScm polling**[cite: 3561]. 2. [cite_start]**GitHub Settings:** Payload URL must be `https://<ngrok_url>/github-webhook/`[cite: 3556]. | Page 163, 165 |
| **Email Configuration** | [cite_start]**Prerequisite:** Enable 2-Step Verification and get a **16-digit App Password** from Gmail[cite: 3570]. [cite_start]**Jenkins Global Config:** SMTP Server (`smtp.gmail.com`), Port (`465`), Use SSL, User Name/App Password[cite: 3575]. [cite_start]**Job Action:** Add **Editable Email Notification** $\to$ set **Triggers** (e.g., Failure, Success)[cite: 3579]. | Page 169-173 |

***

## III. Minikube & Nagios

| Topic | Key Commands / Concept | Purpose | Lab Reference |
| :--- | :--- | :--- |
| **Minikube Deployment** | [cite_start]`kubectl create deployment <name> --image=<image>` [cite: 3532] | Creates the application based on a Docker image (Pod template). | Page 150 |
| **Scaling** | [cite_start]`kubectl scale deployment <name> --replicas=<N>` [cite: 3535] | Adjusts the number of running application instances (Pods). | Page 151 |
| **Service Access** | [cite_start]`kubectl expose deployment <name> --type=NodePort --port=<P>` [cite: 3534] | Creates a stable network endpoint accessible from outside the cluster. | Page 151 |
| **Nagios Run** | [cite_start]`docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest` [cite: 3538] | Deploys the Nagios monitoring tool using Docker, exposing it on port 8888. | Page 153 |
| **Nagios Access** | [cite_start]URL: `http://localhost:8888`[cite: 3539]. [cite_start]Credentials: **nagiosadmin** / **nagios**[cite: 3539]. | [cite_start]Accesses the dashboard to monitor host/service status (e.g., CPU, Memory)[cite: 3544]. | Page 154 |

***

## IV. AWS Deployment

| Prerequisite | Key Action / Command | Expected Outcome | Lab Reference |
| :--- | :--- | :--- | :--- |
| **EC2 Setup** | [cite_start]Choose **Ubuntu** AMI, **t2.micro** instance type[cite: 3584, 3585]. [cite_start]Generate a **Key Pair** (`.pem` file)[cite: 3585]. | [cite_start]Instance is created and running[cite: 3586]. | Page 170-171 |
| **Network Security** | [cite_start]Configure the **Security Group** to allow inbound traffic on **HTTP** (Port 80) and **HTTPS** (Port 443)[cite: 3585]. | Allows public access to the web application. | Page 171 |
| **Connection** | [cite_start]`ssh -i <key-pair.pem> ubuntu@<Public-IP>` [cite: 3587] | Connects securely to the Ubuntu EC2 machine. | Page 172 |
| **Deployment** | [cite_start]Clone Maven Web Project [cite: 3591] [cite_start]$\to$ `docker build` [cite: 3591] [cite_start]$\to$ `docker run -p 80:80`[cite: 3592]. | Application is running inside a container on the EC2 machine. | Page 180-181 |
| **Public Access** | [cite_start]Access the EC2 instance's **Public IPv4 address** in a browser[cite: 3605]. | [cite_start]The application webpage is successfully displayed[cite: 3605]. | Page 189 |

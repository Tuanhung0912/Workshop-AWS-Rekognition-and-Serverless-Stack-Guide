---
title: "Clone and Setup Front-End"
date: 2024-06-17
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

### Clone Project from Github Repository

**1. Clone the Project using the Github Repository link**

{{% notice note %}}
First, please download and install the Javascript runtime environment to be able to run the project.
{{% /notice %}}

- Reference installation link: [node.js](https://nodejs.org/en)

![Node js](/images/2.Prerequiste/nodejs_1.png)

{{% notice info %}}
Next, please download and install a popular code editor such as Visual Studio Code or any equivalent code editor.
{{% /notice %}}

- Reference installation link: [Visual Studio Code](https://code.visualstudio.com/)

![Vs code Install](/images/2.Prerequiste/vscode_6.png)

- Next, go to the [project's github link](https://github.com/Tuanhung0912/Workshop-AWS-Rekognition-and-Serverless-Stack-Guide.git)
- Click the green **Code** button and copy the Repository link as shown below:

![Github Page](/images/2.Prerequiste/github_frontend.png)

- After accessing and copying the Repository link,
- Open **Command Prompt** in the folder where you want to store the Project as shown below

![Terminal Page 1](/images/2.Prerequiste/terminal_1.png)

- Clone the Project into your desired folder with the following command:

```bash
git clone https://github.com/Tuanhung0912/Workshop-AWS-Rekognition-and-Serverless-Stack-Frontend.git
```
![Terminal Page 2](/images/2.Prerequiste/terminal_2.png)

- After cloning the Project from the Repository, you will see the result as shown below:

![Terminal Page 3](/images/2.Prerequiste/terminal_3.png)


**2. Open the Project and Setup**
- After successfully cloning the Project from the Repository,
- Now, quickly open the Project using **Command Prompt** as shown below:

![Terminal Page 4](/images/2.Prerequiste/terminal_4.png)

- After entering the command in **Command Prompt** to open the project, you will see the result as shown below:

![Vs Code 1](/images/2.Prerequiste/vscode_1.png)

- Next, install the necessary **dependencies and libraries** for the project to run in the **node.js** runtime environment.
- Open a **Terminal** in the Project and enter the following command:

```bash
npm install
```

- Wait 1-2 minutes for the installation to complete.
- After installing the necessary libraries, a **node_modules** folder will appear in the Project as shown below:

![Vs Code 2](/images/2.Prerequiste/vscode_2.png)

- Next, update the libraries for **Vite** with the following command:

```bash
npm update vite
```

- After running the above command to update the necessary libraries for **Vite**, you will see the result as shown below:

![Vs Code 3](/images/2.Prerequiste/vscode_3.png)

**3. Run the Project**
- Next, enter the following command to start the website:

```bash
npm run dev
```

- After running the above command, the Terminal will display the following result:

![Vs Code 4](/images/2.Prerequiste/vscode_5.png)

- Visit [http://localhost:5173/](http://localhost:5173/) to launch the website.
- Wait 1-2 minutes for the Project to build on the first run.
- After the build is complete, the website will be displayed as shown below:

![Web Page 1](/images/2.Prerequiste/webpage_2.png)

You have completed the first step to set up and launch
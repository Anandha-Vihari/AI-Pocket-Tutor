![github](https://img.shields.io/badge/GitHub-000000.svg?style=for-the-badge&logo=GitHub&logoColor=white)
![markdown](https://img.shields.io/badge/Markdown-000000.svg?style=for-the-badge&logo=Markdown&logoColor=white)

<h1 align=center>Google GenAI Exchange Hackathon</h1>
<h2 align=center>Millenium Falcons<br>Pocket Tutor</h2>

## Overview
Imagine having a smart tutor at your fingertips, ready to help whenever you need it. That’s what **Pocket Tutor** is all about. It’s like having a personal AI teacher who can answer your questions, explain tricky concepts, and even help you understand pictures and diagrams.

With Pocket-Tutor, learning doesn’t have to be boring or confusing. You can ask it anything, from simple questions to complex problems, and it will do its best to give you a clear and helpful answer. Plus, it can help you make sense of all those graphs, charts, and other visuals that can be so confusing.

It’s like having a personal learning companion that’s always there when you need it.
>[!NOTE]
>### Key Features:
> - ***Text Processing:*** Pocket-Tutor's advanced text processing capabilities ensure you receive clear, concise, and informative answers.
>
> - ***Image Processing:*** Break down complex visuals with ease. Our image processing features help you understand images better by extracting text and interpreting visual concepts, making learning >more engaging and effective.
>
> - ***Document Processing:*** Simplify the task of comprehending complex documents. Pocket-Tutor can assist you in understanding key points, summarizing information, and extracting relevant data >from various types of documents.
>
> - ***Course Suggestions:*** Explore a curated collection of courses tailored to your learning goals. Pocket-Tutor's intelligent algorithms can recommend courses that align with your interests and >help you stay motivated.
>
>- ***Videos and Revision Stuffs:*** Access a vast library of educational videos and revision materials. Whether you need a quick refresher or in-depth explanations, Pocket-Tutor has you covered.

>[!IMPORTANT]
>**As for now, we were able to create the web version of Pocket-Tutor. However, we are all motivated and fired up as we are working for its Mobile App version using react-native.**

## Setting it up in your local envirornment
### Clone the repository
HTTPS:
```
git clone https://github.com/Millenium-Falcons/Pocket-Tutor.git
```
or, SSH:
```
git clone git@github.com:Millenium-Falcons/Pocket-Tutor.git
```
using either of the command should clone the main branch into your local storage. Now we are ready to set it up further.
### Database
Setting up a database is a very crucial step for this application to execute. To do so, please read the following instruction.
- **Create the database:** Open your MongoDB account and create a database with the name `Pocket_Tutor`
- **Create the collections inside the database:** Once the database is created, create the following collections as mentioned below in the image

![241002_19h18m53s_screenshot](https://github.com/user-attachments/assets/a934531a-3458-4208-b067-563d51cddde7)
Each collection should have the following fields respectively with their respective datatypes as mentioned in the images below
<div align="center">
  
|![241002_19h23m19s_screenshot](https://github.com/user-attachments/assets/94a6d8a4-ec89-48d1-9474-d67245e60feb)|![241002_19h25m32s_screenshot](https://github.com/user-attachments/assets/c7a4e696-9f76-4a5e-8084-6256ebdb8d54)|
|---|---|
|![241002_19h28m34s_screenshot](https://github.com/user-attachments/assets/6ea839d1-1c70-41c3-a6e8-836a999b09e0)|![241002_19h31m41s_screenshot](https://github.com/user-attachments/assets/96b16efe-1357-415c-99a7-33338084f64b)|
</div>
If correctly configured to these parameters, now you are good to go ahead.

### Frontend
The website is written using a javascript framework React.js. For setting up the frontend, please read the following instructions:***

Navigate into the cloned repository and go inside the `Frontend` directory
```
cd Pocket-Tutor
cd Frontend
```
now use `npm` to execute the frontend over your localhost
```
npm run dev
```
### Gemini Assistant
It is written in python and is deployed in the form of an API using FastAPI. It is responsible for processing text, images and documents for providing constructive responses. For setting up the GenAI, please read the following instructions:***

Navigate in the cloned repository and go inside the `gemini_assistant` directory
```
cd Pocket-Tutor
cd gemini_assistant
```
Install the required modules and dependencies using this command
```
pip install -r requirements.txt
```
---
#### Environment Variables
![241002_18h53m57s_screenshot](https://github.com/user-attachments/assets/00f4dc31-5e08-4bae-be98-88d48571fb1e)

Once inside the `gemini_assistant` directory, you need to create a `.env` file insde it to setup the environment variables. Following variables should be inside the file
- `API_KEY`: setup an API from the `Google AI Studio` and paste it for this parameter
- `MONGODB_URI`: use your MongoDB URI to connect to your database
---
Now that your environment variables are all good to go, all you need to do is fire up the API using this command
```
python -m uvicorn deploy:app --reload
```
And you can now use this GenAI API over your localhost **(127.0.0.1:8000)**

### Backend
It is written in a node.js framework called Express.js, and it serves as an medium for the frontend and the generative AI to communicate. For setting up the backend, please read the following instructions:***

Navigate into the cloned repository and go inside the `backend` directory
```
cd Pocket-Tutor
cd backend
```
---
#### Environment Variables
<div align="left">
  
![241002_18h39m16s_screenshot](https://github.com/user-attachments/assets/c38433f7-b6d3-4fd0-a178-39e6a3c8d1e0)
</div>

Once inside the `backend` directory, you need to create another `.env` file insde it to setup the environment variables. Following variables should be inside the file
- `PORT`: set it to the value 3001
- `DB_URI`: use your MongoDB URI to connect to your database
- `API_KEY`: use the same API used for the `.env` in `gemini_assistant` directory and paste it here
---
Now that your environment variables are all good to go, all you need to do is fire up the backend using this command
```
node index
```
And you can now use this backend over your localhost **(127.0.0.1:3001)**

# Local Multimodal AI Chat
## Getting Started

To get started with Local Multimodal AI Chat, clone the repository and follow these simple steps:

### Easiest and Preferred Method: Docker Compose
1. **Set model save path**: Line 21 in the docker-compose.yml file

2. **Enter command in terminal**: ```docker compose up```
   
   Note: If you don't have a GPU, you can remove the deploy section from the docker compose file.

3. **Optional**: 
   - Check the config.yaml file and change accordingly to your needs.
   - Place your user_image.png and/or bot_image.png inside the chat_icons folder and remove the old ones. 

4. **Open the app**: Open [0.0.0.0:8501](http://0.0.0.0:8501) in the Browser

5. **Pull Models**: Go to https://ollama.com/library and choose the models you want to use. Enter ```/pull MODEL_NAME``` in the chat bar. 
You need one embedding model e.g. [nomic-embed-text](https://ollama.com/library/nomic-embed-text) to embed pdf files (change embedding model in config if you choose another). You also need a model which undertands 
images e.g. [llava](https://ollama.com/library/llava) 

6. **Optional**: 
   - Check the config.yaml file and change accordingly to your needs.
   - Place your user_image.png and/or bot_image.png inside the chat_icons folder and remove the old ones. 

### Recommendation for Windows
Using ollama docker container results in very slow loading times for the models due to system calls being translated between two kernels. Installing Ollama locally works best here.


1. **Install [Ollama](https://ollama.com/download) desktop**

2. **Change Docker Compose file**: remove docker-compose.yml and rename docker-compose_without_ollama.yml to docker-compose.yml

3. **Change Ollama Base URL in config.yaml**: Use line 4 in the config.yaml file and remove line 3

3. **Enter command in terminal**: ```docker compose up```

4. **Open the app**: Open [0.0.0.0:8501](http://0.0.0.0:8501) in the Browser

5. **Pull Models**: Go to https://ollama.com/library and choose the models you want to use. Enter ```/pull MODEL_NAME``` in the chat bar. 
You need one embedding model e.g. [nomic-embed-text](https://ollama.com/library/nomic-embed-text) to embed pdf files (change embedding model in config if you choose another). You also need a model which undertands 
images e.g. [llava](https://ollama.com/library/llava) 

6. **Optional**: 
   - Check the config.yaml file and change accordingly to your needs.
   - Place your user_image.png and/or bot_image.png inside the chat_icons folder and remove the old ones. 

### Complete Manual Install

1. **Install [Ollama](https://github.com/ollama/ollama)**

2. **Create a Virtual Environment**: I am using Python 3.10.12

3. **Install Requirements**:
   - ```pip install --upgrade pip```
   - ```pip install -r requirements.txt```
   - ```pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu```   

4. **Enter commands in terminal**: 
   1. ```python3 database_operations.py``` This will initialize the sqlite database for the chat sessions.
   2. ```streamlit run app.py```

5. **Pull Models**: Go to https://ollama.com/library and choose the models you want to use. Enter ```/pull MODEL_NAME``` in the chat bar. 
You need one embedding model e.g. [nomic-embed-text](https://ollama.com/library/nomic-embed-text) to embed pdf files and one model which undertands 
images e.g. [llava](https://ollama.com/library/llava) 

6. **Optional**: 
   - Check the config.yaml file and change accordingly to your needs.
   - Place your user_image.png and/or bot_image.png inside the chat_icons folder and remove the old ones. 


## Overview

Local Multimodal AI Chat is a multimodal chat application that integrates various AI models to manage audio, images, and PDFs seamlessly within a single interface. This application is ideal for those passionate about AI and software development, offering a comprehensive solution that employs Whisper AI for audio processing, LLaVA for image management, and Chroma DB for handling PDFs.

I welcome contributions of all forms. Whether you’re introducing new features, optimizing the code, or correcting bugs, your participation is valued. This project thrives on community collaboration and aims to serve as a robust resource for those interested in the practical application of multimodal AI technologies.


## Features

- **Local Model Processing with Ollama**: This app utilizes the Ollama server for running local instances of models, providing a powerful and customizable AI experience without the need for external cloud dependencies. This setup is ideal for maintaining data privacy and improving response times.

- **Integration with OpenAI API**: For broader AI capabilities, this application also connects to the OpenAI API, enabling access to a wide range of cutting-edge AI models hosted externally. This feature ensures the app remains versatile and capable of handling a variety of tasks and queries efficiently.

- **Audio Chatting with Whisper AI**: Leveraging Whisper AI's robust transcription capabilities, this app offers a sophisticated audio messaging experience. The integration of Whisper AI allows for accurate interpretation and response to voice inputs, enhancing the natural flow of conversations.
[Whisper models](https://huggingface.co/collections/openai/whisper-release-6501bba2cf999715fd953013)

- **PDF Chatting with Chroma DB**: The app is tailored for both professional and academic uses, integrating Chroma DB as a vector database for efficient PDF interactions. This feature allows users to engage with their own PDF files locally on their device. This makes it a valuable tool for personal use, where one can extract insights, summaries, and engage in a unique form of dialogue with the text in their PDF files. [Chroma website](https://docs.trychroma.com/)

## Contact Information

If you're interested in working with me, feel free to contact me via email.

- Email: sumanthnshettigar@gmail.com

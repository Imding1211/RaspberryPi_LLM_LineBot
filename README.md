<a id="readme-top"></a>
# RaspberryPi_LLM_LineBot


<ol>
  <li><a href="#about-the-project">About The Project</a></li>
  <li><a href="#built-with">Built With</a></li>
  <li><a href="#getting-started">Getting Started</a></li>
  <li><a href="#contact">Contact</a></li>
</ol>

## About The Project

The RaspberryPi_LLM_LineBot is an intelligent chatbot built for the LINE messaging platform, leveraging AI capabilities on a Raspberry Pi. The bot uses the Ollama language model, specifically the Gemma2 2b, to provide insightful responses to users' queries. This project demonstrates how to integrate a powerful AI model into a lightweight, portable environment like the Raspberry Pi, making it accessible and easy to deploy.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Built With

* Flask
* line-bot-sdk
* Ollama
* Gemma2 2b
  
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

Go to the Line Developer to create your messaging API.

[Line Developer](https://developers.line.biz/zh-hant/services/messaging-api/)

To get a local copy up and running, follow these simple steps.

1. Create a new conda environment
   ```sh
   conda create --name RaspberryPi_LLM_LineBot python=3.11
   ```
   
2. Activate environment
   ```sh
   conda activate RaspberryPi_LLM_LineBot
   ```

3. Clone the repo
   ```sh
   git clone https://github.com/Imding1211/RaspberryPi_LLM_LineBot.git
   ```
   
4. Change directory
   ```sh
   cd RaspberryPi_LLM_LineBot
   ```
   
5. Install the required Python packages
   ```sh
   pip install -r requirements.txt
   ```
   
6. Install Ollama on Raspberry Pi with one command
   ```sh
   curl -fsSL https://ollama.com/install.sh | sh
   ```

8. Activate Ollama
   ```sh
   ollama serve
   ```
   You can open the browser and enter http://127.0.0.1:11434 to check if the Ollama server is operating normally.

9. Download the Gemma2 2b
   ```sh
   ollama run gemma2:2b
   ```

10. Add your Line token and secret to the token and secret variables in main.py.
    ```sh
    token = 'your Line token'
    secret = 'your Line secret'
    ```
   
11. Install Ngrok

    [Download Ngrok](https://ngrok.com/download)

12. Activate Flask
    ```sh
    nohup python main.py > RaspberryPi_LLM_LineBot.log 2>&1 &
    ```

13. Activate Ngrok
    ```sh
    nohup ngrok http http://localhost:8080 > RaspberryPi_LLM_LineBot_ngrok.log 2>&1 &
    ```
   
14. Get your API URL.
    ```sh
    wget http://127.0.0.1:4040/api/tunnels
    cat tunnels
    ```

    Find "public_url," which is your API URL.

15. Paste your URL into your Line Developer Webhook URL.
    ```sh
    [Your URL]/callback
    ```
    
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Chi Heng Ting - a0986772199@gmail.com

Project Link - https://github.com/Imding1211/RaspberryPi_LLM_LineBot

<p align="right">(<a href="#readme-top">back to top</a>)</p>


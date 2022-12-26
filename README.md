# 这是一个焊接chatgpt/gpt3和vits的后端api程序
参考用链接http://43.159.36.6:8080/
项目地址https://drive.google.com/drive/folders/1vtootVMQ7wTOQwd15nJe6akzJUYNOw4d
解压live2d_chat-0.6(gpt3+chatgpt).zip，
运行游戏程序，
你也可以用renpy修改游戏程序，自定义你的live2d模型和交互方式。

## How to launch API in your windows or server
(Suggestion) Python == 3.7
## Clone a VITS repository or iSTFT-VITS repository
```sh
git clone https://github.com/CjangCjengh/vits.git
#git clone https://github.com/innnky/MB-iSTFT-VITS
```
## Adding cleaners inference_api.py to your project
- The path of inference_api.py should be like path/to/vits/inference_api.py
- If you want to launch this project in your server, it is recommanded to use iSTFT-VITS for tts: path/to/MB-iSTFT-VITS/inference_api.py
## Install requirements of vits enviornments
```sh
cd vits
#cd MB-iSTFT-VITS
pip install -r requirements.txt
```
## Install requirements for using GPT3/CHATGPT in python
```sh
pip install pydub 
pip install openai
#Not recommended due to demanding requirements
#pip install pyChatGPT
```
## Editing the path of configuration file in inference_api.py
```sh
line26:#设定存储各种数据的目录，方便查看，默认C:/project_file
line27:current_work_dir = os.path.dirname(__file__)
line28:weight_path = os.path.join(current_work_dir, '/project_file/')
line34:hps_ms = utils.get_hparams_from_file("path/to/config.json")
line43:_ = utils.load_checkpoint("path/to/checkpoint.pth", net_g_ms, None)
```
## For CPU inference in server or those who do not have cuda installed
```sh
#change this line
line32:dev = torch.device("cuda:0")
```

## launch
```sh
python inference_api.py
```

## What to do next?
As you can see in the temminal
```sh
 * Serving Flask app 'inference_api'
 * Debug mode: on
INFO:werkzeug: WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.[0m
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:8080
 * Running on http://10.0.0.14:8080
INFO:werkzeug: Press CTRL+C to quit
```
Which means you can try it in the game now




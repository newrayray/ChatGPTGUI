<img height="128" align="left" src="https://user-images.githubusercontent.com/51039745/222689546-7612df0e-e28b-4693-9f5f-4ef2be3daf48.png" alt="Logo">

# 川虎 ChatGPT / Chuanhu ChatGPT

[![LICENSE](https://img.shields.io/github/license/GaiZhenbiao/ChuanhuChatGPT)](https://github.com/GaiZhenbiao/ChuanhuChatGPT/blob/main/LICENSE)
[![Base](https://img.shields.io/badge/Base-Gradio-fb7d1a?style=flat)](https://gradio.app/)
[![Bilibili](https://img.shields.io/badge/Bilibili-%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B-ff69b4?style=flat&logo=bilibili)](https://www.bilibili.com/video/BV1mo4y1r7eE)

---

为ChatGPT API提供了一个Web图形界面。在Bilibili上[观看视频教程](https://www.bilibili.com/video/BV1mo4y1r7eE/)。也在Hugging Face上[在线体验](https://huggingface.co/spaces/JohnSmith9982/ChuanhuChatGPT)。

<img width="1420" alt="截屏2023-03-04 11 29 50 1" src="https://user-images.githubusercontent.com/51039745/222873690-d046dfa1-8941-49ff-92a2-fef34421c503.png">


## 功能
- 重试对话，让ChatGPT再回答一次。
- 优化Tokens，减少Tokens占用，以支持更长的对话。
- 设置System Prompt，有效地设定前置条件
- 保存/加载对话历史记录
- 在图形界面中添加API key

## 使用技巧

- 使用System Prompt可以很有效地设定前提条件
- 对于长对话，可以使用“优化Tokens”按钮减少Tokens占用。
- 如果部署到服务器，将程序最后一句改成`demo.launch(server_name="0.0.0.0", server_port=99999)`。其中`99999`是端口号，应该是1000-65535任意可用端口，请自行更改为实际端口号。
- 如果需要获取公共链接，将程序最后一句改成`demo.launch(share=True)`。注意程序必须在运行，才能通过公共链接访问

## 安装方式

### 填写API密钥

#### 在图形界面中填写你的API密钥

这样设置的密钥会在页面刷新后被清除

<img width="760" alt="image" src="https://user-images.githubusercontent.com/51039745/222873756-3858bb82-30b9-49bc-9019-36e378ee624d.png">


#### ……或者在代码中填入你的 OpenAI API 密钥

这样设置的密钥会成为默认密钥

<img width="552" alt="SCR-20230302-sula" src="https://user-images.githubusercontent.com/51039745/222445258-248f2789-81d2-4f0a-8697-c720f588d8de.png">

### 安装依赖

```
pip install -r requirements.txt
```

如果报错，试试

```
pip3 install -r requirements.txt
```

如果还是不行，请先[安装Python](https://www.runoob.com/python/python-install.html)。

如果下载慢，建议[配置清华源](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)，或者科学上网。

### 启动

先创建文件夹
```bash
mkdir chat-history-json
mkdir chat-history-txt
```

创建配置文件 config.ini
```bash
vim config.ini
```

```ini
[OPENAI]
api_key = your key
```
启动
```
python ChuanhuChatbot.py
```

如果报错，试试

```
python3 ChuanhuChatbot.py
```

如果还是不行，请先[安装Python](https://www.runoob.com/python/python-install.html)。

## 或者，使用Docker 安装与运行

### 构建镜像
```
docker build -t chuanhuchatgpt:latest .
```

### 一键运行
```
docker run -d --name chatgpt -e my_api_key="替换成API"  --network host chuanhuchatgpt:latest
```

### 查看本地访问地址
```
docker logs chatgpt
```


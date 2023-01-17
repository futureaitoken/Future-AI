---
cover: ../../.gitbook/assets/GITBOOK.png
coverY: 0
---

# 🔹 AI Executor with Docker

#### _<mark style="color:blue;">Installation</mark>_

#### _0. Hardware specification_

_A dedicated machine that can keep the program running continuously. The program supports Linux, Windows & MacOS._

_<mark style="color:blue;">Minimum requirement:</mark>_

```
2vCPUs
2GB RAM
```

#### _1. Docker & docker-compose_

_With docker, the AI Executor program can run on any platforms. As a result, it is a must to install and download Docker. Docker-compose is a tool for defining & running multi-container Docker applications. It is convenient to use docker-compose to work with Docker containers._

_Next, please create a file called: **docker-compose.yml** that has the following content:_

```yml
version: '3.3'
services:
  ai_executor:
    container_name: ai_executor
    image: future-ai/ai-executor:0.0.1
    tty: true
    environment:
      - PIN=${PIN}
      - DOCKER=true
    restart: on-failure
    logging:
      driver: "local"
      options:
        max-size: "100m"
        max-file: "3"
    volumes:
      - ./:/workspace
    command: ./aifuture-executor-process
```

#### 2. Download the executor zip file

_<mark style="color:blue;">Shell (Mac, Linux):</mark>_

```bash
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=180aYBeOlakKorDpHsaHImR1pFlHEGZ26' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=180aYBeOlakKorDpHsaHImR1pFlHEGZ26" -O executor.zip && rm /tmp/cookies.txt && unzip executor.zip
```

#### 3. Configure the .env file

_The .env file in the zip configures the network, wallet, and other basic variables for your program to use. All the key-value pairs are heavily commented already. If you still have questions about them, freel free to ask us, the Future-AI team._

#### _4. File checksum (optional but recommended)_

_Please follow_ [_this guildeline_](ai-executor-file-integrity.md) _to verify your executable._

#### _5. Start the container & program_

_<mark style="color:blue;">Shell (Mac, Linux):</mark>_

_Type:_

```bash
PIN=<your-pin-for-encrypted-mnemonic> docker-compose up -d
```

#### _**Windows:**_

_with powershell:_

```bash
$Env:PIN = "<your-pin-for-encrypted-mnemonic>" && docker-compose up -d
```

_If you do not use an encrypted mnemonic, then you don't have to type in the PIN variable._

#### _6. Monitoring the program_

_To view the program's log, please type the following:_

```
docker-compose logs -f --tail=100 ai_executor
```

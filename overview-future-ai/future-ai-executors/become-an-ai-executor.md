---
cover: ../../.gitbook/assets/GITBOOK.png
coverY: 0
---

# 🔹 AI Executor

#### <mark style="color:blue;">Installation</mark>

#### _0. Hardware specification_

_A dedicated machine that can keep the program running continuously. The program supports Linux, Windows & MacOS._

_<mark style="color:blue;">Minimum requirement:</mark>_

```
2vCPUs
2GB RAM
```

#### _1. Download the program_ <a href="#1" id="1"></a>

_**Shell (Mac, Linux):**_

```bash
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=180aYBeOlakKorDpHsaHImR1pFlHEGZ26' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=180aYBeOlakKorDpHsaHImR1pFlHEGZ26" -O executor.zip && rm /tmp/cookies.txt && unzip executor.zip
```

_You would probably need to install **unzip** afterward if your dedicated host does not have it._

_**Windows:**_

_For Windows users, you can download the zip and unzip it directly._

#### _2. Configure the env file_

_The .env file in the zip configures the network, wallet, and other basic variables for your program to use. All the key-value pairs are heavily commented already. If you still have questions about them, freel free to ask us, the Future-AI team._

#### _3. File checksum (optional but recommended)_

Please follow [this guildeline](ai-executor-file-integrity.md) to verify your executable.

#### _5. Run the program_

_In the zip contains the `aifuture-executor-process-*` programs, please choose one that matches your OS and run it._

_<mark style="color:blue;">If you see the following logs, then the program has run successfully:</mark>_

```
Future-AI Executor program, v0.3.5
```

_For Linux and MacOS users:_

```
./aifuture-executor-process
```

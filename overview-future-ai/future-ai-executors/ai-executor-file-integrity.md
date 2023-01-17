---
cover: ../../.gitbook/assets/GITBOOK.png
coverY: 0
---

# 🔹 AI Executor File Integrity

_File integrity is one of the most important factors when it comes to security check. One can inject a malicious program which reads & collects all sensitive data of your computer._

_As a result, the executors need to verify the integrity of the executable you are about to run. To do so, you need to compare the checksum of your program against the appropriate checksums shown here, which are provided by the Future-AI team. If they don't match, you must not run that program. Otherwise, you would risk losing your sensitive data, especially your wallet._

_<mark style="color:blue;">Below is the list of checksums for Linux, Macos, and Windows:</mark>_

```
Windows: 0e719128676a117596c21a1964cc5c20
MacOS: 40a1cad78f20e9f433572b24240e8e07
Linux: e32f6d68e187ce3ad4b2bf3cbf4be577
```

_These checksums will be updated accordingly to the latest executable's version. As of now, the current version of the executable is v0.3.4.4._

_Please follow the step below depending on the type of machine you are using to generate your local checksum:_

_**Windows & MacOS:**_

_Please use_ [_this link_](http://emn178.github.io/online-tools/md5\_checksum.html) _and upload the file. It will display its checksum. Then, please compare the checksum with the appropriate checkum above. They should match._

_**Linux:**_

_For Linux users, you can use the following command to generate the file's checksum (assuming the executable's name is **aioracle-executor-process**):_

```bash
md5sum aioracle-executor-process | cut -d ' ' -f 1
```

_The checksum should match the Linux checksum above._

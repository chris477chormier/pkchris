# PyInstaller Extractor

PyInstaller Extractor is a Python script to extract the contents of a PyInstaller generated Windows executable file. The contents of the pyz file (usually pyc files) present inside the executable are also extracted.

The header of the pyc files are automatically fixed so that a Python bytecode decompiler will recognize it. The script can run on both Python 2.x and 3.x. Pyinstaller versions 2.0, 2.1, 3.0, 3.1, 3.2, 3.3, 3.4, 3.5, 3.6, 4.0, 4.1, 4.2, 4.3, 4.4, 4.5, 4.5.1, 4.6, 4.7 are [tested](https://github.com/extremecoders-re/pyinstxtractor-test-binaries) & supported. Probably will work with other versions too.

This project was originally hosted on [SourceForge](https://sourceforge.net/projects/pyinstallerextractor/).

## How to use 

The script can be run by passing the name of the exe as an argument.

```
$ python pyinstxtractor.py <filename>
X:\>python pyinstxtractor.py <filename>
```

It is recommended to run the script in the same version of Python which was used to generate the executable. This is to prevent unmarshalling errors(if any) while extracting the PYZ archive.

## Example

```
X:\> python pyinstxtractor.py test.exe
[+] Processing dist\test.exe
[+] Pyinstaller version: 2.1+
[+] Python version: 36
[+] Length of package: 5612452 bytes
[+] Found 59 files in CArchive
[+] Beginning extraction...please standby
[+] Possible entry point: pyiboot01_bootstrap.pyc
[+] Possible entry point: test.pyc
[+] Found 133 files in PYZ archive
[+] Successfully extracted pyinstaller archive: dist\test.exe

You can now use a python decompiler on the pyc files within the extracted directory
```

After extracting the pyc's you can use a Python decompiler like [Uncompyle6](https://github.com/rocky/python-uncompyle6/).

```
X:\> uncompyle6.exe test.exe_extracted\test.pyc
X:\> uncompyle6.exe test.exe_extracted\PYZ-00.pyz_extracted\__future__.pyc
```
## Extracting Linux ELF binaries

Pyinstxtractor can now natively extract Linux ELF binaries without other additional tools.

For other questions and information, please see the [Wiki](https://github.com/extremecoders-re/pyinstxtractor/wiki/Extracting-Linux-ELF-binaries) and the [FAQ](https://github.com/extremecoders-re/pyinstxtractor/wiki/Frequently-Asked-Questions)

## License

GNU General Public License v3.0# V2Ray Heroku

**若需部署 V2Ray VLESS，请转到 [vless](https://github.com/bclswl0827/v2ray-heroku/tree/vless) 分支。**

## 概述

本专案用于在 Heroku 上部署 V2Ray WebSocket，在合理使用的程度下，本镜像不会因为大量占用资源而导致封号。

部署完成后，每次启动应用时，运行的 V2Ray 将始终为最新版本

## 部署

### 步骤

 1. Fork 本专案到自己的 GitHub 账户（用户名以 `example` 为例）
 2. 修改专案名称，注意不要包含 `v2ray` 和 `heroku` 两个关键字（修改后的专案名以 `demo` 为例）
 3. 修改 `README.md`，将 `chris477chormier/ubs` 替换为自己的内容（如 `example/demo`）

> [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/chris477chormier/ubs)

 4. 回到专案首页，点击上面的链接以部署 V2Ray

### 变量

对部署时需设定的变量名称做如下说明。

| 变量 | 默认值 | 说明 |
| :--- | :--- | :--- |
| `ID` | `9fe8ce0d-e8e0-43dc-a815-44149d664a6d` | VMess 用户主 ID，用于身份验证，为 UUID 格式 |
| `WSPATH` | `/` | WebSocket 所使用的 HTTP 协议路径 |

## 接入 CloudFlare

以下两种方式均可以将应用接入 CloudFlare，从而在一定程度上提升速度。

 1. 为应用绑定域名，并将该域名接入 CloudFlare
 2. 通过 CloudFlare Workers 反向代理

## 注意

 1. **请勿滥用本专案，类似 Heroku 的免费服务少之又少，且用且珍惜**
 2. 若使用域名接入 CloudFlare，请考虑启用 TLS 1.3
 3. AWS 绝大部分 IPv4 地址已被 Twitter 屏蔽

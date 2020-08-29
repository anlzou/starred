<!--
 * @Date        : 2020-08-29 09:50:24
 * @LastEditors : anlzou
 * @Github      : https://github.com/anlzou
 * @LastEditTime: 2020-08-30 03:00:44
 * @FilePath    : \starred\README.md
 * @Describe    : 
-->
# Starred

[![github workflow](https://github.com/maguowei/starred/workflows/ci/badge.svg)](https://github.com/maguowei/starred/actions)
![Upload Python Package](https://github.com/maguowei/starred/workflows/Upload%20Python%20Package/badge.svg)

## Install

```bash

$ pip install starred
$ starred --username maguowei --sort > README.md
```

## Usage

```bash
$ starred --help

Usage: starred [OPTIONS]

    GitHub starred

    creating your own Awesome List used GitHub stars!

    example:     starred --username maguowei --sort > README.md

Options:
    --username TEXT    GitHub username
    --token TEXT       GitHub token
    --sort             sort by language
    --repository TEXT  repository name
    --message TEXT     commit message
    --version          Show the version and exit.
    --help             Show this message and exit.
```

## Demo

```bash
# automatically create the repository
$ export GITHUB_TOKEN=yourtoken
$ starred --username yourname --repository awesome-stars --sort
```

- [`maguowei/awesome-stars`](https://github.com/maguowei/awesome-stars)
- [update awesome-stars every day by GitHub Action](https://github.com/maguowei/awesome-stars/blob/master/.github/workflows/schedules.yml) the example with GitHub Action

## FAQ

1. Generate new token

   link: [Github Personal access tokens](https://github.com/settings/tokens)

2. Why do I need a token?

   -  For unauthenticated requests, the rate limit is 60 requests per
      hour.
      see [Github Api Rate
      Limiting](https://developer.github.com/v3/#rate-limiting)
   -  The token must be passed together when you want to automatically
      create the repository.

3. Install the master branch version

    ```bash
    $ pip install -e git+https://github.com/maguowei/starred#egg=starred
    ```

## New function
- [ ] 内容折叠
- [ ] 模板
- [ ] 建立网站
- [ ] 新的爬虫算法

## Issue
```py
运行：starred --username anlzou --sort > StarList.md

报错：
......
File "c:\users\administrator\appdata\local\programs\python\python37\lib\site-packages\click\utils.py", line 260, in echo
file.write(message)
UnicodeEncodeError: 'gbk' codec can't encode character '\U0001f62e' in position 60: illegal multibyte sequence

解决如下：
utils.py->echo()函数中添加该代码：message = message.encode("utf-8")
```
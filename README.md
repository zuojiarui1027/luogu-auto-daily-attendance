# 洛谷自动打卡机

## 快速导航

1. [核心功能](https://github.com/zuojiarui1027/luogu-auto-daily-attendance/?tab=readme-ov-file#核心功能 "核心功能")
2. [原理](https://github.com/zuojiarui1027/luogu-auto-daily-attendance/?tab=readme-ov-file#原理 "原理")
3. [快速开始](https://github.com/zuojiarui1027/luogu-auto-daily-attendance/?tab=readme-ov-file#快速开始 "快速开始")

- 感谢**为项目点 star** 的观众们，**fork** 你所欲也，**star** 我所欲也，两者得兼😍是对开源精神最好的支持;

### 核心功能

为解决洛谷用户经常忘记打卡这件事，特推出此项目。

此项目能每天定时自动打卡。

### 原理

经过网络抓包发现洛谷的打卡按钮是向`htttps://www.luogu.com.cn/index/ajax_punch`发送请求。所以本项目运用python的requests库进行发送请求。

并使用GitHub action 功能运行python文件，进行每日定时打卡。

### 快速开始

**本项目使用GitHub action功能，无需下载任何东西**

1. 点击本项目上方的fork按钮进行复刻。
2. 进入复刻好的项目的settings页，并点击secrets and variables。在下拉列表中选择Action。

   ![](https://cdn.luogu.com.cn/upload/image_hosting/3ted4czu.png)
3. 点击New repository secret

   ![](https://cdn.luogu.com.cn/upload/image_hosting/5gbob7do.png)
4. 在edge浏览器中打开www.luogu.com.cn，按f12打开控制台，点击应用程序，如果找不到点旁边的加号中的应用程序。

   ![](https://cdn.luogu.com.cn/upload/image_hosting/3vi0l519.png)
5. 分别记录\_\_client\_id，\_uid，C3VK的值。
   ![](https://cdn.luogu.com.cn/upload/image_hosting/gk42o91w.png)
6. 回到GitHub，分别创建\_\_client\_id，\_uid，C3VK三个secret。
7. 创建完成

### 自定义运行时间

打开.github/workflows目录下的egg.yml

![](https://cdn.luogu.com.cn/upload/image_hosting/uolach56.png)

编辑该字段。具体编辑规则可以去搜cron即可。

注意***GitHub用的是utc时间北京是utc+8时间需要减8小时，如北京时间23：00是utc时间15:00***
***洛谷的cokkie建议每月一换否则会打卡失败***
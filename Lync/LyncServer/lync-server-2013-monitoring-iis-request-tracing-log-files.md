---
title: 监视 IIS 请求跟踪日志文件
TOCTitle: 监视 IIS 请求跟踪日志文件
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690034(v=OCS.15)
ms:contentKeyID: 49314008
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 监视 IIS 请求跟踪日志文件

 

_**上一次修改主题：** 2016-12-08_

在为 Lync Server Mobility Service 启用 Internet Information Services (IIS) 请求跟踪时，所生成的日志文件每天可占用 3 GB 的磁盘空间。默认情况下，IIS 跟踪日志记录已启用。您应监视前端服务器以确保其不会出现磁盘空间不足的情况。

默认情况下，IIS 将在 %SystemDrive%\\inetpub\\logs\\LogFiles 中存储日志文件。

若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

有关 **httpLogging** 命令的详细信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0x804)。


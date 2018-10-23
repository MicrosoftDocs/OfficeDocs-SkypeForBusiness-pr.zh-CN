---
title: Windows PowerShell 的不正确版本引起的导入模块错误
TOCTitle: Windows PowerShell 的不正确版本引起的导入模块错误
ms:assetid: 6c209f41-2b97-4dda-b0b7-e5b582d3e6b6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362802(v=OCS.15)
ms:contentKeyID: 56271157
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell 的不正确版本引起的导入模块错误

 

_**上一次修改主题：** 2015-06-22_

Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。如果您试图在 Windows PowerShell 的以前版本下导入模块，则导入过程将失败，并出现与此类似的错误消息：

    Import-Module : 加载的 PowerShell 版本为"2.0"。模块 'D:\Program Files\Common Files\Microsoft Lync Server 2013\Modules\LyncOnlineConnector\LyncOnlineConnector.psd1' 至少需要 Windows PowerShell 版本"3.0"才能运行。请确认 Windows PowerShell 安装，然后重试。

解决此问题的唯一方法是安装 Windows PowerShell 3.0，它可从 Microsoft 下载中心下载，网址为 <http://www.microsoft.com/en-us/download/details.aspx?id=29939>。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)


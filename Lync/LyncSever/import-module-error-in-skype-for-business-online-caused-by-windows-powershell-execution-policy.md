---
title: Windows PowerShell 执行策略引起的导入模块错误
TOCTitle: Windows PowerShell 执行策略引起的导入模块错误
ms:assetid: 4bc093ca-fd30-44c9-a0a3-16f78698df2b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362786(v=OCS.15)
ms:contentKeyID: 56271141
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell 执行策略引起的导入模块错误

 

_**上一次修改主题：** 2016-12-08_

Windows PowerShell 执行策略帮助确定哪些配置文件可以加载到 Windows PowerShell 控制台中以及用户可以从该控制台运行哪些脚本。在最低限度，除非执行策略设置为 RemoteSigned，否则 Skype for Business Online 连接器模块无法导入。如果未这样设置，当您试图导入模块时，您将收到以下错误消息：

    Import-Module : 无法加载文件 C:\Program Files\Common Files\Microsoft Lync Server 2013\Modules\LyncOnlineConnector\LyncOnlineConnectorStartup.psm1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 http://go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。

要解决此问题，请以管理员身份启动 Windows PowerShell，然后运行以下命令：

    Set-ExecutionPolicy RemoteSigned

有关执行策略的详细信息，请参阅 [http://go.microsoft.com/fwlink/?LinkID=135170](http://go.microsoft.com/fwlink/?linkid=135170) 处的帮助主题。

## 另请参阅

#### 概念

[诊断和解决 Lync Online 的连接问题](diagnosing-and-resolving-connection-problems-with-skype-for-business-online.md)


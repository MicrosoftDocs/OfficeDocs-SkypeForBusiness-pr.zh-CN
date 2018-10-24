---
title: 迁移模拟设备
TOCTitle: 迁移模拟设备
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49888556
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移模拟设备

 

_**上一次修改主题：** 2012-10-16_

Lync Server 提供对模拟设备的支持。具体地说，支持的模拟设备是模拟音频电话和模拟传真机。您可以将合格的网关配置为支持在您的 Lync Server 环境中使用模拟设备。从 Lync Server 2010 迁移到 Lync Server 2013 之后，您必须同时迁移与模拟设备相关联的联系人对象。使用 Lync Server 命令行管理程序首先检索与 Lync Server 2010 模拟设备相关联的所有联系人对象，然后将这些对象移动到 Lync Server 2013 池。

## 迁移模拟设备

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  验证是否已将所有联系人对象均移动到 Lync Server 2013 池。在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  验证所有联系人对象现在是否均与 Lync Server 2013 池相关联。


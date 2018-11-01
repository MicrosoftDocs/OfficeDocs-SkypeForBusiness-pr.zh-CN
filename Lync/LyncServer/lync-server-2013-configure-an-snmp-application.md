---
title: 配置 SNMP 应用程序
TOCTitle: 配置 SNMP 应用程序
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412972(v=OCS.15)
ms:contentKeyID: 49314191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 SNMP 应用程序

 

_**上一次修改主题：** 2012-10-03_

Lync Server 2013 包含一个标准的 Web 服务接口，可以使用该接口将位置信息服务连接到简单网络管理协议 (SNMP) 应用程序，而这些应用程序使 MAC 地址与端口和交换机信息相匹配。

如果安装了 SNMP 应用程序，但位置信息服务无法在位置数据库中找到匹配项，则位置信息服务会自动使用客户端提供的 MAC 地址查询应用程序。然后，位置信息服务会使用 SNMP 应用程序返回的端口和交换机信息重新查询位置数据库。

有关详细信息，请参阅[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)。

> [!NOTE]  
> 在运行 Windows 8 的计算机上未提供 MAC 地址。



## 配置 SNMP 应用程序 URL

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet 为 SNMP 应用程序配置 URL。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"


---
title: 在 Lync Server 2013 中创建网络站点间策略
TOCTitle: 在 Lync Server 2013 中创建网络站点间策略
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412844(v=OCS.15)
ms:contentKeyID: 49313940
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建网络站点间策略

 

_**上一次修改主题：** 2012-10-19_

“网络站点间策略”定义其间具有直接 WAN 链路的站点间的带宽限制。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中有关以下 cmdlet 的内容：

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

> [!IMPORTANT]
> 仅当两个网络站点之间具有直接交叉链接时，才需要网络站点间策略。


在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。这两个站点需要可应用相应带宽策略配置文件的站点间策略。以下示例将应用 20Mb\_Link 配置文件。

## 创建网络站点间策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略并为两个具有直接交叉链接的站点应用相应的带宽策略配置文件。例如，运行：
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  根据需要重复步骤 2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。


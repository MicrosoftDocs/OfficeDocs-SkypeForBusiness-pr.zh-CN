---
title: 向网络站点添加位置策略
TOCTitle: 向网络站点添加位置策略
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425936(v=OCS.15)
ms:contentKeyID: 49312683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向网络站点添加位置策略

 

_**上一次修改主题：** 2013-02-24_

下面几个示例说明如何将[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)中定义的 **Redmond** 位置策略添加到现有网络站点，以及如何创建使用 **Redmond** 位置策略的新网络站点。

有关使用网络站点的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

## 为现有网络站点分配位置策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet 以修改现有网络站点。
    
    将带 **Redmond** 标记的位置策略分配给名为 **Redmond** 的现有网络站点。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

## 为新的网络站点分配位置策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet 以创建新的网络站点。
    
    在网络区域中创建新的网络站点，并分配带 **Redmond** 标记的位置策略。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"


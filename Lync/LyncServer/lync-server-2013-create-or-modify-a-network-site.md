---
title: Lync Server 2013：创建或修改网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb986f88af11ee2020b760e0a6d65aabed838c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

呼叫许可控制 (CAC)、E9-1 和媒体旁路部署依赖于定义的*网络站点*的配置, 并且与网络区域之间始终关联。 网络站点表示分支机构位置、一组建筑物或校园。 网络站点表示具有相似带宽的子网的集合。

使用以下过程创建或修改网络站点。 例如, 如果已为一个语音功能创建了网络网站, 则不需要创建新的网络网站;其他语音功能将使用这些相同的网站。 但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。 例如，如果已为 E9-1-1 创建了网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。

<div>


> [!NOTE]  
> 无论它们位于何处, 您都可以在适用于每个功能的部署文档中找到与高级语音功能相关的网络站点的特定示例和要求: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中配置 CAC 的网络站点</A></P></LI></UL>



</div>

有关使用网络站点的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>创建网络网站

创建可由呼叫许可控制、E9-1 或媒体旁路使用的网络区域。

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>使用命令行管理程序创建网络站点

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行 New-CsNetworkSite cmdlet 创建网络站点：
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    例如：
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    在此示例中，您创建了一个称为“Chicago”的网络站点，该站点位于“NorthAmerica”网络区域。
    
    <div>
    

    > [!NOTE]  
    > 为了成功运行此命令，NorthAmerica 网络区域必须已经存在。

    
    </div>

3.  要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建网络网站

1.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“站点”**** 导航按钮。

4.  单击“新建”****。

5.  在“新建站点”**** 页上，单击“名称”****，然后键入网络站点的名称。

6.  单击“区域”****，然后单击列表中的某个区域。

7.  或者，单击“带宽策略”****，然后单击列表中的某个带宽策略。
    
    <div>
    

    > [!NOTE]  
    > 只有在站点上部署呼叫允许控制时才需要带宽策略。

    
    </div>

8.  或者，单击“位置策略”****，然后单击列表中的某个位置策略。
    
    <div>
    

    > [!NOTE]  
    > 只有在站点上部署 E9-1-1 时才需要位置策略。

    
    </div>

9.  或者，单击“说明”****，然后键入其他信息以描述此网络站点。

10. 单击“**提交**”。

11. 要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>修改网络网站

修改可由呼叫许可控制、E9-1 或媒体绕过使用的网络区域。

<div>

## <a name="to-modify-a-network-site"></a>修改网络网站

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行 Set-CsNetworkSite cmdlet 修改网络站点：
    
        Set-CsNetworkSite -Identity <string>
    
    例如：
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    在此示例中，称为“Albuquerque”的站点将移动到“NorthAmerica”网络区域。要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。
    
    <div>
    

    > [!NOTE]  
    > 尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。

    
    </div>

3.  要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 修改网络站点

1.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“站点”**** 导航按钮。

4.  在表中，单击要修改的网络站点。

5.  单击“编辑”****，然后单击“显示详细信息...”****。

6.  在“编辑站点”**** 页上，根据需要更改此网络站点的设置的值。

7.  单击“**提交**”。

8.  要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


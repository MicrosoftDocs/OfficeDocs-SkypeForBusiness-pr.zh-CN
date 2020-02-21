---
title: Lync Server 2013：创建网络区域链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af9c2d6b651fd127986d89d521e99745e1af384
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中创建网络区域链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

网络内的区域通过物理 WAN 连接进行链接。*网络区域链接* 在为呼叫允许控制 (CAC) 配置的两个区域之间创建链接，并为这两个区域之间的音频和视频流量设置带宽限制。

有关使用网络区域链接的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。 每个区域链接都受 WAN 带宽的限制，如示例中的 "区域链接带宽信息" 表中所述：在规划文档的 " [Lync Server 2013 中收集对呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)" 一节。

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序创建网络区域链接

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。例如，运行：
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建网络区域链接

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“区域链接”**** 导航按钮。

4.  单击“新建”****。

5.  在“新建区域链接”**** 页上，单击“名称”****，然后键入网络区域链接的名称。

6.  单击 "**网络\#区域 1**"，然后在列表中单击要链接到 "网络区域\#2" 的网络区域。

7.  单击 "**网络\#区域 2**"，然后在列表中单击要链接到 "网络区域\#1" 的网络区域。

8.  也可以选择单击“带宽策略”****，然后选择要应用于网络区域链接的带宽策略配置文件。
    
    <div class=" ">
    

    > [!NOTE]  
    > 仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。

    
    </div>

9.  单击“提交”****。

10. 要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。

</div>

</div>

<span> </span>

</div>

</div>

</div>

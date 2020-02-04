---
title: Lync Server 2013：创建或修改网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-08_

网络站点是在呼叫许可控制（CAC）或增强的9-1-1 部署的每个区域内配置的办公室或位置。 你可以使用 Microsoft Lync Server 2013 控制面板配置网站并将其与区域相关联。 例如，北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。 必须为组织内的每个网站创建 CAC 网络网站，即使该网站没有带宽限制也是如此。 在 Lync Server 控制面板中，您可以创建、修改和删除网络站点。 使用以下过程创建或修改网络网站。 有关删除现有网络网站的详细信息，请参阅[在 Lync Server 2013 中删除现有网络网站](lync-server-2013-deleting-an-existing-network-site.md)。

<div>

## <a name="to-create-a-network-site"></a>创建网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**网站**"。

4.  在 "**网站**" 页面上，单击 "**新建**"。

5.  在 "**新建网站**" 中，在 "**名称**" 字段中键入此网站的名称。
    
    <div>
    

    > [!NOTE]  
    > 网站名称在 Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  在 "**区域**" 下拉列表中，选择要与此网站相关联的网络区域。

7.  可选如果要对此网站的音频或视频呼叫设置带宽限制，请从 "**带宽策略**" 下拉列表中选择具有相应设置的 "带宽策略配置文件"。
    
    <div>
    

    > [!NOTE]  
    > 你可以在 "<STRONG>网络配置</STRONG>" 组的 "<STRONG>策略配置文件</STRONG>" 页面上查看可用带宽策略配置文件的详细信息，或者创建新的带宽策略配置文件。 有关详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中创建或修改带宽策略配置文件</A>。

    
    </div>

8.  可选如果要为此网站提供位置设置，请从 "**位置策略**" 下拉列表中选择一个位置策略。
    
    <div>
    

    > [!NOTE]  
    > 位置策略将特定的增强9-1-1 （E9-1）和客户端位置设置分配给该网站。 你可以从 "<STRONG>网络配置</STRONG>" 组的 "<STRONG>位置策略</STRONG>" 页查看可用位置策略的详细信息，或者创建新的位置策略。 有关详细信息，请参阅<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置策略信息</A>。

    
    </div>

9.  可选在 "**说明**" 字段中键入一个值，以提供有关此网站的详细信息，该信息不能单独以名称表示。

10. 单击“**提交**”。
    
    <div>
    

    > [!NOTE]  
    > 创建新网络网站时，请不要使用<STRONG>关联的子网</STRONG>表。 创建或修改子网时，将子网与网站相关联。 有关详细信息，请参阅<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中创建或修改网络子网</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>修改网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**网站**"。

4.  在 "**网站**" 页面上，单击要修改的网站。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑网站**" 页面上，您可以修改与该网站相关联的说明、区域、带宽策略配置文件和位置策略。 有关详细信息，请参阅本主题前面的 "创建网络网站" 部分。

7.  单击“**提交**”。

不能在此页面上修改**关联的子网**表。 将为参考提供关联子网的列表，以便你在修改网站设置时知道将受到哪些子网的影响。

</div>

<div>

## <a name="to-delete-a-network-site"></a>删除网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**网站**"。

4.  在 "**网站**" 页面上，单击要删除的网站。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个网站。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个网站。 或者，若要选择 "所有网站"，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上，单击 "**删除**"。

6.  单击“**确定**”。
    
    <div>
    

    > [!WARNING]  
    > 如果网络站点与网络子网相关联，则不能将其删除。 如果您尝试删除与子网相关联的网站，您将收到一条错误消息。 若要查看某个网站是否与任何子网相关联，请单击该网站，然后单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>显示详细信息</STRONG>"。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除现有网络网站](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


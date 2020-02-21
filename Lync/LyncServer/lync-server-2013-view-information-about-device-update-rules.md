---
title: Lync Server 2013：查看有关设备更新规则的信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa10335c21a943c90937306a39262e651c392a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>在 Lync Server 2013 中查看有关设备更新规则的信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

查看有关已导入的设备更新规则的详细信息，包括更新适用于的设备的类型、模型和品牌;更新的版本和类型;以及更新的区域设置和池。 信息适用于所有导入的设备更新规则，这些规则是待审批的、已部署的（已批准的）、回调的（已还原）和您决定不使用的（重置）。 从 Lync Server 控制面板或 Windows PowerShell 访问此信息。

<div>


> [!NOTE]  
> 有关如何导入、批准、重置、还原和删除规则的详细信息，请参阅<A href="lync-server-2013-device-update-rules.md">Lync Server 2013 中的设备更新规则中</A>列出的主题。



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板查看设备更新规则

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。 "**设备更新**" 页上列出了导入的规则。

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 查看有关您的所有设备更新规则的详细信息。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>查看所有设备更新规则

  - 以下命令将返回有关配置为在组织中使用的所有设备更新规则的信息：
    
        Get-CsDeviceUpdateRule
    
    该命令将针对每个设备更新规则返回类似以下内容的信息：
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>查看特定 web 服务器上的所有设备更新规则

  - 若要查看特定计算机上的设备更新规则，请使用后跟服务器标识和通配符的筛选器参数（\*）。 例如：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


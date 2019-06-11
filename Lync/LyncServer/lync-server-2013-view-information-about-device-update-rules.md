---
title: 'Lync Server 2013: 查看有关设备更新规则的信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>查看有关 Lync Server 2013 中的设备更新规则的信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

查看有关已导入的设备更新规则的详细信息, 包括更新适用于的设备的类型、模型和品牌;更新的版本和类型;以及更新的区域设置和池。 信息可用于所有导入的设备更新规则, 这些规则包括待审批、已部署 (已批准)、撤回 (已还原) 和您决定不使用的 (重置)。 从 Lync Server "控制面板" 或 Windows PowerShell 中访问此信息。

<div>


> [!NOTE]  
> 有关如何导入、批准、重置、还原和删除规则的详细信息, 请参阅<A href="lync-server-2013-device-update-rules.md">Lync Server 2013 中的设备更新规则中</A>列出的主题。



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 查看设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备更新**" 导航按钮。 "**设备更新**" 页面上列出了导入的规则。

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 查看有关所有设备更新规则的详细信息。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>查看所有设备更新规则

  - 以下命令将返回有关所有设备更新规则的信息, 这些规则已配置为在您的组织中使用:
    
        Get-CsDeviceUpdateRule
    
    该命令将针对每个设备更新规则返回类似于以下内容的信息:
    
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

  - 若要查看特定计算机上的设备更新规则, 请使用筛选器参数, 后跟服务器标识和通配符 (\*)。 例如：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

有关详细信息, 请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


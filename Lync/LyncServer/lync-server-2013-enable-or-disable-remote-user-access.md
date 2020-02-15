---
title: Lync Server 2013：启用或禁用远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c673295f2344d2ca3ca853f76775bbae47a74328
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用远程用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

远程用户是组织内拥有持久 Active Directory 标识的用户。 当远程用户未连接到您的组织的网络时，他们通常使用虚拟专用网络（VPN）从网络外部登录 Lync Server。 远程用户包括在家或在路上工作的员工以及其他远程工作者，如已被授予企业凭据的受信任供应商。 如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 进行连接，并且无需使用 VPN 进行连接，以便与使用 Lync Server 的内部用户进行协作。

要支持远程用户访问，必须启用远程用户访问。启用远程用户访问即为整个组织启用。如果稍后要暂时或永久阻止远程用户访问，可以为组织将其禁用。可以使用本节中的步骤为组织启用或禁用远程用户访问。

<div>


> [!NOTE]  
> 启用远程用户访问仅指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户无法在您的组织中参与即时消息（IM）或会议，除非您还在配置至少一个用于管理远程用户访问的策略。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。 有关为使用远程用户访问配置策略的详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置用于控制远程用户访问的策略</A>。



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>为组织启用或禁用远程用户访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“访问边缘配置”****。

4.  在“访问边缘配置”**** 页上，单击“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑访问边缘配置”**** 中，执行下列操作之一：
    
      - 要为组织启用远程用户访问，请选中“启用远程用户访问”**** 复选框。
    
      - 要为组织禁用远程用户访问，请清除“启用远程用户访问”**** 复选框。

6.  单击“提交”****。

若要使远程用户能够登录到运行 Lync Server 的服务器，您还必须配置至少一个外部访问策略以支持远程用户访问。 有关详细信息，请参阅部署文档中的[配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)和操作文档中的 Lync Server 2013。

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用远程用户访问

可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理远程用户访问。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-remote-user-access"></a>启用远程用户访问

  - 要启用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>禁用远程用户访问

  - 要禁用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


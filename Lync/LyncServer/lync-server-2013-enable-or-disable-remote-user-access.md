---
title: Lync Server 2013：启用或禁用远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用远程用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

远程用户是组织内具有永久 Active Directory 标识的用户。 当远程用户未连接到您的组织网络时, 通过使用虚拟专用网络 (VPN), 从网络外部登录 Lync 服务器。 远程用户包括在家中或在路上和其他远程工作人员 (如受信任的供应商, 他们已授予企业凭据) 工作的员工。 如果为远程用户启用远程用户访问, 受支持的远程用户通过 Internet 进行连接, 并且不必使用 VPN 进行连接, 以便与使用 Lync Server 的内部用户进行协作。

若要支持远程用户访问, 必须启用远程用户访问。 启用远程用户访问时, 将为整个组织启用它。 如果稍后想要临时或永久阻止远程用户访问, 则可以为你的组织禁用它。 使用此部分中的过程可为你的组织启用或禁用远程用户访问。

<div>


> [!NOTE]  
> 启用远程用户访问仅指定运行 Access Edge 服务的服务器支持与远程用户的通信, 但远程用户不能在您的组织中参与即时消息 (IM) 或会议, 除非您还可以在配置管理远程用户访问使用的至少一个策略。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 有关配置使用远程用户访问策略的详细信息, 请参阅<A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置用于控制远程用户访问的策略</A>。



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>为你的组织启用或禁用远程用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。

4.  在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  在 "**编辑访问边缘配置**" 中, 执行下列操作之一:
    
      - 若要为你的组织启用远程用户访问权限, 请选中 "**启用远程用户访问**" 复选框。
    
      - 若要为你的组织禁用远程用户访问权限, 请清除 "**启用远程用户访问**" 复选框。

6.  单击“**提交**”。

若要使远程用户能够登录到运行 Lync Server 的服务器, 还必须至少配置一个外部访问策略以支持远程用户访问。 有关详细信息, 请参阅在部署文档或操作文档中的 "[配置用于控制 Lync Server 2013 中的远程用户访问的策略](lync-server-2013-configure-policies-to-control-remote-user-access.md)"。

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用远程用户访问

可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理远程用户访问。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-remote-user-access"></a>启用远程用户访问

  - 若要启用远程用户访问, 请将**AllowOutsideUsers**属性的值设置为 True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>禁用远程用户访问

  - 若要禁用远程用户访问, 请将**AllowOutsideUsers**属性的值设置为 False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


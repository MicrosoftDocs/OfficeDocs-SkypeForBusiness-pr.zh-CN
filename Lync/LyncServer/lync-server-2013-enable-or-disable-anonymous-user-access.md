---
title: Lync Server 2013：启用或禁用匿名用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用匿名用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

匿名用户是在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户的用户, 但可以邀请他们在本地会议中进行远程参与。 通过允许匿名参与会议, 你可以启用匿名用户 (即仅通过会议或会议密钥验证身份的用户) 来加入会议。 允许匿名参与需要为你的组织启用它。

如果稍后想要临时或永久阻止匿名用户的访问, 则可以为你的组织禁用它。 使用此部分中的过程可为你的组织启用或禁用匿名用户访问权限。

<div>


> [!NOTE]  
> 通过为你的组织启用匿名用户访问, 仅指定运行 Access Edge 服务的服务器支持匿名用户的访问。 匿名用户不能参与您的组织中的任何会议, 除非您还配置了至少一个会议策略并将其应用于一个或多个用户或用户组。 只有分配了会议策略 (配置为支持匿名用户) 的用户才可以邀请匿名用户加入会议。 有关配置会议策略以支持邀请匿名用户的详细信息, 请参阅<A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</A>。



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>为你的组织启用或禁用匿名用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。

4.  在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  在 "**编辑访问边缘配置**" 中, 执行下列操作之一:
    
      - 若要为你的组织启用匿名用户访问, 请选中 "**启用与匿名用户的通信**" 复选框。
    
      - 若要为你的组织禁用匿名用户访问, 请清除 "**启用与匿名用户的通信**" 复选框。

6.  单击“**提交**”。

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用匿名用户访问

你可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 管理匿名用户访问。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-anonymous-user-access"></a>启用匿名用户访问

  - 若要启用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>禁用匿名用户访问

  - 若要禁用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


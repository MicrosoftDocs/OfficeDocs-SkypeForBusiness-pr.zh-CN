---
title: Lync Server 2013：配置策略以控制 XMPP 联盟用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

本文档是预备文档，可能随时更改。 空白主题均以占位符的形式包含在内。

当您为支持可扩展消息和状态协议（XMPP）联盟伙伴的策略配置策略时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议（SIP）的用户（IM）服务提供商（例如，Windows Live）或 SIP 联盟域。 为你希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置**XMPP 联盟合作伙伴**。 XMPP 联盟伙伴策略仅在单个作用域内可用，但它不是作为全局策略定义的作为全局策略。 若要为 XMPP 联合合作伙伴定义全局、网站或用户策略，请通过首先创建和配置所需作用域的外部访问策略来配置策略范围。 有关可针对外部访问和联盟配置的策略类型的详细信息，请参阅在操作文档中[管理 Lync Server 2013 的联合身份验证和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。

<div>


> [!NOTE]  
> 所有<STRONG>联盟和外部访问</STRONG>策略均通过带内配置应用。 在登录期间，应用于用户、属于网站或全局范围内的策略将传递给客户端。 你可以配置策略来控制 XMPP 联盟合作伙伴的访问权限，即使你没有为你的组织启用 XMPP 联盟也是如此。 但是，仅当为你的组织部署、启用和配置了 XMPP 合作伙伴联合身份验证时，你配置的策略才会生效。 有关部署和配置 XMPP 合作伙伴联盟的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 中的 "配置 SIP 联合"、"XMPP 联盟" 和 "公共即时消息</A>"。 此外，如果在外部访问策略中指定了用于控制 XMPP 联盟伙伴的用户策略，该策略将仅应用于已启用 Lync Server 2013 的用户，并且配置为使用该策略。



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>编辑 XMPP 联盟合作伙伴的全局策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 页面上，对全局策略执行以下操作：

5.  单击 "全局策略"，单击 "**编辑**"，然后单击 "显示详细信息"。

6.  提供全局策略的说明（可选）。

7.  选择 "**启用与联盟用户的通信**"。

8.  选择 "**启用与 XMPP 联盟用户的通信**"。

9.  单击 "**提交**" 以将更改保存到全局策略。

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>为 XMPP 联盟合作伙伴创建网站或用户策略

1.  单击 "**新建**"，然后单击 "**网站策略**" 或 "**用户策略**"。 在 "**选择网站**" 中，从列表中单击相应的网站，然后单击 **"确定"**。

2.  提供网站策略的说明（可选）。

3.  在 "网站或用户策略" 中，选择 "**启用与联盟用户的通信**"。

4.  选择 "**启用与 XMPP 联盟用户的通信**"。

5.  单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>编辑 XMPP 联盟合作伙伴的现有策略

1.  若要更改现有策略，请在列表中选择相应的策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

2.  更改或更新策略的说明（可选）。

3.  选择或取消选择 "**启用与联盟用户的通信**"。

4.  选择或取消选择 "**启用与 XMPP 联盟用户的通信**"。

5.  单击 "**提交**" 以保存对策略所做的更改。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 编辑 XMPP 联盟合作伙伴的现有策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    将联盟用户访问的全局策略设置为 True （enabled），并将 XMPP 域访问设置为 True （已启用）的示例命令：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>使用 Windows PowerShell 为 XMPP 联盟合作伙伴创建网站或用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    一个示例命令，将为 Redmond 用户访问启用和 XMPP 域访问启用的 "Redmond" 网站设置网站策略。
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 删除 XMPP 联盟合作伙伴的现有策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    将删除用户策略的示例命令：
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  将全局策略重置为默认值的示例命令：
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授权-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


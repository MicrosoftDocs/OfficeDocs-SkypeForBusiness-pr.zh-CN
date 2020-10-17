---
title: Lync Server 2013：配置策略以控制 XMPP 联盟用户访问
description: Lync Server 2013：配置策略以控制 XMPP 联盟用户访问。
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
ms.openlocfilehash: cdb2b7a3da6c00aa7725ecbb69856756f229ed97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542778"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

这是初步文档，可能会发生变更。 空白主题作为占位符包含在内。

当您配置用以支持可扩展消息传递和状态协议 (XMPP) 联盟合作伙伴的策略时，这些策略适用于 XMPP 联盟域用户，但不适用于会话初始协议 (SIP) 即时消息 (IM) 服务提供商（例如，Windows Live）用户或 SIP 联盟域用户。 您为每个您希望允许您的用户在其中添加联系人并与其通信的 XMPP 联盟域配置一个 **XMPP 联盟伙伴**。 XMPP 联盟伙伴策略只在单一范围内可用，尽管它未定义为全局策略，却充当全局策略。 要为 XMPP 联盟伙伴定义全局、站点或用户策略，需要通过首先为您所需的范围创建和配置外部访问策略来配置策略范围。 有关可为外部访问和联盟配置的策略类型的详细信息，请参阅操作文档中的 [管理对 Lync Server 2013 的联合身份验证和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) 。

<div>


> [!NOTE]  
> 所有<STRONG>联盟和外部访问</STRONG>策略都是通过带内设置应用的。 登录期间，应用于用户、属于某个站点或在全局范围内的策略传达给客户端。 您可以配置策略来控制 XMPP 联盟伙伴访问，即使您还没有为您的组织启用 XMPP 联盟也是如此。 但是，您配置的策略只在您为您的组织部署、启用和配置了 XMPP 合作伙伴联盟后才生效。 有关部署和配置 XMPP 合作伙伴联盟的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 中配置 SIP 联合、XMPP 联盟和公共即时消息</A> 。 此外，如果您在外部访问策略中指定用户策略以控制 XMPP 联盟伙伴，则该策略仅适用于启用了 Lync Server 2013 的用户并配置为使用该策略。



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>编辑 XMPP 联盟伙伴的全局策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“外部访问策略”****。

4.  在“外部访问策略”**** 页面上，对全局策略执行以下操作：

5.  单击全局策略，单击“编辑”****，然后单击“显示详细信息”。

6.  提供全局策略说明（可选）。

7.  选择“启用与联盟用户的通信”****。

8.  选择“启用与 XMPP 联盟用户的通信”****。

9.  单击“提交”**** 保存对全局策略所做的更改。

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>为 XMPP 联盟伙伴创建站点或用户策略

1.  单击“新建”****，然后单击“站点策略”**** 或“用户策略”****。在“选择站点”**** 中，从列表中单击适当的站点，然后单击“确定”****。

2.  提供站点策略说明（可选）。

3.  在站点或用户策略中，选择“启用与联盟用户的通信”****。

4.  选择“启用与 XMPP 联盟用户的通信”****。

5.  单击“提交”**** 保存对站点或用户策略所做的更改。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>编辑 XMPP 联盟伙伴的现有策略

1.  若要更改现有策略，请在列表中选择相应策略，单击“编辑”****，然后单击“显示详细信息”****。

2.  更改或更新策略说明（可选）。

3.  选择或取消选择“启用与联盟用户的通信”****。

4.  选择或取消选择“启用与 XMPP 联盟用户的通信”****。

5.  单击“提交”**** 保存对策略所做的更改。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 编辑 XMPP 联盟伙伴的现有策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    将联盟用户访问的全局策略设置为 True (启用) 并将域访问权限设置为 True (启用) 的命令示例：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>使用 Windows PowerShell 为 XMPP 联盟伙伴创建网站或用户策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    设置 Redmond 站点的站点策略以启用联盟用户访问和 XMPP 域访问的示例命令：
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 删除 XMPP 联盟伙伴的现有策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    删除用户策略的示例命令：
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  将全局策略重置为默认值的示例命令：
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新 Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


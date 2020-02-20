---
title: Lync Server 2013：配置策略以控制联盟用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2395efc4351f7ec91e489eaae3dd57a973e77e86
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置用于控制联合用户访问的策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。 您可以配置一个或多个外部用户访问策略，以控制联盟域的用户是否可以与 Lync Server 2013 用户进行协作。 要控制联盟用户访问，可以在全局、站点和用户级别配置策略。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。

<div>


> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制联盟用户访问的策略。 但是，只有为组织启用联盟后，配置的策略才会生效。 有关启用联合的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A>。 此外，如果您指定了用于控制联合用户访问的用户策略，则该策略仅适用于启用了 Lync Server 2013 的用户并配置为使用该策略。



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>配置策略以支持联盟域用户访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“外部访问策略”****。

4.  在“外部访问策略”**** 页上，执行下列操作之一：
    
      - 要将全局策略配置为支持联盟用户访问，请单击该全局策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
      - 要创建新的站点策略，请单击“新建”****，然后单击“站点策略”****。在“选择站点”**** 中，单击列表中相应的站点，然后单击“确定”****。
    
      - 要创建新的用户策略，请单击“新建”****，然后单击“用户策略”****。在“新建外部访问策略”**** 的“名称”**** 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableFederatedUsers** 代表启用联盟域用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”****，然后单击“显示详细信息”****。

5.  （可选）如果要添加或编辑说明，请在“说明”**** 中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用联盟用户访问，请选中“启用与联盟用户的通信”**** 复选框。
    
      - 要为策略禁用联盟用户访问，请清除“启用与联盟用户的通信”**** 复选框。

7.  单击“提交”****。

要启用联盟用户访问，还必须在组织中启用对联盟的支持。 有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是一个用户策略，则还必须将此策略应用于希望其可以与联盟用户进行协作的用户。 有关详细信息，请参阅[在 Lync Server 2013 中向启用 Lync 的用户分配外部用户访问策略](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 配置现有策略以支持由联盟域的用户进行访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    一个示例命令，该命令可将针对联盟用户访问、XMPP 域访问、远程用户访问、公共提供程序访问的全局策略设置为已启用，并允许对支持音频和视频的公共提供程序使用这些音频和视频：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > "EnablePublicCloudAudioVideoAccess" 参数在 Lync Server 控制面板中没有对应的选择

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 创建新策略以支持由联盟域的用户进行访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序中键入以下内容：
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    创建新站点策略的示例：
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 删除或重置策略以支持由联盟域的用户进行访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  在 Lync Server 命令行管理程序中键入以下命令
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    重置全局策略的示例（只能删除全局策略的设置，而无法删除全局策略本身）：
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    若要删除站点策略，请键入：
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    删除站点策略 Redmond。 若要删除名为 UserEAPPolicy 的用户策略，请键入：
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
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


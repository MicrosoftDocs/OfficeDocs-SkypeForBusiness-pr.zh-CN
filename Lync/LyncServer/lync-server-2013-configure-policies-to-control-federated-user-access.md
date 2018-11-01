---
title: Lync Server 2013：配置策略以控制联盟用户访问
TOCTitle: 配置策略以控制联盟用户访问
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398359(v=OCS.15)
ms:contentKeyID: 49312869
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置策略以控制联盟用户访问

 

_**上一次修改主题：** 2014-02-05_

如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。可以配置一个或多个外部用户访问策略来控制联盟域用户能否与 Lync Server 2013 用户进行协作。要控制联盟用户访问，可以在全局、站点和用户级别配置策略。 在一个策略级别应用的 Lync Server 策略设置可能会覆盖在另一个策略级别应用的设置。Lync Server 策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制联盟用户访问的策略。但是，只有为组织启用联盟后，配置的策略才会生效。有关启用联盟的详细信息，请参阅部署文档或操作文档中的<a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a>。此外，如果指定了某个用户策略用来控制联盟用户访问，则该策略仅应用于已启用 Lync Server 2013 并配置为使用该策略的用户。



## 配置策略以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”页上，执行下列操作之一：
    
      - 要将全局策略配置为支持联盟用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。
    
      - 要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。
    
      - 要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableFederatedUsers** 代表启用联盟域用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

5.  （可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。
    
      - 要为策略禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。

7.  单击“提交”。

要启用联盟用户访问，还必须在组织中启用对联盟的支持。有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是一个用户策略，则还必须将此策略应用于希望其可以与联盟用户进行协作的用户。有关详细信息，请参阅 [在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

## 使用 Windows PowerShell 将现有策略配置为支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在 Lync Server 命令行管理程序中键入：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    一个示例命令，该命令可将针对联盟用户访问、XMPP 域访问、远程用户访问、公共提供程序访问的全局策略设置为已启用，并允许对支持音频和视频的公共提供程序使用这些音频和视频：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    > [!TIP]
    > 参数“EnablePublicCloudAudioVideoAccess”在 Lync Server 控制面板中没有对应的选项


## 使用 Windows PowerShell 创建新策略以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在 Lync Server 命令行管理程序中键入：
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    创建新站点策略的示例：
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## 使用 Windows PowerShell 删除或重置策略以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  在 Lync Server 命令行管理程序中键入：
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    重置全局策略的示例（只能删除全局策略的设置，而无法删除全局策略本身）：
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    若要删除站点策略，请键入：
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    删除站点策略 Redmond。若要删除名为 UserEAPPolicy 的用户策略，请键入：
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## 另请参阅

#### 任务

[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)


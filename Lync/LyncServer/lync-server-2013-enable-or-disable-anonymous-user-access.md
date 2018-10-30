---
title: Lync Server 2013：启用或禁用匿名用户访问
TOCTitle: 启用或禁用匿名用户访问
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49314695
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用或禁用匿名用户访问

 

_**上一次修改主题：** 2013-02-23_

匿名用户是指在组织的 Active Directory 域服务 中或支持的联盟域中没有用户帐户的用户，但可以受邀远程参加内部会议。通过允许匿名参加会议，匿名用户（即仅通过会议密钥验证其身份的用户）可以加入会议。允许匿名参与需要为组织启用匿名参与。

如果随后要暂时或永久阻止匿名用户访问，则可为组织禁用它。使用本节中的过程为组织启用或禁用匿名用户访问。

> [!NOTE]  
> 仅为组织启用匿名用户访问，将指定运行访问边缘服务的服务器支持匿名用户访问。在至少配置一个会议策略并将其应用于一个或多个用户或用户组之前，匿名用户将无法参加组织中的任何会议。只有分配了配置为支持匿名用户的会议策略的那些用户才能邀请匿名用户参加会议。有关配置会议策略以支持邀请匿名用户的详细信息，请参阅 <a href="lync-server-2013-conferencing-policies.md">会议策略</a>。



## 为组织启用或禁用匿名用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用匿名用户访问，请选中“启用与匿名用户的通信”复选框。
    
      - 要为组织禁用匿名用户访问，请清除“启用与匿名用户的通信”复选框。

6.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 启用或禁用匿名用户访问

还可以通过使用 Windows PowerShell和 **Set-CsAccessEdgeConfiguration** cmdlet 管理匿名用户访问。可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用匿名用户访问

  - 要启用匿名用户访问，请将 **AllowAnonymousUsers** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## 禁用匿名用户访问

  - 要禁用匿名用户访问，请将 **AllowAnonymousUsers** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

## 另请参阅

#### 概念

[在 Lync Server 2013 中会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)


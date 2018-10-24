---
title: Lync Server 2013：将外部用户访问策略分配到启用 Lync 的用户
TOCTitle: 将外部用户访问策略分配到启用 Lync 的用户
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398551(v=OCS.15)
ms:contentKeyID: 49313241
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户

 

_**上一次修改主题：** 2013-02-22_

如果已为某个用户启用 Lync Server，则可通过将相应的策略应用于特定用户，在 Lync Server 控制面板中配置 SIP 联盟、XMPP 联盟、远程用户访问和公共即时消息 (IM) 连接。例如，如果您已创建支持远程用户访问的策略，则必须将该策略应用于此用户，然后此用户才能从一个远程位置连接到 Lync Server，并从该远程位置与内部用户进行协作。

> [!NOTE]  
> 要支持外部用户访问，必须启用对要支持的每种外部用户访问类型的支持，并配置相应的策略及其他选项以控制其使用。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a>或操作文档中的 <a href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理对 Lync Server 2013 的联盟和外部访问</a>。



使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。

## 将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 Lync Server 用户”中的“外部访问策略”下，选择要应用的用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置将应用默认服务器或全局策略设置。
    


## 使用 Windows PowerShell cmdlet 分配每用户外部访问策略

可以使用 Windows PowerShell 和 Grant-CsExternalAccessPolicy cmdlet 分配每用户外部访问策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序 或从Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 将每用户外部访问策略分配到单个用户

  - 此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

## 将每用户外部访问策略分配到多个用户

  - 此命令向在 Active Directory 的 UnitedStates OU 中拥有帐户的所有用户分配每用户外部访问策略 USAExternalAccessPolicy。有关此命令中使用的 OU 参数的详细信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

## 取消分配每用户外部访问策略

  - 此命令取消分配之前为 Ken Myer 分配的任何每用户外部访问策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅 [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。


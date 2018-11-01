---
title: 将存档策略应用于用户
TOCTitle: 将存档策略应用于用户
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521004(v=OCS.15)
ms:contentKeyID: 49313035
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将存档策略应用于用户

 

_**上一次修改主题：** 2013-02-23_

如果已为用户启用 Lync Server 2013，并且已为驻留在 Lync Server 2013 上的用户创建了一个或多个用户存档策略，则可以通过为特定用户或用户组应用相应的策略来实现对其的存档支持。例如，如果创建支持内部通信存档的策略，则可以将其应用于至少一个用户或用户组以支持该用户的 Lync Server 2013 通信的存档。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上且其邮箱使用就地保留的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
> 您应在存档配置中指定所有适当的选项，然后再启用存档。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">在 Lync Server 2013 中管理组织、站点和池的存档配置选项</a>。



使用本主题中的过程将以前创建的存档用户策略应用于一个或多个用户帐户或用户组。

## 将存档用户策略应用于用户帐户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 Lync Server 用户”中的“存档策略”下，选择要应用的存档用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置将应用默认服务器安装设置。服务器将自动应用这些设置。
    


6.  单击“提交”。

## 使用 Lync Server 命令行管理程序 Cmdlet 分配每用户存档策略

每用户存档策略还可使用 Lync ServerWindows PowerShell 和 **Grant-CsArchivingPolicy** cmdlet 进行分配。您可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 向单个用户分配每用户存档策略

  - 以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## 向多个用户分配每用户存档策略

  - 此命令向帐户驻留在注册器池 atl-cs-001.litwareinc.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。有关此命令中使用的 Filter 参数的详细信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 文档。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## 取消分配每用户存档策略

  - 以下命令取消之前已分配给 Ken Myer 的所有每用户存档策略的分配。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅 [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 文档。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[分配每用户策略](lync-server-2013-assigning-per-user-policies.md)


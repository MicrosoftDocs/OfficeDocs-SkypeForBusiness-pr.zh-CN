---
title: 更改存档策略以启用或禁用组织、站点或用户的内部或外部通信的存档
TOCTitle: 更改存档策略以启用或禁用组织、站点或用户的内部或外部通信的存档
ms:assetid: b85dc3fb-8ebd-4e3c-ac90-fc79270ac867
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182576(v=OCS.15)
ms:contentKeyID: 49314057
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 更改存档策略以启用或禁用组织、站点或用户的内部或外部通信的存档

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 中，可以使用某些策略来针对驻留在 Lync Server 2013 上的用户启用和禁用内部通信和外部通信的存档。这包括以下存档策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 您可以创建并用来指定如何针对特定站点或用户实施存档的可选站点级别和用户级别策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。在 Lync Server 2013 控制面板中，可以使用“存档和监控”组的“存档策略”页来管理全局级、站点级和用户级的策略。如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略优先于 Lync Server 2013 存档策略。

有关策略的实现方式的详细信息（包括策略的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，则 Exchange 策略控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
在启用存档之前，应在存档配置中指定所有适当选项。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">在 Lync Server 2013 中管理组织、站点和池的存档配置选项</a>。



## 更改存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。

4.  在策略列表中，执行下列操作之一：
    
      - 若要更改整个部署的策略，请单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
      - 若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“编辑”，然后单击“显示详细信息”。
    
      - 若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑存档策略”页中，执行下列操作：
    
      - 若要为策略启用或禁用内部存档，请选中或清除“存档内部通信”复选框。
    
      - 若要为策略启用或禁用外部存档，请选中或清除“存档外部通信”复选框。

6.  单击“提交”。
    
    > [!IMPORTANT]  
	> 用户策略的设置仅适用于要应用该策略的特定用户和用户组。有关详细信息，请参阅<a href="lync-server-2013-applying-an-archiving-policy-to-users.md">将存档策略应用于用户</a>


## 使用 Lync Server PowerShell Cmdlet 启用和禁用存档

也可以使用 **Set-CsArchivingPolicy** cmdlet 启用和禁用存档（适用于内部和外部通信会话）。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用内部通信会话的存档

  - 要启用内部通信会话的存档，请将 **ArchiveInternal** 属性的值设置为 True ($True)。例如：
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

## 启用外部通信会话的存档

  - 要启用外部通信会话的存档，请将 **Archiveexternal** 属性的值设置为 True ($True)。例如：
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

## 同时启用内部和外部通信会话的存档

  - 要同时启用内部和外部通信会话的存档，请将 **ArchiveInternal** 和 **ArchiveExternal** 属性的值均设置为 True：
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

## 禁用存档

  - 要一起禁用存档，请将 **ArchiveInternal** 和 **ArchiveExternal** 属性的值均设置为 False ($False)。例如：
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

有关详细信息，请参阅 [Set-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)


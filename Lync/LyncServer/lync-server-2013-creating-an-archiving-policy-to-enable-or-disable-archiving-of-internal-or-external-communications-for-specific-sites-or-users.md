---
title: 创建存档策略以启用或禁用特定站点或用户的内部或外部通信的存档
TOCTitle: 创建存档策略以启用或禁用特定站点或用户的内部或外部通信的存档
ms:assetid: 5864793a-ba72-470c-bb5b-9fb41e968896
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398385(v=OCS.15)
ms:contentKeyID: 49312925
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建存档策略以启用或禁用特定站点或用户的内部或外部通信的存档

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 中，可使用策略为驻留在 Lync Server 2013 上的用户启用或禁用对内部通信和外部通信的存档。这包括以下存档策略：

  - 在部署 Lync Server 2013 时默认创建的全局策略。

  - 可创建并用于指定为特定站点或用户实现存档的方式的可选站点级和用户级策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。在 Lync Server 2013 控制面板中，可以使用“存档和监控”组的“存档策略”页来管理全局级、站点级和用户级的策略。如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略将优先于 Lync Server 2013 存档策略。

有关策略如何实现的详细信息（包括策略的层次结构），请参见规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要控制存档的实现，您必须在存档配置中指定选项，例如，是否存档 IM 或会议、关键模式的用法和清除选项。默认情况下，在全局存档配置或任意站点或池存档配置中未启用任何选项。您应在存档配置中指定所有适当的选项，然后在存档策略中为内部或外部通信启用存档。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">在 Lync Server 2013 中管理组织、站点和池的存档配置选项</a>。<br />
如果为部署启用 Microsoft Exchange 集成，则 Exchange 策略可控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。



## 创建站点或用户的存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。

4.  单击“新建”，然后执行以下操作之一：
    
      - 若要创建站点级别的存档策略，请单击“站点策略”，然后在“选择站点”中，单击要应用该策略的站点。
    
      - 若要创建用户级别的存档策略，请单击“用户策略”。

5.  在“新建存档策略”中，执行下列操作：
    
      - 在“名称”中，指定新策略的名称（例如，externalContoso）。
    
      - 在“说明”中，提供有关该策略内容的详细信息（例如，Contoso 的外部用户存档策略）。
    
      - 要控制内部用户通信的存档，请选中或清除“存档内部通信”复选框。
    
      - 要控制外部用户通信的存档，请选中或清除“存档外部通信”复选框。

6.  单击“提交”。
    
    > [!IMPORTANT]
    > 用户策略的设置仅应用于您向其应用该策略的特定用户和用户组。有关详细信息，请参阅<a href="lync-server-2013-applying-an-archiving-policy-to-users.md">将存档策略应用于用户</a>


## 使用 Lync Server 命令行管理程序 cmdlet 创建存档策略

还可以使用 Windows PowerShell 和 **Remove-CsArchivingPolicy** cmdlet 创建存档策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 在站点范围创建新的存档策略

  - 此命令可为 Redmond 站点创建新的存档策略：
    
        New-CsArchivingPolicy -Identity "site:Redmond"

## 在每用户范围创建新的存档策略

  - 若要在每用户范围创建新的存档策略，只需在创建策略时指定唯一标识即可：
    
        New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"

## 创建允许对内部通信会话进行存档的新存档策略

  - 由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新策略将对其所有属性使用默认值。若要创建使用其他属性值的策略，只需包括适当的参数和参数值。例如，若要创建允许对内部即时消息会话进行存档的存档策略，请使用与以下内容类似的命令：
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True

## 创建允许对内部和外部通信会话进行存档的新存档策略

  - 可通过包含多个参数来修改多个属性值。例如，此命令将配置新策略以便对内部和外部即时消息会话进行存档：
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True

有关详细信息，请参阅 [New-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)


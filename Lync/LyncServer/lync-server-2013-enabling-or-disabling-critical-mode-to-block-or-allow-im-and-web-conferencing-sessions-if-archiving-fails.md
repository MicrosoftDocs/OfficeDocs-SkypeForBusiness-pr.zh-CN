---
title: 'Lync Server 2013: 启用或禁用关键模式, 以阻止或允许 IM 和网络会议会话 (如果存档失败)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>启用或禁用 Lync Server 2013 中的关键模式, 以阻止或允许 IM 和网络会议会话 (如果存档失败)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

在 Lync Server 2013 "控制面板" 中, 使用存档配置启用和禁用关键模式。 这包括以下存档配置:

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可创建和使用的可选网站级和池级配置, 用于指定如何为特定网站或池实现存档。

你在部署存档时开始设置存档配置, 但你可以在部署后更改、添加和删除配置。 有关如何实现存档配置的详细信息, 包括你可以指定哪些选项和存档配置的层次结构, 请参阅规划文档、部署中的[Lync Server 2013 中的存档工作原理](lync-server-2013-how-archiving-works.md)文档或操作文档。

<div>


> [!NOTE]  
> 若要使用存档, 必须配置存档策略以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的用户启用存档。 默认情况下, 不会为内部或外部通信启用存档。 在任何策略中启用存档之前, 应为你的部署指定相应的存档配置, 并根据需要为特定的网站和池指定相应的存档配置, 如本节所述。 有关启用存档的详细信息, 请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。<BR>如果你在部署要使用 Exchange Server 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档后确定你想要使用 Exchange Server 集成, 并且你的所有用户都在 Exchange 2013 服务器上托管, 则应删除 SQL Server 数据库配置你的拓扑。 您必须使用拓扑生成器执行此操作。 有关详细信息, 请参阅在操作文档中<A href="lync-server-2013-changing-archiving-database-options.md">更改 Lync Server 2013 中的存档数据库选项</A>。



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>启用或禁用阻止即时消息和网络会议会话 (如果存档失败)

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。

4.  单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：

5.  要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。

6.  单击“**提交**”。

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用和禁用关键模式

你可以使用**CsArchivingConfiguration** cmdlet 启用或禁用关键模式。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-critical-mode"></a>启用关键模式

  - 若要启用关键模式, 请将 BlockOnArchiveFailure 属性的值设置为 True ($True)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>禁用关键模式

  - 若要禁用关键模式, 请将 BlockOnArchiveFailure 属性的值设置为 False ($False)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

有关详细信息, 请参阅[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中更改存档数据库选项](lync-server-2013-changing-archiving-database-options.md)  


[在 Lync Server 2013 中存档的工作方式](lync-server-2013-how-archiving-works.md)  


[管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


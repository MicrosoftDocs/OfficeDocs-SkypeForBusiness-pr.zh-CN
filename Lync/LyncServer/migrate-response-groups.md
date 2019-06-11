---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>迁移响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-09-23_

将用户移动到 Lync Server 2013 池后, 您可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Lync Server 2013 池。 迁移旧版响应组后, 对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序处理。 不再通过旧版池处理对响应组的调用。

<div>


> [!NOTE]  
> 虽然你可以在将所有用户移到 Lync Server 2013 池之前迁移响应组, 但我们建议你先移动所有用户。 特别是, 响应组代理的用户在移动到 Lync Server 2013 池之前不具有新功能的完整功能。



</div>

在迁移响应组之前, 必须已部署包含响应组应用程序的 Lync Server 2013 池。 部署企业语音时, 将默认安装并激活 "响应组" 应用程序。 你可以通过运行**CsService-ApplicationServer** cmdlet 来确保响应组应用程序已安装。

<div>


> [!NOTE]  
> 在迁移旧版响应组之前, 您可以在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组。



</div>

若要将响应组从旧版池迁移到 Lync Server 2013, 请运行**CsRgsConfiguration** cmdlet。

<div>


> [!IMPORTANT]  
> 响应组迁移 cmdlet 移动整个池的响应组配置。 您不能选择要迁移的特定组、队列或工作流。



</div>

迁移响应组后, 你需要使用 Lync Server 控制面板或 Lync Server Management Shell cmdlet 验证是否已成功移动所有代理组、队列和工作流。

迁移响应组时, 不会删除 Lync Server 2010 响应组。 如果你在迁移后通过使用 Lync Server 控制面板或 Lync Server 命令行管理程序管理响应组, 你可以同时看到 Lync Server 2010 响应组和 Lync Server 2013 响应组。 应仅将更新应用于 Lync Server 2013 响应组。 Lync Server 2010 响应组仅为回滚而保留。

<div>


> [!WARNING]  
> 完成迁移并创建新的响应组后, Lync Server 控制面板和 Lync Server 命令行管理程序将显示每个响应组的 Lync Server 2010 和 Lync Server 2013 版本。 请勿使用 Lync Server 控制面板或 Lync Server 命令行管理程序删除 Lync Server 2010 响应组。 如果确实删除了一个, 则迁移期间创建的相应响应组将停止工作。 当您解除 Lync Server 2010 池时, 将删除 Lync Server 2010 响应组。



</div>

<div>


> [!IMPORTANT]  
> 我们建议您不要从以前的部署中删除任何数据, 直到解除池。 此外, 我们强烈建议您在迁移后立即导出响应组。 如果 Lync Server 2010 响应组应被删除, 则可以从备份还原响应组, 以使 Lync Server 2013 响应组再次运行。



</div>

Lync Server 2013 引入了名为 "**工作流类型**" 的新响应组功能。 **工作流类型**可以是**托管**或**非托管**。 将使用**工作流类型**设置为**非托管**并使用空管理器列表迁移所有响应组。

当你运行**CsRgsConfiguration** cmdlet 时, 代理组、队列、工作流和音频文件将保留在旧版池中, 以便进行回退。 但是, 如果确实需要回退到旧版池, 则需要运行**CsApplicationEndpoint** cmdlet 以将联系人对象移回旧版池。

用于迁移响应组配置的以下过程假定你的旧池和 Lync Server 2013 池之间具有一对一关系。 如果你计划在迁移和部署期间合并或拆分池, 你需要规划哪些旧式池映射到哪些 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1.  使用属于 RTCUniversalServerAdmins 组的成员的帐户登录到计算机, 或具有等效的管理员权利和权限。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  运行：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  将响应组和代理迁移到 Lync Server 2013 池后, 代理用于登录和注销的 URL 是 Lync Server 2013 URL, 可从 "**工具**" 菜单中访问。 提醒代理将任何引用 (如书签) 更新到新 URL。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 验证响应组迁移

1.  使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航窗格中, 单击 "**响应组**"。

4.  在 "**工作流**" 选项卡上, 验证您的 Lync Server 2010 环境中的所有工作流是否都包含在列表中。

5.  单击 "**队列**" 选项卡, 然后验证您的 Lync Server 2010 环境中的所有队列是否都包含在列表中。

6.  单击 "**组**" 选项卡, 然后验证您的 Lync Server 2010 环境中的所有代理组是否都包含在列表中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序验证响应组迁移

1.  使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。
    
    有关以下 cmdlet 的详细信息, 请运行:
    
        Get-Help <cmdlet name> -Detailed

3.  运行：
    
        Get-CsRgsAgentGroup

4.  验证您的 Lync Server 2010 环境中的所有代理组是否都包含在列表中。

5.  运行：
    
        Get-CsRgsQueue

6.  验证您的 Lync Server 2010 环境中的所有队列是否都包含在列表中。

7.  运行：
    
        Get-CsRgsWorkflow

8.  验证您的 Lync Server 2010 环境中的所有工作流是否都包含在列表中。

</div>

</div>

<span> </span>

</div>

</div>

</div>


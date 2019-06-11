---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>迁移响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

将用户移动到 Lync Server 2013 池后, 您可以迁移响应组。 迁移响应组包括复制代理组、队列、工作流和音频文件, 以及将响应组联系人对象从旧部署移动到 Lync Server 2013 池。 迁移旧版响应组后, 对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序处理。 不再通过旧版池处理对响应组的调用。

<div>


> [!NOTE]  
> 虽然你可以在将所有用户移到 Lync Server 2013 池之前迁移响应组, 但我们建议你先移动所有用户。 特别是, 响应组代理的用户在移动到 Lync Server 2013 池之前不具有新功能的完整功能。



</div>

在迁移响应组之前, 必须已部署包含响应组应用程序的 Lync Server 2013 池。 部署企业语音时, 将默认安装并激活 "响应组" 应用程序。 你可以通过运行**CsService-ApplicationServer** cmdlet 来确保响应组应用程序已安装。

<div>


> [!NOTE]  
> 在迁移旧版响应组之前, 您可以在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组。



</div>

若要将响应组从旧版池迁移到 Lync Server 2013, 请运行**CsRgsConfiguration** cmdlet。 必须首先安装 Windows Management Instrumentation (WMI) 向后兼容接口程序包, 然后才能运行**CsRgsConfiguration**。 通过运行 OCSWMIBC 安装此应用程序。 你可以在安装媒体上的 "设置" 文件夹中找到 OCSWMIBC。

<div>


> [!IMPORTANT]  
> 响应组迁移 cmdlet 移动整个池的响应组配置。 您不能选择要迁移的特定组、队列或工作流。



</div>

迁移响应组后, 你需要更新正式代理用于登录和注销其响应组的 URL, 并使用 Lync Server 控制面板或 Lync Server Management Shell cmdlet 验证是否已移动所有代理组、队列和工作流顺利.

<div>


> [!WARNING]  
> 当您迁移响应组时, 不会删除 Office 通信服务器 2007 R2 响应组。 不要删除 Office 通信服务器 2007 R2 响应组。 如果您删除了 Office 通信服务器 2007 R2 响应组, 则 Lync Server 2013 中的响应组将停止工作。



</div>

<div>


> [!IMPORTANT]  
> 我们建议您不要从以前的部署中删除任何数据, 直到解除池。 此外, 我们强烈建议您在迁移后立即导出响应组。 如果删除了 Office 通信服务器 2007 R2 响应组, 则可以从备份还原响应组, 以使 Lync Server 2013 响应组再次运行。



</div>

当你运行**CsRgsConfiguration** cmdlet 时, 代理组、队列、工作流和音频文件将保留在旧版池中, 以便进行回退。 但是, 如果确实需要回退到旧版池, 则需要运行**CsApplicationEndpoint** cmdlet 以将联系人对象移回旧版池。

<div>


> [!IMPORTANT]  
> 我们建议你不要从旧池中删除任何响应组数据, 直到停止池。



</div>

迁移响应组配置后遵循的过程假定你的旧池和 Lync Server 2013 池之间有一对一关系。 如果你计划在迁移和部署期间合并或拆分池, 你需要规划哪些旧式池映射到哪些 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1.  在安装媒体的 "设置" 文件夹中找到 OCSWMIBC, 然后进行安装。

2.  使用属于 RTCUniversalServerAdmins 组的成员的帐户登录到计算机, 或具有等效的管理员权利和权限。

3.  打开 Lync Server 命令行管理程序。

4.  在命令行中键入：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果你在 Office 通信服务器 2007 R2 环境中部署了 Microsoft Office Communicator 2007 R2 的 "响应组" 选项卡, 请删除 Office Communicator 2007 R2 选项卡 .xml 文件中的选项卡。
    
    <div>
    

    > [!NOTE]  
    > 正式代理在接收呼叫之前使用 "响应组" 选项卡登录到其响应组。 如果你部署了 "响应组" 选项卡, 则在部署 Office Communicator 2007 R2 选项卡 .xml 文件时选择该位置。

    
    </div>

6.  向用户提供代理需要登录和注销其响应组的更新的 URL。
    
    <div>
    

    > [!NOTE]  
    > URL 通常https://webpoolFQDN/RgsClients/Tab.aspx是, 其中 webpoolFQDN 是与你刚刚迁移到 Lync Server 2013 的池关联的 web 池的完全限定的域名 (FQDN)。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 用户升级到 Lync 2013 后不需要执行此步骤, 因为 URL 可通过 Lync 中的 "<STRONG>工具</STRONG>" 菜单使用。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 验证响应组迁移

1.  打开 Lync Server "控制面板"。

2.  在左侧导航窗格中, 单击 "**响应组**"。

3.  在 "**工作流**" 选项卡上, 验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有工作流。

4.  单击 "**队列**" 选项卡, 验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有队列。

5.  单击 "**组**" 选项卡, 验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有代理组。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>使用 Cmdlet 验证响应组迁移

1.  打开 Lync Server 命令行管理程序。
    
    有关以下 cmdlet 的详细信息, 请运行:
    
        Get-Help <cmdlet name> -Detailed

2.  在命令行中键入：
    
        Get-CsRgsAgentGroup

3.  验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有代理组。

4.  在命令行中键入：
    
        Get-CsRgsQueue

5.  验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有队列。

6.  在命令行中键入：
    
        Get-CsRgsWorkflow

7.  验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有工作流。

</div>

</div>

<span> </span>

</div>

</div>

</div>


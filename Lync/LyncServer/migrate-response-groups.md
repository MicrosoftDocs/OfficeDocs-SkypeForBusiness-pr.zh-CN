---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d69bcdffdb420d0c79d049f83ab5fa23ddc968
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>迁移响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-23_

将用户移动到 Lync Server 2013 池之后，可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Lync Server 2013 池。 迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序进行处理。 旧版池不再处理对响应组的调用。

<div>


> [!NOTE]  
> 虽然您可以在将所有用户移动到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。 特别是，响应组代理的用户在移动到 Lync Server 2013 池之前，不会具有新功能的完整功能。



</div>

在迁移响应组之前，必须已部署包含响应组应用程序的 Lync Server 2013 池。 默认情况下，在部署企业语音时，会安装并激活响应组应用程序。 您可以通过运行**get-csservice – ApplicationServer** cmdlet 来确保响应组应用程序已安装。

<div>


> [!NOTE]  
> 您可以先在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组，然后再迁移旧版响应组。



</div>

若要将响应组从旧版池迁移到 Lync Server 2013，请运行**CsRgsConfiguration** cmdlet。

<div>


> [!IMPORTANT]  
> 响应组迁移 cmdlet 将移动整个池的响应组配置。 您不能选择特定组、队列或工作流进行迁移。



</div>

迁移响应组之后，需要使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 来验证是否已成功移动所有代理组、队列和工作流。

迁移响应组时，不会删除 Lync Server 2010 响应组。 在迁移后使用 Lync Server 控制面板或 Lync Server 命令行管理程序管理响应组时，您可以看到 Lync Server 2010 响应组和 Lync Server 2013 响应组。 应仅将更新应用到 Lync Server 2013 响应组。 仅出于回滚目的保留 Lync Server 2010 响应组。

<div>


> [!WARNING]  
> 在完成迁移并创建新的响应组之后，Lync Server 控制面板和 Lync Server 命令行管理程序将显示每个响应组的 Lync Server 2010 和 Lync Server 2013 版本。 请勿使用 Lync Server 控制面板或 Lync Server 命令行管理程序删除 Lync Server 2010 响应组。 如果确实删除了一个，则在迁移过程中创建的相应响应组将停止工作。 当您停止 Lync Server 2010 池时，将删除 Lync Server 2010 响应组。



</div>

<div>


> [!IMPORTANT]  
> 建议在停用池之前不要删除之前的部署中的任何数据。 此外，强烈建议在迁移后立即导出响应组。 如果应删除 Lync Server 2010 响应组，则可以从备份中还原响应组，以获取 Lync Server 2013 响应组再次运行。



</div>

Lync Server 2013 引入了名为 "**工作流类型**" 的新响应组功能。 “工作流类型”**** 可以是“托管”**** 的，也可以是“非托管”**** 的。 所有响应组都是使用设置为“非托管”**** 的“工作流类型”**** 和空管理员列表进行迁移的。

在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。 但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。

下面的迁移响应组配置的过程假设您的旧版池和 Lync Server 2013 池之间具有一对一关系。 如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1.  使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  将响应组和代理迁移到 Lync Server 2013 池之后，代理用于登录和注销的 URL 是 Lync Server 2013 URL，可从 "**工具**" 菜单中获取。 提醒代理更新对新 URL 的所有引用（例如书签）。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板验证响应组迁移

1.  使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航窗格中，单击“响应组”****。

4.  在 "**工作流**" 选项卡上，验证 "Lync Server 2010" 环境中的所有工作流是否都包含在列表中。

5.  单击 "**队列**" 选项卡，并验证 "Lync Server 2010" 环境中的所有队列是否都包含在列表中。

6.  单击 "**组**" 选项卡，并验证您在 Lync Server 2010 环境中的所有代理组是否都包含在列表中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序验证响应组迁移

1.  使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
        Get-Help <cmdlet name> -Detailed

3.  以
    
        Get-CsRgsAgentGroup

4.  验证 Lync Server 2010 环境中的所有代理组是否都包含在列表中。

5.  以
    
        Get-CsRgsQueue

6.  验证 Lync Server 2010 环境中的所有队列是否都包含在列表中。

7.  以
    
        Get-CsRgsWorkflow

8.  验证 Lync Server 2010 环境中的所有工作流是否都包含在列表中。

</div>

</div>

<span> </span>

</div>

</div>

</div>


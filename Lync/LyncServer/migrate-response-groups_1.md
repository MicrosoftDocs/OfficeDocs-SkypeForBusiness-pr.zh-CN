---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36b37fc6a67a1935c442edb4e2e8ef0d8812315c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>迁移响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

将用户移动到 Lync Server 2013 池之后，可以迁移响应组。 迁移响应组包括复制代理组、队列、工作流和音频文件，以及将响应组联系人对象从旧部署移动到 Lync Server 2013 池。 迁移旧版响应组后，对响应组的呼叫由 Lync Server 2013 池中的响应组应用程序进行处理。 旧版池不再处理对响应组的调用。

<div>


> [!NOTE]  
> 虽然您可以在将所有用户移动到 Lync Server 2013 池之前迁移响应组，但我们建议您首先移动所有用户。 特别是，响应组代理的用户在移动到 Lync Server 2013 池之前，不会具有新功能的完整功能。



</div>

在迁移响应组之前，必须已部署包含响应组应用程序的 Lync Server 2013 池。 默认情况下，在部署企业语音时，会安装并激活响应组应用程序。 您可以通过运行**get-csservice – ApplicationServer** cmdlet 来确保响应组应用程序已安装。

<div>


> [!NOTE]  
> 您可以先在 Lync Server 2013 池中创建新的 Lync Server 2013 响应组，然后再迁移旧版响应组。



</div>

若要将响应组从旧版池迁移到 Lync Server 2013，请运行**CsRgsConfiguration** cmdlet。 在运行 **Move-CsRgsConfiguration** 之前，您必须先安装 Windows Management Instrumentation (WMI) Backward Compatibility 接口包。 可通过运行 OCSWMIBC.msi 来安装此应用程序。 OCSWMIBC.msi 位于安装介质上的 Setup 文件夹中。

<div>


> [!IMPORTANT]  
> 响应组迁移 cmdlet 将移动整个池的响应组配置。 您不能选择特定组、队列或工作流进行迁移。



</div>

迁移响应组之后，需要更新正式代理用于登录到其响应组的 URL，并使用 Lync Server 控制面板或 Lync Server 命令行管理程序 cmdlet 来验证是否已移动所有代理组、队列和工作流失败.

<div>


> [!WARNING]  
> 迁移响应组时，不会删除 Office 通信服务器 2007 R2 响应组。 请勿删除 Office 通信服务器 2007 R2 响应组。 如果删除 Office 通信服务器 2007 R2 响应组，Lync Server 2013 中的响应组将停止工作。



</div>

<div>


> [!IMPORTANT]  
> 建议在停用池之前不要删除之前的部署中的任何数据。 此外，强烈建议在迁移后立即导出响应组。 如果删除了 Office 通信服务器 2007 R2 响应组，则可以从备份中还原响应组，以获取 Lync Server 2013 响应组再次运行。



</div>

在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。 但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。

<div>


> [!IMPORTANT]  
> 建议在停用旧池之前不要删除其中的任何响应组数据。



</div>

迁移响应组配置后遵循的过程假定您的旧池和 Lync Server 2013 池之间具有一对一关系。 如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1.  在安装介质的 Setup 文件夹中找到 OCSWMIBC.msi 并安装它。

2.  使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。

3.  打开 Lync Server 命令行管理程序。

4.  在命令行中键入：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果您在 Office 通信服务器 2007 R2 环境中为 Microsoft Office Communicator 2007 R2 部署了 "响应组" 选项卡，请从 Office Communicator 2007 R2 选项卡 .xml 文件中删除该选项卡。
    
    <div>
    

    > [!NOTE]  
    > 正式代理会在接收呼叫之前，先使用响应组选项卡登录其响应组。 如果您部署了 "响应组" 选项卡，则您在部署 Office Communicator 2007 R2 选项卡 .xml 文件时选择了该位置。

    
    </div>

6.  向用户提供代理登录和注销其响应组所需的更新 URL。
    
    <div>
    

    > [!NOTE]  
    > URL 通常https://webpoolFQDN/RgsClients/Tab.aspx为，其中 webpoolFQDN 是与您刚迁移到 Lync Server 2013 的池关联的 web 池的完全限定域名（FQDN）。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 用户升级到 Lync 2013 后不需要执行此步骤，因为 URL 可从 Lync 的 "<STRONG>工具</STRONG>" 菜单中获取。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板验证响应组迁移的具体方法

1.  打开“Lync Server 控制面板”。

2.  在左侧导航窗格中，单击“响应组”****。

3.  在 "**工作流**" 选项卡上，验证 "Office 通信服务器 2007 R2" 环境中的所有工作流是否都包含在列表中。

4.  单击 "**队列**" 选项卡，并验证 "Office 通信服务器 2007 R2" 环境中的所有队列是否都包含在列表中。

5.  单击 "**组**" 选项卡，并验证 "Office 通信服务器 2007 R2" 环境中的所有代理组是否都包含在列表中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>使用 Cmdlet 验证响应组迁移

1.  打开 Lync Server 命令行管理程序。
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
        Get-Help <cmdlet name> -Detailed

2.  在命令行中键入：
    
        Get-CsRgsAgentGroup

3.  验证 Office 通信服务器 2007 R2 环境中的所有代理组是否都包含在列表中。

4.  在命令行中键入：
    
        Get-CsRgsQueue

5.  验证 Office 通信服务器 2007 R2 环境中的所有队列是否都包含在列表中。

6.  在命令行中键入：
    
        Get-CsRgsWorkflow

7.  验证您的 Office 通信服务器 2007 R2 环境中的所有工作流是否都包含在列表中。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 创建或修改客户端版本配置设置的集合
description: 创建或修改客户端版本配置设置的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0082b618b8417c9d0da44599f1606cd238dfd7e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578308"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改客户端版本配置设置的集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置与 Lync Server 一起安装，用于为整个服务器部署启用或禁用客户端版本控制。 您还可以为各个网站配置客户端版本配置设置。 您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改客户端版本配置设置。

<div>


> [!NOTE]
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建或修改客户端版本配置设置

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 " **客户端**"，然后单击 " **客户端版本配置** " 导航按钮。

4.  在 " **客户端版本配置** " 页上，执行以下操作：
    
      - 若要创建新的配置，请单击 " **新建**"，选择一个网站，单击 **"确定** 名称"，然后更新设置。
    
      - 若要修改配置，请选择该配置，单击 " **编辑**"，再单击 " **显示详细信息**"，然后对设置进行更改。

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建或修改客户端版本配置设置

您可以使用 **CsClientVersionConfiguration** cmdlet 创建客户端版本配置设置，并使用 **CsClientVersionConfiguration** cmdlet 对其进行修改。 这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>创建新的客户端版本配置设置集合

  - 以下命令将创建应用于 Redmond 站点的客户端版本配置设置的新集合。 在此示例中，将禁用 Redmond 站点的客户端版本控制。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>为网站启用客户端版本控制

  - 此命令为 Redmond 站点启用客户端版本控制。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>在整个组织中禁用客户端版本控制

  - 在此示例中，将对组织中使用的所有客户端版本配置设置禁用客户端版本控制。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

有关详细信息，请参阅 [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 和 [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


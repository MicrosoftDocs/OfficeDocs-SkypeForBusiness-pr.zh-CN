---
title: Lync Server 2013：启用或禁用客户端版本控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d09d563abb44884b1248974ea188dc142e1b95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用客户端版本控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

客户端版本配置设置用于为全局或对特定网站启用或禁用客户端版本控制。 全局客户端版本配置将随 Lync Server 2013 一起安装，并用于为整个服务器部署启用或禁用客户端版本控制。 启用全局配置后，任何已有的客户端版本策略将在用户尝试登录时生效。 如果您不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。 您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序启用或禁用客户端版本控制。

<div>


> [!NOTE]  
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板启用或禁用客户端版本管理

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**" 导航按钮。

4.  请执行以下操作：
    
      - 若要全局启用或禁用客户端版本控制，请双击**全局**配置，然后修改设置。
    
      - 若要启用或禁用特定网站的客户端版本控制，请单击 "**新建**"，选择网站，单击 **"确定**"，然后修改网站的设置。

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用客户端版本控制

您可以使用**CsClientVersionConfiguration** cmdlet 启用或禁用客户端版本控制。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-client-versioning"></a>启用客户端版本控制

  - 可以通过将**Enabled**属性设置为 True 来启用客户端版本控制（$True）。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>禁用客户端版本控制

  - 您可以通过将**Enabled**属性设置为 False （$False）来禁用客户端版本控制。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

有关详细信息，请参阅[CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


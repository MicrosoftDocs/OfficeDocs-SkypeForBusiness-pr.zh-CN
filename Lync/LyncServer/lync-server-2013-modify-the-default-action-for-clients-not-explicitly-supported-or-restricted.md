---
title: 修改不显式支持或限制的客户端的默认操作
description: 修改不显式支持或不受限制的客户端的默认操作。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c28ad4d357953c22f889309323ccbb95c6840e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566948"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>修改在 Lync Server 2013 中未明确支持或不受限制的客户端的默认操作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

除了指定要在 Lync Server 2013 环境中支持的客户端版本之外，还可以为尚未定义版本策略的客户端指定默认操作。 这使您可以限制在 Lync Server 环境中使用的客户端版本，这有助于控制与支持多个客户端版本相关的成本。

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>修改未显式支持或限制的客户端的默认操作

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“客户端版本配置”****。

4.  在“客户端版本配置”**** 页上，双击列表中的“全局”**** 配置。

5.  在“编辑客户端版本配置”**** 对话框中，验证是否已选中“启用版本控制”**** 复选框，然后在“默认操作”**** 下选择下列操作之一：
    
      - **允许**    如果客户端版本与**客户端版本策略**列表中的任何筛选器都不匹配，则允许客户端登录。
    
      - **阻止**    如果客户端版本与**客户端版本策略**列表中的任何筛选器都不匹配，则阻止客户端登录。
    
      - **带 URL**     的块如果客户端版本与 "**客户端版本策略**" 列表中的任何筛选器都不匹配，则阻止客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。
    
      - **允许 URL**    如果客户端版本与 "**客户端版本策略**" 列表中的任何筛选器都不匹配，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。

6.  如果选择“使用 URL 阻止”****，则在“URL”**** 框中键入将包含在错误消息中的客户端下载 URL。

7.  单击“提交”****。

</div>

<div>

## <a name="to-disable-client-version-control"></a>禁用客户端版本控制

  - 要禁用版本控制以允许所有版本的客户端登录，请清除“启用版本控制”**** 复选框，然后单击“提交”****。

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 修改默认操作

使用 Windows PowerShell 命令行接口和 **CsClientVersionPolicy** cmdlet 来管理用户尝试使用不是明确支持或受客户端版本策略限制的客户端登录时所采取的默认操作。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>配置默认操作以阻止访问

  - 以下命令可将 Redmond 站点的默认操作设置为“阻止”。这将阻止针对没有客户端版本配置规则的任何客户端的注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>将默认操作配置为允许访问

  - 在此示例中，Redmond 站点的默认操作将设置为“允许”。这将允许针对没有客户端版本配置规则的任何客户端的注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

有关详细信息，请参阅 [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


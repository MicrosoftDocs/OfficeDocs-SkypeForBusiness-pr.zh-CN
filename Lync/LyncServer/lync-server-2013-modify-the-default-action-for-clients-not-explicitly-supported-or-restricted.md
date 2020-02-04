---
title: 修改不明确支持或限制的客户端的默认操作
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
ms.openlocfilehash: 0262bface172c965d12fc276bc08882cac8348ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>修改在 Lync Server 2013 中未明确支持或限制的客户端的默认操作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

除了指定你希望在 Lync Server 2013 环境中支持的客户端版本，还可以为尚未定义版本策略的客户端指定默认操作。 这使你能够限制 Lync Server 环境中使用的客户端版本，这有助于你控制与支持多个客户端版本相关联的成本。

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>修改不明确支持或限制的客户端的默认操作

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**"。

4.  在 "**客户端版本配置**" 页面上，双击列表中的**全局**配置。

5.  在 "**编辑客户端版本配置**" 对话框中，验证已选中 "**启用版本控制**" 复选框，然后在 "**默认操作**" 下，选择下列选项之一：
    
      - ****   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，允许客户端登录。
    
      - ****   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，则 Block 将阻止客户端登录。
    
      - **带 url**   的块阻止客户端在客户端版本与**客户端版本策略**列表中的任何筛选器不匹配时登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。
    
      - **允许使用 URL**   如果客户端版本与**客户端版本策略**列表中的任何筛选器不匹配，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。

6.  如果选择了 "**带 URL 的块**"，请在 " **URL** " 框中键入要包含在错误消息中的客户端下载 URL。

7.  单击“**提交**”。

</div>

<div>

## <a name="to-disable-client-version-control"></a>禁用客户端版本控制

  - 若要在不考虑客户端版本的情况下禁用版本控制以允许所有客户端登录，请清除 "**启用版本控制**" 复选框，然后单击 "**提交**"。

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 修改默认操作

使用 Windows PowerShell 命令行界面和**CsClientVersionPolicy** cmdlet 管理用户尝试使用不是由客户端版本策略明确支持或限制的客户端尝试登录时所采取的默认操作。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>配置默认操作阻止访问

  - 以下命令设置雷德蒙网站块的默认操作。 这将阻止不存在任何客户端版本配置规则的任何客户端的注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>将默认操作配置为允许访问

  - 在此示例中，雷德蒙网站的默认操作设置为 "允许"。 这将允许为不存在任何客户端版本配置规则的任何客户端注册。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

有关详细信息，请参阅[CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) Cmdlet 的帮助主题。

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


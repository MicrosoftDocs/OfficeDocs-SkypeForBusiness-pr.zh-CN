---
title: Lync Server 2013：删除现有注册器配置设置
description: Lync Server 2013：删除现有注册器配置设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b625b97724edf0ecf8928ec31d89a6166230c4c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555408"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有的注册器配置设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

按照以下步骤删除注册器。

<div>

## <a name="to-delete-registrar-configuration-settings"></a>删除注册器配置设置

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。

4.  在 " **注册** 器" 页上，在 "搜索" 字段中，键入要删除的注册器的全部或部分名称。

5.  在列表中，单击所需的注册器，单击 " **编辑**"，然后单击 " **删除**"。

6.  单击“确定”****。

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除注册器配置设置

您可以使用 Windows PowerShell 和 **CsProxyConfiguration** Cmdlet 删除注册器配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>删除一组特定的注册器安全设置

  - 以下命令将删除应用于边缘服务器 atl-edge-011.litwareinc.com 的注册器安全设置：
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有注册器安全设置

  - 以下命令将删除应用于注册器服务的所有注册器安全设置：
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>删除允许 NTLM 身份验证的所有注册器安全设置

  - 以下命令将删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

有关详细信息，请参阅 [CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


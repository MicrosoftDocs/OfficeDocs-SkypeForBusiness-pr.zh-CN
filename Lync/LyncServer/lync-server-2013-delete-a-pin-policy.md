---
title: Lync Server 2013：删除 PIN 策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f8c9899665353d33682cc0c780cd7411b0abfd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除 PIN 策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

按照以下步骤删除个人标识号 (PIN) 策略。

<div>


> [!NOTE]  
> 无法删除全局 PIN 策略。



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 控制面板中删除 PIN 策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。

4.  在“PIN 策略”**** 页上的搜索字段中，键入要删除的策略的全部或部分名称。

5.  在策略列表中，单击所需的策略，再单击“编辑”****，然后单击“删除”****。

6.  单击“确定”****。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

您可以使用 Windows PowerShell 和 Get-cspinpolicy cmdlet 删除 PIN 策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specific-pin-policy"></a>删除特定的 PIN 策略

  - 以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>删除应用到站点范围的所有 PIN 策略

  - 以下命令删除在站点作用域配置的所有 PIN 策略：
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>删除允许使用通用模式的所有 PIN 策略

  - 以下命令删除允许使用通用模式的所有 PIN 策略：G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

有关详细信息，请参阅[get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


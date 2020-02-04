---
title: Lync Server 2013：重置外部用户访问的全局策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中重置外部用户访问的全局策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

您不能完全删除全局策略。 使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>将全局策略重置为默认设置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**外部用户访问**"，单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 选项卡上，单击 "全局策略"，单击 "**编辑**"，然后单击 "**删除**"。

5.  当系统提示确认删除时，单击 **"确定"**。 将在页面顶部显示一条消息，通知您全局策略已重置。

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重置全局外部访问策略

全局外部访问策略可以通过使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 进行重置。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从远程会话 Windows PowerShell 运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-reset-the-global-external-access-policy"></a>重置全局外部访问策略

  - 此命令将重置全局外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：启用或禁用热 desking
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb052f3a0743edac47ccfbe3786943820c59f78f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515539"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用热 desking

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

你可以将公用区域电话设置为 *热电话*。 使用热电话，用户可以登录到自己的用户帐户，并在登录后使用 Lync Server 功能及其自己的用户配置文件设置。 热 desking 通过使用客户端策略进行管理：若要启用或禁用热 desking，需要修改公共区域电话所使用的客户端策略。 有关如何确定已分配给您的公共区域电话的会议策略的详细信息，请参阅 [在 Lync Server 2013 中查看常见区域电话信息](lync-server-2013-view-common-area-phone-information.md)。

您可以使用 **set-csclientpolicy** Cmdlet 或 **Set-csclientpolicy** cmdlet 的 EnableHotdesking 参数在手机上启用或禁用热 desking，如下所示。 从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>


<div>

## <a name="enabling-hot-desking"></a>启用热 desking

  - 若要为公用区域电话启用热 desking，您必须修改已分配给该电话 (或电话集合) 的客户端策略。
    
    在确定了需要修改的策略后，下一步是使用 **set-csclientpolicy** Cmdlet 将 EnableHotdesking 参数设置为 True。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 或者，也可以使用 **set-csclientpolicy** cmdlet 创建启用热 desking 的新客户端策略。 例如：
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> 创建此策略后，必须将其分配给适当的公共区域电话。 有关详细信息，请参阅 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">在 Lync Server 2013 中将策略分配给公用区域电话</A>。



</div>

<div>

## <a name="disabling-hot-desking"></a>禁用热 desking

  - 若要为公用区域电话禁用热 desking，请将 **set-csclientpolicy** Cmdlet 的 EnableHotdesking 参数重置为默认值 False。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

有关详细信息，请参阅 [set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和 [Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


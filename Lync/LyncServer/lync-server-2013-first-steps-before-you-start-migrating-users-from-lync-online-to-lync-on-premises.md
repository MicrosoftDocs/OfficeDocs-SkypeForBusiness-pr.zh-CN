---
title: Lync Server 2013：开始将用户从 Lync Online 迁移到 Lync 本地 Lync 之前的第一步
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>在 Lync Server 2013 中开始将用户从 Lync Online 迁移到 Lync 本地的第一步

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-08_

在开始将 Lync Online 用户移动到本地环境之前，请检查是否满足以下所有条件：

  - 必须完全部署和验证 Lync Server 本地环境。 有关详细信息，请参阅[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

  - 必须为你的 Lync Online 租户配置远程 PowerShell 访问。
    
    为此，请首先安装可在此处获取的适用于 Windows PowerShell 的 Lync Online 模块： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911)。
    
    安装该模块后，可以通过在 Lync Server 命令行管理程序中键入以下 cmdlet 来建立远程会话：
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    有关如何使用 Lync Online 建立远程 PowerShell 会话的详细信息，请参阅[使用 Windows PowerShell 连接到 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
    有关使用 Lync Online PowerShell 模块的详细信息，请参阅[Using Windows PowerShell to Manage Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

  - 必须为共享 SIP 地址空间配置 Lync Online。 若要执行此操作，请先启动与 Lync Online 的远程 Powershell 会话。 然后运行以下 cmdlet：
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

完成这些步骤后，您可以继续将[Lync Online 用户迁移到 Lync Server 2013 中的 lync 本地](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。

</div>

<span> </span>

</div>

</div>

</div>


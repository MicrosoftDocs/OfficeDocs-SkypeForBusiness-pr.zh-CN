---
title: 'Lync Server 2013: 开始将用户从 Lync Online 迁移到本地 Lync 之前的第一步'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e278fcb1e63c1db1334e625765d65d5d556e934
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>在 Lync Server 2013 中开始将用户从 Lync Online 迁移到本地 Lync 之前的第一步

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-08_

在开始将 Lync Online 用户移动到本地环境之前, 请检查以下所有条件是否为 true:

  - 您的 Lync Server 本地环境必须完全部署和验证。 有关详细信息, 请参阅[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

  - 必须为远程 PowerShell 访问配置 Lync Online 租户。
    
    若要执行此操作, 请首先安装适用于 Windows PowerShell 的 Lync Online 模块, 可在[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)此处获取:。
    
    安装该模块后, 您可以通过在 Lync Server Management Shell 中键入以下 cmdlet 来建立远程会话:
    
       ```
        Import-Module LyncOnlineConnector
       ```  
    
       ```
        $cred = Get-Credential
       ``` 
    
       ```
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```
        Import-PSSession $CSSession -AllowClobber
       ```
    
    有关如何建立与 Lync Online 的远程 PowerShell 会话的详细信息, 请参阅[使用 Windows PowerShell 连接到 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
    有关使用 Lync Online PowerShell 模块的详细信息, 请参阅[使用 Windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

  - 必须为共享 SIP 地址空间配置您的 Lync Online。 若要执行此操作, 请首先启动与 Lync Online 的远程 Powershell 会话。 然后运行以下 cmdlet：
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

完成这些步骤后, 您可以继续在[Lync Server 2013 中将 Lync Online 用户迁移到本地 lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。

</div>

<span> </span>

</div>

</div>

</div>


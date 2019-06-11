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

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="7f454-102">在 Lync Server 2013 中开始将用户从 Lync Online 迁移到本地 Lync 之前的第一步</span><span class="sxs-lookup"><span data-stu-id="7f454-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f454-103">_**主题上次修改时间:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="7f454-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="7f454-104">在开始将 Lync Online 用户移动到本地环境之前, 请检查以下所有条件是否为 true:</span><span class="sxs-lookup"><span data-stu-id="7f454-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="7f454-105">您的 Lync Server 本地环境必须完全部署和验证。</span><span class="sxs-lookup"><span data-stu-id="7f454-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="7f454-106">有关详细信息, 请参阅[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7f454-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="7f454-107">必须为远程 PowerShell 访问配置 Lync Online 租户。</span><span class="sxs-lookup"><span data-stu-id="7f454-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="7f454-108">若要执行此操作, 请首先安装适用于 Windows PowerShell 的 Lync Online 模块, 可在[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)此处获取:。</span><span class="sxs-lookup"><span data-stu-id="7f454-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="7f454-109">安装该模块后, 您可以通过在 Lync Server Management Shell 中键入以下 cmdlet 来建立远程会话:</span><span class="sxs-lookup"><span data-stu-id="7f454-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="7f454-110">有关如何建立与 Lync Online 的远程 PowerShell 会话的详细信息, 请参阅[使用 Windows PowerShell 连接到 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f454-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="7f454-111">有关使用 Lync Online PowerShell 模块的详细信息, 请参阅[使用 Windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f454-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="7f454-112">必须为共享 SIP 地址空间配置您的 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="7f454-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="7f454-113">若要执行此操作, 请首先启动与 Lync Online 的远程 Powershell 会话。</span><span class="sxs-lookup"><span data-stu-id="7f454-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="7f454-114">然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f454-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="7f454-115">完成这些步骤后, 您可以继续在[Lync Server 2013 中将 Lync Online 用户迁移到本地 lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="7f454-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


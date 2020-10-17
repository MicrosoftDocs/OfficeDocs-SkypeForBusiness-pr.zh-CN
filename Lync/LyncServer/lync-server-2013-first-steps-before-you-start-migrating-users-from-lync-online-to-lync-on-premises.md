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
ms.openlocfilehash: 8065d1c09ab48b1b3a874fd11d7f8fcad298bfcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500839"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="d8268-102">在 Lync Server 2013 中开始将用户从 Lync Online 迁移到 Lync 本地的第一步</span><span class="sxs-lookup"><span data-stu-id="d8268-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8268-103">_**上次修改的主题：** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="d8268-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="d8268-104">在开始将 Lync Online 用户移动到本地环境之前，请检查是否满足以下所有条件：</span><span class="sxs-lookup"><span data-stu-id="d8268-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="d8268-105">必须完全部署和验证 Lync Server 本地环境。</span><span class="sxs-lookup"><span data-stu-id="d8268-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="d8268-106">有关详细信息，请参阅 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d8268-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="d8268-107">必须为你的 Lync Online 租户配置远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="d8268-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="d8268-108">为此，请首先安装可在此处获取的适用于 Windows PowerShell 的 Lync Online 模块： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) 。</span><span class="sxs-lookup"><span data-stu-id="d8268-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="d8268-109">安装该模块后，可以通过在 Lync Server 命令行管理程序中键入以下 cmdlet 来建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="d8268-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="d8268-110">有关如何使用 Lync Online 建立远程 PowerShell 会话的详细信息，请参阅 [使用 Windows PowerShell 连接到 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d8268-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="d8268-111">有关使用 Lync Online PowerShell 模块的详细信息，请参阅 [Using Windows PowerShell to Manage Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d8268-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="d8268-112">必须为共享 SIP 地址空间配置 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="d8268-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="d8268-113">若要执行此操作，请先启动与 Lync Online 的远程 Powershell 会话。</span><span class="sxs-lookup"><span data-stu-id="d8268-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="d8268-114">然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d8268-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="d8268-115">完成这些步骤后，您可以继续将 [Lync Online 用户迁移到 Lync Server 2013 中的 lync 本地](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="d8268-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


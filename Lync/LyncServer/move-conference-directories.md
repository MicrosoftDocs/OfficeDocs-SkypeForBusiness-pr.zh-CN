---
title: 移动会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="4dc5f-102">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="4dc5f-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc5f-103">_**主题上次修改时间:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4dc5f-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4dc5f-104">在取消池之前, 你需要针对 Office 通信服务器 2007 R2 池中的每个会议目录执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="4dc5f-105">将会议目录移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dc5f-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="4dc5f-106">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4dc5f-107">若要获取组织中的会议目录的标识, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="4dc5f-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="4dc5f-108">由于此 cmdlet 返回你的组织中的所有会议目录, 你可能希望将结果限制为仅限于你希望解除授权的池。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="4dc5f-109">例如, 如果要使用完全限定的域名 (FQDN) pool01.contoso.net 解除池的授权, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="4dc5f-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="4dc5f-110">此 cmdlet 返回服务 ID 包含 FQDN pool01.contoso.net 的所有会议目录。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="4dc5f-111">若要移动会议目录, 请对池中的每个会议目录运行以下操作:</span><span class="sxs-lookup"><span data-stu-id="4dc5f-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="4dc5f-112">例如：</span><span class="sxs-lookup"><span data-stu-id="4dc5f-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="4dc5f-113">你可能会遇到如下所示的错误, 该错误由 Lync Server 管理外壳要求从 Active Directory 中更新的权限集导致的。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="4dc5f-114">若要解决此错误, 请关闭当前窗口并打开新的 Lync Server 命令行管理程序, 然后再次运行该命令。</span><span class="sxs-lookup"><span data-stu-id="4dc5f-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="4dc5f-115">![移动-CsConferenceDirectory 错误输出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "移动-CsConferenceDirectory 错误输出")</span><span class="sxs-lookup"><span data-stu-id="4dc5f-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


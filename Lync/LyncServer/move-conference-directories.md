---
title: 移动会议目录
description: 移动会议目录。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a91c30c0bedc84c684a096f5ea482fa911dc798
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549728"
---
# <a name="move-conference-directories"></a><span data-ttu-id="89461-103">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="89461-103">Move conference directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89461-104">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="89461-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="89461-105">在取消池的授权之前，您需要为 Office 通信服务器 2007 R2 池中的每个会议目录执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="89461-105">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="89461-106">将会议目录移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89461-106">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="89461-107">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="89461-107">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="89461-108">若要获取组织中会议目录的标识，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89461-108">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="89461-p101">因为此 cmdlet 返回组织中的所有会议目录，所以您可能希望将结果限制为仅要停用的池。例如，如果要停用具有完全限定域名 (FQDN) pool01.contoso.net 的池：</span><span class="sxs-lookup"><span data-stu-id="89461-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="89461-111">此 cmdlet 返回其中服务 ID 包含 FQDN pool01.contoso.net 的所有会议目录。</span><span class="sxs-lookup"><span data-stu-id="89461-111">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="89461-112">若要移动会议目录，请对池中的每个会议目录运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89461-112">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="89461-113">例如：</span><span class="sxs-lookup"><span data-stu-id="89461-113">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="89461-114">您可能会遇到以下错误： Lync Server 命令行管理程序需要从 Active Directory 中更新一组权限导致的错误。</span><span class="sxs-lookup"><span data-stu-id="89461-114">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="89461-115">若要解决此错误，请关闭当前窗口并打开新的 Lync Server 命令行管理程序，然后再次运行该命令。</span><span class="sxs-lookup"><span data-stu-id="89461-115">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="89461-116">![移动-New-csconferencedirectory 错误输出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 错误输出")</span><span class="sxs-lookup"><span data-stu-id="89461-116">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


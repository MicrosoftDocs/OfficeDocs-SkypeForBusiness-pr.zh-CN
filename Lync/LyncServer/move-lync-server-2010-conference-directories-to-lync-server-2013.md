---
title: 将 Lync Server 2010 会议目录移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="37ab1-102">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="37ab1-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ab1-103">_**主题上次修改时间:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="37ab1-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="37ab1-104">在取消池之前, 必须针对 Lync Server 2010 池中的每个会议目录执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="37ab1-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="37ab1-105">将会议目录移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37ab1-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="37ab1-106">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="37ab1-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="37ab1-107">若要获取组织中的会议目录的标识, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="37ab1-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="37ab1-108">上面的命令返回你的组织中的所有会议目录。</span><span class="sxs-lookup"><span data-stu-id="37ab1-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="37ab1-109">因此, 你可能希望将结果限制为即将停止的池。</span><span class="sxs-lookup"><span data-stu-id="37ab1-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="37ab1-110">例如, 如果你使用完全限定的域名 (FQDN) pool01.contoso.net 取消池, 请使用此命令将返回的数据限制为来自该池中的会议目录:</span><span class="sxs-lookup"><span data-stu-id="37ab1-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="37ab1-111">该命令仅返回 ServiceID 属性包含 FQDN pool01.contoso.net 的会议目录。</span><span class="sxs-lookup"><span data-stu-id="37ab1-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="37ab1-112">若要移动会议目录, 请对池中的每个会议目录运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="37ab1-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="37ab1-113">例如, 若要移动会议目录 3, 请使用此命令, 将 Lync Server 2013 池指定为 TargetPool:</span><span class="sxs-lookup"><span data-stu-id="37ab1-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="37ab1-114">如果要移动池中的所有会议目录, 请使用类似于以下内容的命令:</span><span class="sxs-lookup"><span data-stu-id="37ab1-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="37ab1-115">有关取消 Lync 2010 池的完整、分步说明, 请参阅文档 "卸载 Microsoft Lync Server 2010 和[http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)删除服务器角色" (可从中下载)。</span><span class="sxs-lookup"><span data-stu-id="37ab1-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="37ab1-116">移动会议目录时, 可能会遇到以下错误:</span><span class="sxs-lookup"><span data-stu-id="37ab1-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="37ab1-117">此错误通常在 Lync Server Management Shell 需要更新的 Active Directory 权限集以便完成任务时出现。</span><span class="sxs-lookup"><span data-stu-id="37ab1-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="37ab1-118">若要解决此问题, 请关闭该命令行管理程序的当前实例, 然后打开一个新的 Shell 实例并重新运行该命令, 以便移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="37ab1-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


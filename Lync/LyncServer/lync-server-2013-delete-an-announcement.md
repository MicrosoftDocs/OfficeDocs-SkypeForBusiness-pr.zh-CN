---
title: Lync Server 2013：删除通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66d10f53f89690a25860ba403ed7a8b21f7a1d4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="073d1-102">在 Lync Server 2013 中删除通知</span><span class="sxs-lookup"><span data-stu-id="073d1-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="073d1-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="073d1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="073d1-104">使用以下过程可删除用于呼叫未分配号码的通知。</span><span class="sxs-lookup"><span data-stu-id="073d1-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="073d1-105">删除通知</span><span class="sxs-lookup"><span data-stu-id="073d1-105">To delete an announcement</span></span>

1.  <span data-ttu-id="073d1-106">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="073d1-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="073d1-107">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="073d1-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="073d1-p101">列出组织中的所有通知。在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="073d1-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="073d1-p102">在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="073d1-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="073d1-112">例如：</span><span class="sxs-lookup"><span data-stu-id="073d1-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="073d1-113">有关更多选项的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">CsAnnouncement</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>。</span><span class="sxs-lookup"><span data-stu-id="073d1-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="073d1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="073d1-114">See Also</span></span>


[<span data-ttu-id="073d1-115">在 Lync Server 2013 中创建通知</span><span class="sxs-lookup"><span data-stu-id="073d1-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="073d1-116">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="073d1-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="073d1-117">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="073d1-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


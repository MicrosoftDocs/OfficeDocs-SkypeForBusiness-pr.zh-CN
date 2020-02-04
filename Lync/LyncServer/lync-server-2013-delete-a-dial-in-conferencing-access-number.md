---
title: Lync Server 2013：删除电话拨入式会议接入号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d461aafd4f111484faf295bef2dd50685e41e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="2d626-102">删除 Lync Server 2013 中的电话拨入式会议接入号码</span><span class="sxs-lookup"><span data-stu-id="2d626-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d626-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2d626-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2d626-104">请按照以下步骤删除电话拨入式会议接入号码。</span><span class="sxs-lookup"><span data-stu-id="2d626-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="2d626-105">删除电话拨入式会议接入号码</span><span class="sxs-lookup"><span data-stu-id="2d626-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="2d626-106">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2d626-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2d626-107">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2d626-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d626-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2d626-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d626-109">在左侧导航栏中，单击“**会议**”，然后单击“**拨入访问号码**”。</span><span class="sxs-lookup"><span data-stu-id="2d626-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="2d626-110">在页面上，单击列表中要删除的电话拨入式号码，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="2d626-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="2d626-111">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2d626-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d626-112">使用 Windows PowerShell Cmdlet 删除电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="2d626-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2d626-113">可以使用 Windows PowerShell 和**CsDialInConferencingAccessNumber** cmdlet 删除电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="2d626-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="2d626-114">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="2d626-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2d626-115">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="2d626-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="2d626-116">删除特定的电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="2d626-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="2d626-117">此命令将删除具有标识 sip:RedmondDialInAccess@litwareinc.com 的电话拨入式会议访问号码：</span><span class="sxs-lookup"><span data-stu-id="2d626-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="2d626-118">删除分配给特定区域的所有拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="2d626-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="2d626-119">此命令将删除与西北地区相关联的所有拨入式会议访问号码：</span><span class="sxs-lookup"><span data-stu-id="2d626-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="2d626-120">删除基于主要语言的电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="2d626-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="2d626-121">此命令将删除意大利语是主要语言的所有电话拨入式会议访问号码：</span><span class="sxs-lookup"><span data-stu-id="2d626-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="2d626-122">有关详细信息，请参阅[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2d626-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


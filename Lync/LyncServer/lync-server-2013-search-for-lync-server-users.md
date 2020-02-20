---
title: Lync Server 2013：搜索 Lync Server 用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665d8bbb0f3409de62565c25dfdb494fd140d636
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="59e14-102">在 Lync Server 2013 中搜索 Lync Server 用户</span><span class="sxs-lookup"><span data-stu-id="59e14-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59e14-103">_**上次修改的主题：** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="59e14-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="59e14-104">您可以使用搜索查询的结果为 Lync Server 2013 配置用户。</span><span class="sxs-lookup"><span data-stu-id="59e14-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="59e14-105">可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。</span><span class="sxs-lookup"><span data-stu-id="59e14-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="59e14-106">您可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。</span><span class="sxs-lookup"><span data-stu-id="59e14-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="59e14-107">以下过程介绍如何使用 Lync Server 控制面板搜索用户。</span><span class="sxs-lookup"><span data-stu-id="59e14-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59e14-108">在包括中央林拓扑的环境中，按照用户的电子邮件地址搜索用户时，搜索结果可能不准确。</span><span class="sxs-lookup"><span data-stu-id="59e14-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="59e14-109">可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 <STRONG>Get-CSUser</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="59e14-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="59e14-110">搜索一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="59e14-110">To search for one or more users</span></span>

1.  <span data-ttu-id="59e14-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="59e14-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59e14-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="59e14-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59e14-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="59e14-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59e14-114">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59e14-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="59e14-115">在“搜索用户”\*\*\*\* 框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59e14-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="59e14-116">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="59e14-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="59e14-117">单击“搜索结果”\*\*\*\* 上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59e14-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="59e14-118">通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="59e14-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="59e14-119">在“等于”\*\*\*\* 列表中，单击“等于”\*\*\*\* 或“不等于”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59e14-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="59e14-120">在文本框中，键入要用于筛选搜索结果的搜索条件，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59e14-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="59e14-p105">搜索结果将显示在“搜索结果”\*\*\*\* 下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。</span><span class="sxs-lookup"><span data-stu-id="59e14-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59e14-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59e14-123">See Also</span></span>


[<span data-ttu-id="59e14-124">查看有关为 Lync Server 2013 启用的用户帐户的信息</span><span class="sxs-lookup"><span data-stu-id="59e14-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="59e14-125">为 Lync Server 2013 启用和禁用用户</span><span class="sxs-lookup"><span data-stu-id="59e14-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


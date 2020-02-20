---
title: 将单个用户移动到引导池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7320f55b88786ccf4e1a1a26c28483f3ccbd7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="d76f4-102">将单个用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="d76f4-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d76f4-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d76f4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d76f4-104">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将用户从 Office 通信服务器 2007 R2 池移动到 Lync Server 2013 引导池。</span><span class="sxs-lookup"><span data-stu-id="d76f4-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="d76f4-105">在下面的示例中，在 "注册器池" 列中， \*\* \<office 通信服务器\> \*\*是 office 通信服务器 2007 R2 池，这些用户中的所有六个都连接到此池。</span><span class="sxs-lookup"><span data-stu-id="d76f4-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="d76f4-106">使用以下过程将用户移动到使用 Lync Server 2013 控制面板和 Lync Server 命令行管理程序的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="d76f4-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="d76f4-107">![在 Lync Server 控制面板中搜索 OCS 用户](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server 控制面板中搜索 OCS 用户")</span><span class="sxs-lookup"><span data-stu-id="d76f4-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d76f4-108">使用 Lync Server 2013 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="d76f4-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d76f4-109">使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d76f4-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d76f4-110">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="d76f4-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="d76f4-111">单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d76f4-111">Click **Users**.</span></span>

4.  <span data-ttu-id="d76f4-112">从“用户搜索”\*\*\*\* 选项卡中，单击“搜索”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="d76f4-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="d76f4-113">接下来，单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d76f4-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="d76f4-114">创建一个筛选器，其中的 **Office Communications Server 用户**等于 **True**。</span><span class="sxs-lookup"><span data-stu-id="d76f4-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="d76f4-115">单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。</span><span class="sxs-lookup"><span data-stu-id="d76f4-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="d76f4-116">![在 Lync Server 控制面板中搜索 OCS 用户](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server 控制面板中搜索 OCS 用户")</span><span class="sxs-lookup"><span data-stu-id="d76f4-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="d76f4-117">选择要移到 Lync Server 2013 池的用户。</span><span class="sxs-lookup"><span data-stu-id="d76f4-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d76f4-118">在本示例中，我们将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="d76f4-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="d76f4-119">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d76f4-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="d76f4-120">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="d76f4-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="d76f4-121">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d76f4-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d76f4-122">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d76f4-122">Click **OK**.</span></span>
    
    <span data-ttu-id="d76f4-123">![在 "移动用户" 对话框中设置目标池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在 "移动用户" 对话框中设置目标池")</span><span class="sxs-lookup"><span data-stu-id="d76f4-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="d76f4-124">确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动该用户</span><span class="sxs-lookup"><span data-stu-id="d76f4-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d76f4-125">使用 Lync Server 2013 命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="d76f4-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="d76f4-126">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="d76f4-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d76f4-127">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="d76f4-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="d76f4-128">接下来，在命令行处键入：</span><span class="sxs-lookup"><span data-stu-id="d76f4-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="d76f4-129">**RegistrarPool**标识现在指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="d76f4-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d76f4-130">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="d76f4-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="d76f4-131">![使用标识筛选器的 Get-csuser cmdlet 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "使用标识筛选器的 Get-csuser cmdlet 的输出")</span><span class="sxs-lookup"><span data-stu-id="d76f4-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d76f4-132">有关 <STRONG>Get-CsUser</STRONG> cmdlet 的详细信息，请运行：<STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="d76f4-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


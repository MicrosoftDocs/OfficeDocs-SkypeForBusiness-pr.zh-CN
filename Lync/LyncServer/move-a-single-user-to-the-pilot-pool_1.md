---
title: 将单个用户移动到 "引导" 池
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
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="9284b-102">将单个用户移动到 "引导" 池</span><span class="sxs-lookup"><span data-stu-id="9284b-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9284b-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9284b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9284b-104">你可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将用户从 Office 通信服务器 2007 R2 池移动到 Lync Server 2013 试点项目池中。</span><span class="sxs-lookup"><span data-stu-id="9284b-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="9284b-105">在下面的示例中，在 "注册机构池" 列中， \*\* \<"office 通信服务器\> \*\* " 是 office 通信服务器 2007 R2 池，这些用户中的所有六个用户都连接到该池。</span><span class="sxs-lookup"><span data-stu-id="9284b-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="9284b-106">使用以下过程，使用 Lync Server 2013 控制面板和 Lync Server Management Shell 将用户移动到您的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9284b-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="9284b-107">![在 Lync Server "控制面板" 中搜索 OCS 用户](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server "控制面板" 中搜索 OCS 用户")</span><span class="sxs-lookup"><span data-stu-id="9284b-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="9284b-108">使用 Lync Server 2013 "控制面板" 移动用户</span><span class="sxs-lookup"><span data-stu-id="9284b-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="9284b-109">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="9284b-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="9284b-110">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="9284b-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="9284b-111">单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="9284b-111">Click **Users**.</span></span>

4.  <span data-ttu-id="9284b-112">从 "**用户搜索**" 选项卡中，单击 "**搜索**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="9284b-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="9284b-113">接下来，单击 "**添加筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="9284b-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="9284b-114">创建**Office 通信服务器用户**等于**True**的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9284b-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="9284b-115">单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。</span><span class="sxs-lookup"><span data-stu-id="9284b-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="9284b-116">![在 Lync Server "控制面板" 中搜索 OCS 用户](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server "控制面板" 中搜索 OCS 用户")</span><span class="sxs-lookup"><span data-stu-id="9284b-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="9284b-117">选择要移动到 Lync Server 2013 池的用户。</span><span class="sxs-lookup"><span data-stu-id="9284b-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="9284b-118">在此示例中，将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="9284b-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="9284b-119">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9284b-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="9284b-120">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="9284b-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="9284b-121">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9284b-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="9284b-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9284b-122">Click **OK**.</span></span>
    
    <span data-ttu-id="9284b-123">![在 "移动用户" 对话框中设置目标池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在 "移动用户" 对话框中设置目标池")</span><span class="sxs-lookup"><span data-stu-id="9284b-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="9284b-124">验证用户的**注册池**列现在是否包含 Lync Server 2013 池，这表示用户已成功移动</span><span class="sxs-lookup"><span data-stu-id="9284b-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="9284b-125">使用 Lync Server 2013 命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="9284b-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="9284b-126">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9284b-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="9284b-127">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="9284b-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="9284b-128">接下来，在命令行键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9284b-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="9284b-129">**RegistrarPool**标识现在指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9284b-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="9284b-130">此标识的存在可确认用户已成功移动。</span><span class="sxs-lookup"><span data-stu-id="9284b-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="9284b-131">![Move-csuser cmdlet 和 Identity filter 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Move-csuser cmdlet 和 Identity filter 的输出")</span><span class="sxs-lookup"><span data-stu-id="9284b-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9284b-132">有关<STRONG>move-csuser</STRONG> cmdlet 的详细信息，请运行： <STRONG>Get-help move-csuser-详细</STRONG>信息</span><span class="sxs-lookup"><span data-stu-id="9284b-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


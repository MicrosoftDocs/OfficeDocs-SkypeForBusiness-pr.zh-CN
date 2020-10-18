---
title: Lync Server 2013：创建或修改电话拨入式会议访问号码
description: Lync Server 2013：创建或修改电话拨入式会议访问号码。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577958"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="be0d6-103">在 Lync Server 2013 中创建或修改电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="be0d6-103">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be0d6-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="be0d6-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="be0d6-105">如果要创建或修改电话拨入式会议访问号码，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="be0d6-105">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be0d6-106">在创建新的拨入访问号码之前，必须在与新的拨入访问号码相关联的拨号计划中设置电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="be0d6-106">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="be0d6-107">多个拨号计划可以使用同一个区域。</span><span class="sxs-lookup"><span data-stu-id="be0d6-107">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="be0d6-108">创建或修改拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="be0d6-108">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="be0d6-109">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="be0d6-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="be0d6-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="be0d6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="be0d6-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="be0d6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="be0d6-112">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="be0d6-112">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="be0d6-113">在 " **拨入访问号码** " 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="be0d6-113">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="be0d6-114">单击 " **新建** " 打开 " **新建拨入访问号码**"。</span><span class="sxs-lookup"><span data-stu-id="be0d6-114">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="be0d6-115">单击列表中的某个拨入访问号码，再单击 " **编辑**"，然后单击 " **显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="be0d6-115">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="be0d6-116">使用搜索字段搜索拨入访问号码列表中某一列的内容可能不会产生预期的结果。</span><span class="sxs-lookup"><span data-stu-id="be0d6-116">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="be0d6-117">而是按感兴趣的列对列表进行排序，以标识要查看或更改的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="be0d6-117">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="be0d6-118">在 " **显示号码**" 中，键入公开交换电话网络 (PSTN) 电话用户拨打以加入会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="be0d6-118">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-119">此号码显示在 "会议邀请" 和 "电话拨入式会议设置" 网页上。</span><span class="sxs-lookup"><span data-stu-id="be0d6-119">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="be0d6-120">在 " **显示名称**" 中，键入拨入访问号码的说明。</span><span class="sxs-lookup"><span data-stu-id="be0d6-120">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="be0d6-121">这是与 Lync 搜索结果中的电话拨入访问号码相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="be0d6-121">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-122">当用户呼叫访问号码时，此名称将显示在客户端中。</span><span class="sxs-lookup"><span data-stu-id="be0d6-122">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="be0d6-123">在 " **线路 uri**" 中，使用电话 URI 格式键入拨入访问号码的 e.164 号码，包括号码前面的 + 符号，不包括空格。</span><span class="sxs-lookup"><span data-stu-id="be0d6-123">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="be0d6-124">例如电话： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="be0d6-124">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-125">同一行 URI 不能由其他电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="be0d6-125">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="be0d6-126">在 " **SIP URI**" 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be0d6-126">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="be0d6-127">在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="be0d6-127">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="be0d6-128">此 SIP URI 显示在各种位置，包括但不限于呼叫通知邮件和以前版本的 Communicator 客户端。</span><span class="sxs-lookup"><span data-stu-id="be0d6-128">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="be0d6-129">同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="be0d6-129">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="be0d6-130">在创建访问号码后，不能修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="be0d6-130">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="be0d6-131">更改 SIP URI 的唯一方法是删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="be0d6-131">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="be0d6-132">在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序所在的域。</span><span class="sxs-lookup"><span data-stu-id="be0d6-132">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="be0d6-133">在 " **池**" 中，单击运行支持此拨入访问号码的会议助理实例的池。</span><span class="sxs-lookup"><span data-stu-id="be0d6-133">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-134">如果您在创建访问号码后需要更改池，则必须使用 <STRONG>CsApplicationEndpoint</STRONG> cmdlet 或删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="be0d6-134">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="be0d6-135">在 " **主要语言**" 中，单击针对此拨入访问号码播放提示时使用的语言。</span><span class="sxs-lookup"><span data-stu-id="be0d6-135">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-136">主要语言是会议助理用来应答呼叫的语言。</span><span class="sxs-lookup"><span data-stu-id="be0d6-136">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="be0d6-137">在 "电话拨入式会议设置" 网页上，每个访问电话号码旁都会显示支持的语言。</span><span class="sxs-lookup"><span data-stu-id="be0d6-137">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="be0d6-138"> \(\**辅助语言中的可选)  (最多四)\ \**中，单击 " **添加**"，选择要为呼叫者支持此拨入访问号码的一种或多种其他语言，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="be0d6-138">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0d6-139">您最多可以为每个拨入访问号码选择四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="be0d6-139">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="be0d6-140">用户在拨入会议时，可以在进入会议 ID 之前选择辅助语言。</span><span class="sxs-lookup"><span data-stu-id="be0d6-140">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="be0d6-141">若要为拨入访问号码添加区域，请在 " **关联区域**" 下，单击 " **添加**"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="be0d6-141">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="be0d6-142">若要从拨入访问号码中删除某个区域，请在 " **关联区域**" 下，单击要删除的区域，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="be0d6-142">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="be0d6-143">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="be0d6-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


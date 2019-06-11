---
title: Lync Server 2013：创建或修改电话拨入式会议访问号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="1c913-102">在 Lync Server 2013 中创建或修改电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="1c913-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c913-103">_**主题上次修改时间:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1c913-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1c913-104">如果要创建或修改电话拨入式会议接入号码, 请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="1c913-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c913-105">在创建新的拨入访问号码之前, 必须在与新的拨入接入号码相关联的拨号计划中设置电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="1c913-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="1c913-106">多个拨号计划可以使用同一区域。</span><span class="sxs-lookup"><span data-stu-id="1c913-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="1c913-107">创建或修改拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="1c913-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="1c913-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1c913-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1c913-109">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1c913-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1c913-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1c913-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1c913-111">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c913-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="1c913-112">在“拨入访问号码”\*\*\*\* 页上，执行下列某个操作：</span><span class="sxs-lookup"><span data-stu-id="1c913-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1c913-113">单击“新建”\*\*\*\* 打开“新建拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c913-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="1c913-114">单击列表中的一个拨入访问号码，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c913-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1c913-p103">使用搜索字段搜索拨入访问号码列表中某一列的内容时，可能得不到预期结果。此时，可以按照列的关注度对列表进行排序，以识别要查看或更改的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="1c913-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="1c913-117">在“**显示号码**”中，键入相应的电话号码，以便公用电话交换网 (PSTN) 电话用户可拨打此号码加入会议。</span><span class="sxs-lookup"><span data-stu-id="1c913-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-118">该号码会显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="1c913-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="1c913-119">在“显示名称”\*\*\*\* 中，键入拨入访问号码的说明。</span><span class="sxs-lookup"><span data-stu-id="1c913-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="1c913-120">这是与 Lync 搜索结果中的拨入访问号码相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="1c913-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-121">用户呼叫访问号码时，此名称会显示在客户端上。</span><span class="sxs-lookup"><span data-stu-id="1c913-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="1c913-p105">在“线路 URI”\*\*\*\* 中，使用 TEL URI 格式键入拨入访问号码的 E.164 号码，请在此号码前添加 + 符号，不要添加空格。例如：tel:+14255550200。</span><span class="sxs-lookup"><span data-stu-id="1c913-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-124">同一线路 URI 不能由其他电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="1c913-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="1c913-125">在“SIP URI”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1c913-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="1c913-126">在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="1c913-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="1c913-127">SIP URI 显示在不同的位置, 其中包括但不限于呼叫通知消息和以前版本的 Communicator 客户端。</span><span class="sxs-lookup"><span data-stu-id="1c913-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1c913-p107">同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。创建访问号码之后，将不能修改 SIP URI。更改 SIP URI 的唯一方法是删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="1c913-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="1c913-131">在下拉列表框中, 单击支持此拨入访问号码的会议助理应用程序所在的域。</span><span class="sxs-lookup"><span data-stu-id="1c913-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="1c913-132">在“池”\*\*\*\* 中，单击运行支持此拨入访问号码的会议助理实例的池。</span><span class="sxs-lookup"><span data-stu-id="1c913-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-133">创建访问号码后，如果需要更改池，必须使用  <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet 或删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="1c913-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="1c913-134">在“主要语言”\*\*\*\* 中，单击针对此拨入访问号码播放提示时使用的语言。</span><span class="sxs-lookup"><span data-stu-id="1c913-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-p108">主要语言是会议助理应答呼叫时使用的语言。支持的语言显示在电话拨入式会议设置网页上的每个访问电话号码旁边。</span><span class="sxs-lookup"><span data-stu-id="1c913-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="1c913-137">（可选）在“辅助语言（最多 4 个）”\*\*\*\* 中，单击“添加”\*\*\*\*，选择一个或多个要为此拨入访问号码的呼叫者提供支持的其他语言，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c913-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c913-p109">最多可以为每个拨入访问号码选择四种辅助语言。用户通过电话拨入加入会议时，在输入会议 ID 之前可以选择一种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="1c913-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="1c913-140">若要为拨入访问号码添加区域, 请在 "**关联区域**" 下, 单击 "**添加**", 单击与此拨入访问号码的拨号计划相关联的一个或多个区域, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1c913-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="1c913-141">要从拨入访问号码中删除某个区域，请在“关联区域”\*\*\*\* 下，单击要删除的区域，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c913-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="1c913-142">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1c913-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


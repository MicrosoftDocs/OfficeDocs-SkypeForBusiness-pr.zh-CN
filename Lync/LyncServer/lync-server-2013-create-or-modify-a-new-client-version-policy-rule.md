---
title: 'Lync Server 2013: 创建或修改新的客户端版本策略规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="f367b-102">在 Lync Server 2013 中创建或修改新的客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="f367b-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f367b-103">_**主题上次修改时间:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="f367b-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="f367b-104">客户端版本策略规则定义当用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="f367b-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="f367b-105">你可以从 Lync Server 2013 控制面板创建或修改客户端版本策略的单个规则。</span><span class="sxs-lookup"><span data-stu-id="f367b-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f367b-106">规则按优先级顺序列出。</span><span class="sxs-lookup"><span data-stu-id="f367b-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="f367b-107">例如, 如果你有允许运行版本1.5 的客户端连接的规则, 然后是阻止运行2.0 之前的版本的客户端的规则, 则将优先使用运行版本1.5 的客户端, 并且允许运行版本的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="f367b-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="f367b-108">通过 Lync Server "控制面板" 创建或修改客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="f367b-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f367b-109">使用 Lync Server "控制面板"[在 Lync server 2013 中创建或修改新的客户端版本策略](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="f367b-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="f367b-110">在 "**编辑客户端版本策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="f367b-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f367b-111">单击 "**新建**" 以创建新的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="f367b-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="f367b-112">单击列表中某个已定义的客户端类型, 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f367b-113">可以使用通配符指示客户端类型。</span><span class="sxs-lookup"><span data-stu-id="f367b-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="f367b-114">在 "**用户代理**" 中, 选择一种客户端类型。</span><span class="sxs-lookup"><span data-stu-id="f367b-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="f367b-115">在 "**版本号**" 下, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="f367b-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="f367b-116">在 "**主要版本**" 中, 键入与客户端的主要版本相对应的数字。</span><span class="sxs-lookup"><span data-stu-id="f367b-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="f367b-117">在 "**次要版本**" 中, 键入与客户端的次要版本相对应的数字。</span><span class="sxs-lookup"><span data-stu-id="f367b-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="f367b-118">在 "**生成**" 中, 键入与客户端的主要和次要版本相对应的数字。</span><span class="sxs-lookup"><span data-stu-id="f367b-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="f367b-119">在 "**更新**" 中, 键入与客户端更新的版本相对应的数字。</span><span class="sxs-lookup"><span data-stu-id="f367b-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f367b-120">可以使用通配符指示客户端版本号。</span><span class="sxs-lookup"><span data-stu-id="f367b-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="f367b-121">若要为您在前面的步骤中指定的客户端版本指定匹配操作, 请在 "**比较" 操作**中, 单击下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="f367b-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="f367b-122">**相同**</span><span class="sxs-lookup"><span data-stu-id="f367b-122">**Same as**</span></span>
    
      - <span data-ttu-id="f367b-123">**不是**</span><span class="sxs-lookup"><span data-stu-id="f367b-123">**Is not**</span></span>
    
      - <span data-ttu-id="f367b-124">**更高**</span><span class="sxs-lookup"><span data-stu-id="f367b-124">**Newer than**</span></span>
    
      - <span data-ttu-id="f367b-125">**更高或相同**</span><span class="sxs-lookup"><span data-stu-id="f367b-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="f367b-126">**更低**</span><span class="sxs-lookup"><span data-stu-id="f367b-126">**Older than**</span></span>
    
      - <span data-ttu-id="f367b-127">**更低或相同**</span><span class="sxs-lookup"><span data-stu-id="f367b-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="f367b-128">若要指定在满足前面步骤中的条件时要执行的操作, 请单击下列**操作**之一:</span><span class="sxs-lookup"><span data-stu-id="f367b-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="f367b-129">要允许客户登录, 请单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="f367b-130">若要允许客户登录并接收来自 Windows Server 更新服务或 Microsoft 更新的更新, 请单击 "**允许和升级**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="f367b-131">仅当选择了 "用户代理**OC** " 时, 此操作才可用。</span><span class="sxs-lookup"><span data-stu-id="f367b-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f367b-132">选择此操作会导致在用户下次登录 Lync 2013 时显示通知。</span><span class="sxs-lookup"><span data-stu-id="f367b-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="f367b-133">该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="f367b-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="f367b-134">为了避免混淆，您只应在更新可用后选择此操作。</span><span class="sxs-lookup"><span data-stu-id="f367b-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="f367b-135">若要允许客户登录并显示有关从何处下载另一个客户端版本的消息, 请单击 "**允许使用 URL**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="f367b-136">在此过程后面的部分中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="f367b-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="f367b-137">若要阻止客户端登录, 请单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="f367b-138">若要阻止客户端登录并允许客户从 Windows Server 更新服务或 Microsoft 更新接收更新, 请单击 "**阻止和升级**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="f367b-139">仅当选择了 "用户代理**OC** " 时, 此操作才可用。</span><span class="sxs-lookup"><span data-stu-id="f367b-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="f367b-140">若要阻止客户登录并显示有关从何处下载另一个客户端版本的消息, 请单击 "**带 URL 阻止**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="f367b-141">在此过程后面的部分中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="f367b-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="f367b-142">可选如果在上一步中单击 "**允许 url**或带 Url 的**阻止**", 请键入要包含在**url**中的消息中的客户端下载 URL。</span><span class="sxs-lookup"><span data-stu-id="f367b-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="f367b-143">单击 **"确定**", 然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="f367b-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


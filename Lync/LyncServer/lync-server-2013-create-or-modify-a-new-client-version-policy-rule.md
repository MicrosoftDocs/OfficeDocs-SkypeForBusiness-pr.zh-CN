---
title: Lync Server 2013：创建或修改新的客户端版本策略规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fec7930b8ebd7aa6bb7f50c71a1f163cdb83f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="11ff2-102">在 Lync Server 2013 中创建或修改新的客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="11ff2-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ff2-103">_**上次修改的主题：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="11ff2-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="11ff2-104">客户端版本策略规则定义当用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="11ff2-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="11ff2-105">您可以从 Lync Server 2013 控制面板中创建或修改客户端版本策略的各个规则。</span><span class="sxs-lookup"><span data-stu-id="11ff2-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11ff2-106">规则按优先级顺序列出。</span><span class="sxs-lookup"><span data-stu-id="11ff2-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="11ff2-107">例如，如果您有一个允许运行版本1.5 的客户端进行连接的规则，然后是一个规则，该规则会阻止运行低于2.0 的版本的客户端，则第一个规则优先，并且允许运行版本1.5 的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="11ff2-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="11ff2-108">使用 Lync Server 控制面板创建或修改客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="11ff2-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="11ff2-109">在 Lync server 2013 with Lync Server 控制面板[中创建或修改新的客户端版本策略](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="11ff2-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="11ff2-110">在 "**编辑客户端版本策略**" 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="11ff2-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="11ff2-111">单击“新建”\*\*\*\* 创建新的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="11ff2-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="11ff2-112">单击列表中已定义的客户端类型之一，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11ff2-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11ff2-113">可以使用通配符来指示客户端类型。</span><span class="sxs-lookup"><span data-stu-id="11ff2-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="11ff2-114">在“用户代理”\*\*\*\* 中，选择客户端类型。</span><span class="sxs-lookup"><span data-stu-id="11ff2-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="11ff2-115">在“版本号”\*\*\*\* 下，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="11ff2-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="11ff2-116">在“主版本”\*\*\*\* 中，键入与客户端的主版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="11ff2-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="11ff2-117">在“次版本”\*\*\*\* 中，键入与客户端的次版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="11ff2-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="11ff2-118">在“内部版本”\*\*\*\* 中，键入与客户端的主版本和次版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="11ff2-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="11ff2-119">在“更新”\*\*\*\* 中，键入与客户端的更新版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="11ff2-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11ff2-120">可以使用通配符来指示客户端版本号。</span><span class="sxs-lookup"><span data-stu-id="11ff2-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="11ff2-121">要为上述步骤中指定的客户端版本指定匹配操作，请在“比较操作”\*\*\*\* 中，单击下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="11ff2-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="11ff2-122">**相同**</span><span class="sxs-lookup"><span data-stu-id="11ff2-122">**Same as**</span></span>
    
      - <span data-ttu-id="11ff2-123">**不是**</span><span class="sxs-lookup"><span data-stu-id="11ff2-123">**Is not**</span></span>
    
      - <span data-ttu-id="11ff2-124">**更高**</span><span class="sxs-lookup"><span data-stu-id="11ff2-124">**Newer than**</span></span>
    
      - <span data-ttu-id="11ff2-125">**更高或相同**</span><span class="sxs-lookup"><span data-stu-id="11ff2-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="11ff2-126">**更低**</span><span class="sxs-lookup"><span data-stu-id="11ff2-126">**Older than**</span></span>
    
      - <span data-ttu-id="11ff2-127">**更低或相同**</span><span class="sxs-lookup"><span data-stu-id="11ff2-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="11ff2-128">要指定在满足上述步骤中的条件时执行的操作，请在“操作”\*\*\*\* 中，单击下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="11ff2-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="11ff2-129">要允许客户端登录，请单击“允许”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11ff2-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="11ff2-p103">要允许客户端登录并接收来自 Windows Server 更新服务或 Microsoft Update 的更新，请单击“允许并升级”\*\*\*\*。仅当选中用户代理“OC”\*\*\*\* 时，才能进行此操作。</span><span class="sxs-lookup"><span data-stu-id="11ff2-p103">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="11ff2-132">如果选择此操作，则会在用户下一次登录 Lync 2013 时显示通知。</span><span class="sxs-lookup"><span data-stu-id="11ff2-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="11ff2-133">该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="11ff2-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="11ff2-134">为了避免混淆，您只应在更新可用后选择此操作。</span><span class="sxs-lookup"><span data-stu-id="11ff2-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="11ff2-p105">要允许客户端登录并显示有关下载其他客户端版本的位置的消息，请单击“使用 URL 允许”\*\*\*\*。需要在此过程的后面阶段指定 URL。</span><span class="sxs-lookup"><span data-stu-id="11ff2-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="11ff2-137">要阻止客户端登录，请单击“阻止”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11ff2-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="11ff2-p106">要阻止客户端登录并允许客户端接收来自 Windows Server 更新服务或 Microsoft Update 的更新，请单击“阻止并升级”\*\*\*\*。仅当选中用户代理“OC”\*\*\*\* 时，才能进行此操作。</span><span class="sxs-lookup"><span data-stu-id="11ff2-p106">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="11ff2-p107">要阻止客户端登录并显示有关下载其他客户端版本的位置的消息，请单击“使用 URL 阻止”\*\*\*\*。需要在此过程的后面阶段指定 URL。</span><span class="sxs-lookup"><span data-stu-id="11ff2-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="11ff2-142">（可选）如果在上一步中单击“使用 URL 允许”\*\*\*\* 或“使用 URL 阻止”\*\*\*\*，则在“URL”\*\*\*\* 中键入要包含在消息中的客户端下载 URL。</span><span class="sxs-lookup"><span data-stu-id="11ff2-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="11ff2-143">单击“确定”\*\*\*\*，然后单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11ff2-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


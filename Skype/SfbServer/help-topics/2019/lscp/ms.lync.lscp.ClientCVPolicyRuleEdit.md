---
title: 客户端版本规则
ms.reviewer: ''
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。
ms.openlocfilehash: d1de600a3907d3e981bb1f706cdedbff05e965f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215897"
---
# <a name="client-version-rule"></a><span data-ttu-id="836e1-104">客户端版本规则</span><span class="sxs-lookup"><span data-stu-id="836e1-104">Client Version Rule</span></span>

<span data-ttu-id="836e1-p102">客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="836e1-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="836e1-107">Tasks you can perform</span></span>

<span data-ttu-id="836e1-108">您可以在“**新建客户端版本配置**”或“**编辑客户端版本配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="836e1-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="836e1-109">向客户端版本策略添加新规则。</span><span class="sxs-lookup"><span data-stu-id="836e1-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="836e1-110">修改构成现有客户端版本策略的规则</span><span class="sxs-lookup"><span data-stu-id="836e1-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="836e1-111">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="836e1-111">UI Reference</span></span>

<span data-ttu-id="836e1-112">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="836e1-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="836e1-113">**用户代理**您可以从列表中选择客户端类型。</span><span class="sxs-lookup"><span data-stu-id="836e1-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="836e1-114">下表定义了用户代理代码。</span><span class="sxs-lookup"><span data-stu-id="836e1-114">The following table defines user agent codes.</span></span> <span data-ttu-id="836e1-115">此列表包含旧客户端类型，其中一些不再受支持。</span><span class="sxs-lookup"><span data-stu-id="836e1-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="836e1-116">**客户端名称**</span><span class="sxs-lookup"><span data-stu-id="836e1-116">**Client Name**</span></span>|<span data-ttu-id="836e1-117">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="836e1-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="836e1-118">Lync 2013，Lync 2010，Office Communicator</span><span class="sxs-lookup"><span data-stu-id="836e1-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="836e1-119">OC</span><span class="sxs-lookup"><span data-stu-id="836e1-119">OC</span></span>  <br/> |
|<span data-ttu-id="836e1-120">Lync Web App 中，Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="836e1-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="836e1-121">CWA</span><span class="sxs-lookup"><span data-stu-id="836e1-121">CWA</span></span>  <br/> |
|<span data-ttu-id="836e1-122">Lync Phone Edition，Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="836e1-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="836e1-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="836e1-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="836e1-124">Communicator Phone Edition 平台</span><span class="sxs-lookup"><span data-stu-id="836e1-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="836e1-125">CPE</span><span class="sxs-lookup"><span data-stu-id="836e1-125">CPE</span></span>  <br/> |
|<span data-ttu-id="836e1-126">统一通信平台</span><span class="sxs-lookup"><span data-stu-id="836e1-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="836e1-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="836e1-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="836e1-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="836e1-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="836e1-129">AOC</span><span class="sxs-lookup"><span data-stu-id="836e1-129">AOC</span></span>  <br/> |
|<span data-ttu-id="836e1-130">Live Meeting 外接程序</span><span class="sxs-lookup"><span data-stu-id="836e1-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="836e1-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="836e1-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="836e1-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="836e1-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="836e1-133">LMC</span><span class="sxs-lookup"><span data-stu-id="836e1-133">LMC</span></span>  <br/> |
|<span data-ttu-id="836e1-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="836e1-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="836e1-135">WM</span><span class="sxs-lookup"><span data-stu-id="836e1-135">WM</span></span>  <br/> |
|<span data-ttu-id="836e1-136">实时通信客户端</span><span class="sxs-lookup"><span data-stu-id="836e1-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="836e1-137">RTC</span><span class="sxs-lookup"><span data-stu-id="836e1-137">RTC</span></span>  <br/> |
|<span data-ttu-id="836e1-138">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="836e1-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="836e1-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="836e1-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="836e1-140">Lync 2010 for iPhone</span><span class="sxs-lookup"><span data-stu-id="836e1-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="836e1-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="836e1-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="836e1-142">Lync 2010 for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="836e1-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="836e1-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="836e1-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="836e1-144">Lync 2010 for Nokia</span><span class="sxs-lookup"><span data-stu-id="836e1-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="836e1-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="836e1-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="836e1-146">Lync 2010 for Android</span><span class="sxs-lookup"><span data-stu-id="836e1-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="836e1-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="836e1-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="836e1-148">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="836e1-148">Mobility service</span></span>  <br/> |<span data-ttu-id="836e1-149">McxService</span><span class="sxs-lookup"><span data-stu-id="836e1-149">McxService</span></span>  <br/> |

- <span data-ttu-id="836e1-150">**版本号**您可以指定以下字段的版本号，或使用通配符来指示客户端版本号。</span><span class="sxs-lookup"><span data-stu-id="836e1-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="836e1-151">**主要版本**指定对应于主要客户端版本的号码。</span><span class="sxs-lookup"><span data-stu-id="836e1-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="836e1-152">**次要版本**指定与客户端的次版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="836e1-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="836e1-153">**生成**指定与客户端的主版本和次版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="836e1-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="836e1-154">**更新**指定与客户端的更新版本相对应的版本号。</span><span class="sxs-lookup"><span data-stu-id="836e1-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="836e1-155">**比较操作**您可以指定您在前面的步骤中指定的客户端版本匹配的操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="836e1-156">以下操作有：</span><span class="sxs-lookup"><span data-stu-id="836e1-156">The following operations are available:</span></span>

  - <span data-ttu-id="836e1-157">**相同**</span><span class="sxs-lookup"><span data-stu-id="836e1-157">**Same as**</span></span>

  - <span data-ttu-id="836e1-158">**不是**</span><span class="sxs-lookup"><span data-stu-id="836e1-158">**Is not**</span></span>

  - <span data-ttu-id="836e1-159">**更高**</span><span class="sxs-lookup"><span data-stu-id="836e1-159">**Newer than**</span></span>

  - <span data-ttu-id="836e1-160">**更高或相同**</span><span class="sxs-lookup"><span data-stu-id="836e1-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="836e1-161">**更低**</span><span class="sxs-lookup"><span data-stu-id="836e1-161">**Older than**</span></span>

  - <span data-ttu-id="836e1-162">**更低或相同**</span><span class="sxs-lookup"><span data-stu-id="836e1-162">**Older than or same as**</span></span>

- <span data-ttu-id="836e1-163">**操作**您可以指定要满足上述步骤中的条件时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="836e1-164">以下操作有：</span><span class="sxs-lookup"><span data-stu-id="836e1-164">The following actions are available:</span></span>

  - <span data-ttu-id="836e1-165">**允许**允许客户端登录。</span><span class="sxs-lookup"><span data-stu-id="836e1-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="836e1-166">**允许并升级**允许客户端登录和 Windows Server 更新服务或 Microsoft Update 接收更新。</span><span class="sxs-lookup"><span data-stu-id="836e1-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="836e1-167">仅当选择用户代理**OC**时，才可使用此操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="836e1-168">选择此操作将导致通知显示在用户下次登录到 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="836e1-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="836e1-169">该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="836e1-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="836e1-170">为了避免混淆，您只应在更新可用后选择此操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="836e1-171">**使用 URL 允许**允许客户端登录，并显示一条有关在何处下载另一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="836e1-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="836e1-172">可以在“**URL**”字段中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="836e1-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="836e1-173">**阻止**阻止客户端登录。</span><span class="sxs-lookup"><span data-stu-id="836e1-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="836e1-174">**块和升级**阻止客户端登录，并允许客户端从 Windows Server 更新服务或 Microsoft Update 接收更新。</span><span class="sxs-lookup"><span data-stu-id="836e1-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="836e1-175">仅当选择用户代理**OC**时，才可使用此操作。</span><span class="sxs-lookup"><span data-stu-id="836e1-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="836e1-p110">**使用 URL 阻止**   阻止客户端登录并显示有关下载其他客户端版本的位置的消息。可以在“**URL**”字段中指定 URL。</span><span class="sxs-lookup"><span data-stu-id="836e1-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="836e1-178">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[客户端互操作性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="836e1-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="836e1-179">有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="836e1-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>


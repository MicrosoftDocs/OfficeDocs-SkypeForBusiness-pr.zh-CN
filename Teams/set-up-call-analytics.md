---
title: 设置通话分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 设置和使用调用分析确定并解决 Skype 的业务和 Microsoft 团队呼叫质量问题。
ms.openlocfilehash: ebd5ec0ea60a59e50c3ce7137f518d9a596074a5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204809"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="e65c3-103">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="e65c3-103">Set up Call Analytics</span></span>

<span data-ttu-id="e65c3-104">为工作组或业务联机管理 Skype，您可以使用调用分析解决 for Business 的 Skype 和 Microsoft 团队呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="e65c3-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="e65c3-105">您可能会发现有用设置呼叫分析中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="e65c3-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="e65c3-106">设置让其他人员，如技术支持代理，请使用调用分析的权限，但禁止访问的 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="e65c3-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="e65c3-107">上载.tsv 或.csv 数据文件，可以将构建、 网站和租户信息添加到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="e65c3-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="e65c3-108">**调用分析现已在 Microsoft 团队管理中心**。</span><span class="sxs-lookup"><span data-stu-id="e65c3-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="e65c3-109">若要查看所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过查看用户配置文件页上，通过执行下列选项之一来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e65c3-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="e65c3-110">搜索仪表板中的用户。</span><span class="sxs-lookup"><span data-stu-id="e65c3-110">Search for the user from the dashboard.</span></span>
  
   ![屏幕截图的用户搜索仪表板上](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="e65c3-112">左侧导航窗格中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="e65c3-112">Select **Users** in the left navigation.</span></span>

   ![左侧导航的屏幕截图](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="e65c3-114">设置呼叫分析的权限</span><span class="sxs-lookup"><span data-stu-id="e65c3-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="e65c3-115">作为管理员，必须调用分析的所有功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="e65c3-115">As the admin, you have full access to all the features of Call Analytics.</span></span> <span data-ttu-id="e65c3-116">此外，您可以分配支持人员的 Azure Active Directory 角色。</span><span class="sxs-lookup"><span data-stu-id="e65c3-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="e65c3-117">团队 communications 支持专家角色分配用户应具有有限的呼叫分析视图。</span><span class="sxs-lookup"><span data-stu-id="e65c3-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="e65c3-118">团队 communications 支持工程师角色分配用户需要访问呼叫分析的全部功能。</span><span class="sxs-lookup"><span data-stu-id="e65c3-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="e65c3-119">这两个权限级别防止对其余的 Microsoft 团队管理中心的访问。</span><span class="sxs-lookup"><span data-stu-id="e65c3-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="e65c3-120">Communications 支持专家角色等同于第 1 层支持它等效于第 2 层支持 communications 支持工程师角色。</span><span class="sxs-lookup"><span data-stu-id="e65c3-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="e65c3-121">有关团队管理员角色的详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e65c3-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="e65c3-122">Communications 支持专家处理基本呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="e65c3-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="e65c3-123">他们不调查与会议的问题。</span><span class="sxs-lookup"><span data-stu-id="e65c3-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="e65c3-124">相反，它们收集相关的信息，然后升级到 communications 支持工程师。</span><span class="sxs-lookup"><span data-stu-id="e65c3-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="e65c3-125">Communications 支持工程师请参阅详细的呼叫日志的已隐藏从通信支持专家的信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="e65c3-126">下表提供的信息概述了对通信支持专家和通信支持工程师使用调用分析时。</span><span class="sxs-lookup"><span data-stu-id="e65c3-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="e65c3-127">**活动**</span><span class="sxs-lookup"><span data-stu-id="e65c3-127">**Activity**</span></span>|<span data-ttu-id="e65c3-128">**呼叫分析中的信息**</span><span class="sxs-lookup"><span data-stu-id="e65c3-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="e65c3-129">**哪些 communications 支持专业人员可以看到**</span><span class="sxs-lookup"><span data-stu-id="e65c3-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="e65c3-130">**哪些 communications 支持工程师可以看到**</span><span class="sxs-lookup"><span data-stu-id="e65c3-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e65c3-131">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="e65c3-131">**Calls**</span></span> <br/> |<span data-ttu-id="e65c3-132">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="e65c3-132">Caller name</span></span>  <br/> |<span data-ttu-id="e65c3-133">仅为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e65c3-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="e65c3-134">用户名。</span><span class="sxs-lookup"><span data-stu-id="e65c3-134">User name.</span></span>  <br/> |
||<span data-ttu-id="e65c3-135">收件人的姓名</span><span class="sxs-lookup"><span data-stu-id="e65c3-135">Recipient name</span></span>  <br/> |<span data-ttu-id="e65c3-136">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="e65c3-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="e65c3-137">收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="e65c3-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="e65c3-138">呼叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="e65c3-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="e65c3-139">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="e65c3-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e65c3-140">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e65c3-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="e65c3-141">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="e65c3-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e65c3-142">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e65c3-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="e65c3-143">收件人的电话号码</span><span class="sxs-lookup"><span data-stu-id="e65c3-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="e65c3-144">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="e65c3-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e65c3-145">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e65c3-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="e65c3-146">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="e65c3-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="e65c3-147">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e65c3-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="e65c3-148">**呼叫详细信息** > **高级**选项卡</span><span class="sxs-lookup"><span data-stu-id="e65c3-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="e65c3-149">不显示的信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="e65c3-150">所示，如设备名称、 IP 地址、 子网映射和更多的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="e65c3-151">**呼叫详细信息** > **高级** > **调试**选项卡</span><span class="sxs-lookup"><span data-stu-id="e65c3-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="e65c3-152">不显示的信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="e65c3-153">所示，如 DNS 后缀和 SSID 的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="e65c3-154">**会议**</span><span class="sxs-lookup"><span data-stu-id="e65c3-154">**Meetings**</span></span> <br/> |<span data-ttu-id="e65c3-155">参与者姓名</span><span class="sxs-lookup"><span data-stu-id="e65c3-155">Participant names</span></span>  <br/> |<span data-ttu-id="e65c3-156">仅为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e65c3-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="e65c3-157">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="e65c3-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="e65c3-158">显示所有名称。</span><span class="sxs-lookup"><span data-stu-id="e65c3-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="e65c3-159">参与者计数</span><span class="sxs-lookup"><span data-stu-id="e65c3-159">Participant count</span></span>  <br/> |<span data-ttu-id="e65c3-160">参与者数目。</span><span class="sxs-lookup"><span data-stu-id="e65c3-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="e65c3-161">参与者数目。</span><span class="sxs-lookup"><span data-stu-id="e65c3-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="e65c3-162">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="e65c3-162">Session details</span></span>  <br/> |<span data-ttu-id="e65c3-163">显示例外的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-163">Session details shown with exceptions.</span></span> <span data-ttu-id="e65c3-164">仅为其显示搜索的代理的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e65c3-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="e65c3-165">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="e65c3-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="e65c3-166">最后三个星号符号模糊处理的电话号码的数字。</span><span class="sxs-lookup"><span data-stu-id="e65c3-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="e65c3-167">显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-167">Session details shown.</span></span> <span data-ttu-id="e65c3-168">用户的用户名和显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-168">User names and session details shown.</span></span> <span data-ttu-id="e65c3-169">最后三个星号符号模糊处理的电话号码的数字。</span><span class="sxs-lookup"><span data-stu-id="e65c3-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="e65c3-170">设置通过分配管理员角色的权限</span><span class="sxs-lookup"><span data-stu-id="e65c3-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="e65c3-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="e65c3-171"></span></span>

<span data-ttu-id="e65c3-172">若要了解如何为 Azure Active Directory 中的管理角色分配，请参阅[在 Azure Active Directory 中的视图和分配角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="e65c3-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="e65c3-173">上载.tsv 或.csv 文件添加生成，网站和租户信息</span><span class="sxs-lookup"><span data-stu-id="e65c3-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="e65c3-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="e65c3-174"></span></span>

<span data-ttu-id="e65c3-175">可以通过上载.csv 或.tsv 文件构建、 网站和租户信息添加到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="e65c3-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="e65c3-176">与所有此类信息呼叫分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="e65c3-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="e65c3-177">您或帮助台代理可能会发现有用帮助呼叫问题中的专色趋势的此信息。</span><span class="sxs-lookup"><span data-stu-id="e65c3-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="e65c3-178">例如，为什么很多用户在同一构建具有类似呼叫质量问题？</span><span class="sxs-lookup"><span data-stu-id="e65c3-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="e65c3-179">如果您是团队和 Skype 对于业务管理员，您可以使用团队 & Skype 从现有数据文件对于业务呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="e65c3-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="e65c3-180">首先，呼叫质量仪表板中下载文件，然后将其上载到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="e65c3-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="e65c3-181">若要下载现有数据文件，转到**Microsoft 团队管理中心** > **呼叫质量仪表板** > **立即上载**。</span><span class="sxs-lookup"><span data-stu-id="e65c3-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="e65c3-182">在**我上载**列表中，单击所需的文件旁边的**下载**。</span><span class="sxs-lookup"><span data-stu-id="e65c3-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="e65c3-183">若要上载的新文件，转到**Microsoft 团队管理中心** > **位置**，然后选择**上载位置数据**或**替换位置数据**。</span><span class="sxs-lookup"><span data-stu-id="e65c3-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="e65c3-184">如果您正在从头创建.tsv 或.csv 文件，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。</span><span class="sxs-lookup"><span data-stu-id="e65c3-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e65c3-185">相关主题</span><span class="sxs-lookup"><span data-stu-id="e65c3-185">Related topics</span></span>
<span data-ttu-id="e65c3-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="e65c3-186"></span></span>

[<span data-ttu-id="e65c3-187">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="e65c3-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="e65c3-188">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="e65c3-188">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 

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
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 设置和使用呼叫分析来识别 Skype for Business 和 Microsoft 团队通话质量问题，并对其进行故障排除。
ms.openlocfilehash: 7a91bc0d8503d313ae3b3dfa7ddd32b6a8c5207a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571245"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="b7b8e-103">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="b7b8e-103">Set up Call Analytics</span></span>

<span data-ttu-id="b7b8e-104">作为团队或 Skype for Business Online 管理员，您可以使用呼叫分析对 Skype for Business 和 Microsoft 团队通话质量和连接问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="b7b8e-105">你可能会发现在调用分析中设置以下功能非常有用：</span><span class="sxs-lookup"><span data-stu-id="b7b8e-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="b7b8e-106">设置允许其他人员（如帮助台代理）使用呼叫分析的权限，但阻止他们访问 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="b7b8e-107">通过上载 tsv 或 .csv 数据文件，将生成、网站和租户信息添加到调用分析。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="b7b8e-108">**"呼叫分析" 现在可在 Microsoft 团队管理中心中使用**。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="b7b8e-109">若要查看用户的所有呼叫信息和数据，请使用 "**通话记录**" 选项卡。你可以通过执行下列操作之一，通过查看用户的配置文件页面来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b7b8e-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="b7b8e-110">从仪表板中搜索用户。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-110">Search for the user from the dashboard.</span></span>
  
   ![仪表板上的用户搜索的屏幕截图](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="b7b8e-112">在左侧导航中选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-112">Select **Users** in the left navigation.</span></span>

   ![左侧导航的屏幕截图](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="b7b8e-114">设置呼叫分析权限</span><span class="sxs-lookup"><span data-stu-id="b7b8e-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="b7b8e-115">作为管理员，你拥有对呼叫分析的所有功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-115">As the admin, you have full access to all the features of Call Analytics.</span></span> <span data-ttu-id="b7b8e-116">此外，你可以将 Azure Active Directory 角色分配给支持人员。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="b7b8e-117">将团队通信支持专家角色分配给应具有有限视图的调用分析的用户。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="b7b8e-118">将团队通信支持工程师角色分配给需要访问调用分析的完整功能的用户。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="b7b8e-119">这两个权限级别阻止访问 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="b7b8e-120">通信支持专家角色等效于第1层支持，而通信支持工程师角色等效于第2层支持。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="b7b8e-121">有关团队管理员角色的详细信息，请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="b7b8e-122">通信支持专家处理基本的通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="b7b8e-123">他们不会调查会议问题。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="b7b8e-124">而是收集相关信息，然后升级到通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="b7b8e-125">通信支持工程师查看有关通信支持专家隐藏的详细通话记录中的信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="b7b8e-126">下表简要介绍了在使用呼叫分析时，通信支持专家和通信支持工程师可使用的信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="b7b8e-127">**活动**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-127">**Activity**</span></span>|<span data-ttu-id="b7b8e-128">**通话分析中的信息**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="b7b8e-129">**通信支持专家可以看到的内容**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="b7b8e-130">**通信支持工程师看到的内容**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7b8e-131">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-131">**Calls**</span></span> <br/> |<span data-ttu-id="b7b8e-132">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="b7b8e-132">Caller name</span></span>  <br/> |<span data-ttu-id="b7b8e-133">仅限代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="b7b8e-134">用户名。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-134">User name.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-135">收件人姓名</span><span class="sxs-lookup"><span data-stu-id="b7b8e-135">Recipient name</span></span>  <br/> |<span data-ttu-id="b7b8e-136">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="b7b8e-137">收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-138">呼叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="b7b8e-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="b7b8e-139">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b7b8e-140">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="b7b8e-141">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b7b8e-142">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-143">收件人电话号码</span><span class="sxs-lookup"><span data-stu-id="b7b8e-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="b7b8e-144">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b7b8e-145">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="b7b8e-146">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b7b8e-147">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-148">**"呼叫详细信息** > "**高级**选项卡</span><span class="sxs-lookup"><span data-stu-id="b7b8e-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="b7b8e-149">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="b7b8e-150">显示所有详细信息，如设备名称、IP 地址、子网映射等。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-151">**"呼叫详细信息** > "**高级** > "**调试**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b7b8e-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="b7b8e-152">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="b7b8e-153">显示所有详细信息，如 DNS 后缀和 SSID。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="b7b8e-154">**会议**</span><span class="sxs-lookup"><span data-stu-id="b7b8e-154">**Meetings**</span></span> <br/> |<span data-ttu-id="b7b8e-155">参与者姓名</span><span class="sxs-lookup"><span data-stu-id="b7b8e-155">Participant names</span></span>  <br/> |<span data-ttu-id="b7b8e-156">仅限代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="b7b8e-157">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="b7b8e-158">显示所有名称。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-159">参与者计数</span><span class="sxs-lookup"><span data-stu-id="b7b8e-159">Participant count</span></span>  <br/> |<span data-ttu-id="b7b8e-160">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="b7b8e-161">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="b7b8e-162">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="b7b8e-162">Session details</span></span>  <br/> |<span data-ttu-id="b7b8e-163">与异常一起显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-163">Session details shown with exceptions.</span></span> <span data-ttu-id="b7b8e-164">仅显示对其进行代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="b7b8e-165">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="b7b8e-166">用星号符号进行混淆的电话号码的最后三位数字。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="b7b8e-167">显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-167">Session details shown.</span></span> <span data-ttu-id="b7b8e-168">显示的用户名和会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-168">User names and session details shown.</span></span> <span data-ttu-id="b7b8e-169">用星号符号进行混淆的电话号码的最后三位数字。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="b7b8e-170">通过分配管理员角色设置权限</span><span class="sxs-lookup"><span data-stu-id="b7b8e-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="b7b8e-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="b7b8e-171"></span></span>

<span data-ttu-id="b7b8e-172">若要了解如何在 Azure Active Directory 中分配管理角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="b7b8e-173">上载 tsv 或 .csv 文件以添加建筑物、网站和租户信息</span><span class="sxs-lookup"><span data-stu-id="b7b8e-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="b7b8e-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="b7b8e-174"></span></span>

<span data-ttu-id="b7b8e-175">你可以通过上载 .csv 或 tsv 文件，将生成、网站和租户信息添加到调用分析。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="b7b8e-176">有了所有这些信息，呼叫分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="b7b8e-177">您或帮助台工程师可能会发现此信息有助于发现通话问题的趋势。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="b7b8e-178">例如，为什么同一建筑物中的许多用户有类似的通话质量问题？</span><span class="sxs-lookup"><span data-stu-id="b7b8e-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="b7b8e-179">如果你是团队和 Skype for business 管理员，则可以使用来自 & Skype for business 通话质量仪表板的团队中的现有数据文件。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="b7b8e-180">首先，从 "呼叫质量" 仪表板下载文件，然后将其上传到 "调用分析"。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="b7b8e-181">若要下载现有数据文件，请转到**Microsoft 团队管理中心** > **呼叫质量仪表板** > "**立即上载**"。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="b7b8e-182">在 "**我的上载**" 列表中，单击所需文件旁边的 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="b7b8e-183">若要上传新文件，请转到 " **Microsoft 团队管理中心** > "**位置**，然后选择 "**上载位置数据**" 或 "**替换位置数据**"。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="b7b8e-184">如果要从头开始创建 tsv 或 .csv 文件，请参阅[租户数据文件格式和生成数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。</span><span class="sxs-lookup"><span data-stu-id="b7b8e-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b7b8e-185">相关主题</span><span class="sxs-lookup"><span data-stu-id="b7b8e-185">Related topics</span></span>
<span data-ttu-id="b7b8e-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="b7b8e-186"></span></span>

[<span data-ttu-id="b7b8e-187">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="b7b8e-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="b7b8e-188">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="b7b8e-188">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 

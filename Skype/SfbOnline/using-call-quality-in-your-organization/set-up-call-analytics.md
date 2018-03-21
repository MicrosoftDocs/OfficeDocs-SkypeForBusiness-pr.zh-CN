---
title: "Skype 业务调用分析设置"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "设置和使用调用分析来识别和解决 Skype 的通话质量问题，业务和 Microsoft 小组。"
ms.openlocfilehash: ef8f9e10e25e7f67f0161a143c313ed25330db18
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="set-up-skype-for-business-call-analytics"></a><span data-ttu-id="81eb2-103">Skype 业务调用分析设置</span><span class="sxs-lookup"><span data-stu-id="81eb2-103">Set up Skype for Business Call Analytics</span></span>

<span data-ttu-id="81eb2-104">Skype 的在线业务的管理，您可以使用调用分析来解决 Skype 业务以及 Microsoft 小组呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="81eb2-104">As a Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="81eb2-105">您可能会发现有用设置调用分析中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="81eb2-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="81eb2-106">设置权限让其他人员，如帮助台代理，请使用调用的分析，但阻止其访问业务管理中心的 Skype 的其余部分。</span><span class="sxs-lookup"><span data-stu-id="81eb2-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics but prevent them from accessing the rest of the Skype for Business admin center.</span></span> 
    
- <span data-ttu-id="81eb2-107">通过上传数据的文件.tsv 或.csv 文件，可以将建筑物、 站点和组织信息添加到调用分析。</span><span class="sxs-lookup"><span data-stu-id="81eb2-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81eb2-108">调用分析目前在预览中。</span><span class="sxs-lookup"><span data-stu-id="81eb2-108">Call Analytics is currently in preview.</span></span> <span data-ttu-id="81eb2-109">文本和此处所述的图像可能会不匹配您的体验。</span><span class="sxs-lookup"><span data-stu-id="81eb2-109">Text and images described here may not match your experience.</span></span> 
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="81eb2-110">设置调用分析权限</span><span class="sxs-lookup"><span data-stu-id="81eb2-110">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="81eb2-111">作为管理员，您获得的调用分析的所有功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="81eb2-111">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="81eb2-112">此外，可以使用中包括的权限组，第 1 层和 2 层的调用分析帮助台模型。</span><span class="sxs-lookup"><span data-stu-id="81eb2-112">In addition, you can use a helpdesk model in Call Analytics that includes Tier 1 and Tier 2 permission groups.</span></span> <span data-ttu-id="81eb2-113">使用第 1 层的权限的用户可以访问只片面调用分析。</span><span class="sxs-lookup"><span data-stu-id="81eb2-113">Users with Tier 1 permissions can access only a limited view of Call Analytics.</span></span> <span data-ttu-id="81eb2-114">使用第 2 层的权限的用户可以访问调用分析的全部功能。</span><span class="sxs-lookup"><span data-stu-id="81eb2-114">Users with Tier 2 permissions can access the full functionality of Call Analytics.</span></span> <span data-ttu-id="81eb2-115">这两种权限级别对业务管理中心的 Skype 的其余部分阻止访问。</span><span class="sxs-lookup"><span data-stu-id="81eb2-115">Both permission levels prevent access to the rest of the Skype for Business admin center.</span></span> <span data-ttu-id="81eb2-116">您可以通过添加包含到第 1 层或 2 层部分中的权限页面的用户的组授予访问层。</span><span class="sxs-lookup"><span data-stu-id="81eb2-116">You can grant access to the tiers by adding a group that contains the user to either the Tier 1 or the Tier 2 section of the Permissions page.</span></span> <span data-ttu-id="81eb2-117">有关详细信息，请参阅[设置分层调用分析中的权限](set-up-call-analytics.md#BKMK_SetUpTier)。</span><span class="sxs-lookup"><span data-stu-id="81eb2-117">For details, see [Set up tiered permissions in Call Analytics](set-up-call-analytics.md#BKMK_SetUpTier).</span></span>
  
<span data-ttu-id="81eb2-118">第 1 层支持人员代理处理呼叫质量的基本问题。</span><span class="sxs-lookup"><span data-stu-id="81eb2-118">Tier 1 helpdesk agents handle basic call-quality problems.</span></span> <span data-ttu-id="81eb2-119">第 1 层工程师不调查问题的会议;它们收集相关的信息，然后就汇报给第 2 层工程师。</span><span class="sxs-lookup"><span data-stu-id="81eb2-119">Tier 1 agents don't investigate issues with meetings; they collect related information and then escalate to a Tier 2 agent.</span></span> <span data-ttu-id="81eb2-120">第 2 层工程师请参阅详细的电话记录中的信息隐藏的第 1 层工程师。</span><span class="sxs-lookup"><span data-stu-id="81eb2-120">Tier 2 agents see information in detailed call logs that's hidden from Tier 1 agents.</span></span> <span data-ttu-id="81eb2-121">下表概述了为代理使用调用分析可用的信息。</span><span class="sxs-lookup"><span data-stu-id="81eb2-121">The following table gives an overview of information available to agents using Call Analytics.</span></span>


|<span data-ttu-id="81eb2-122">**活动**</span><span class="sxs-lookup"><span data-stu-id="81eb2-122">**Activity**</span></span>|<span data-ttu-id="81eb2-123">**在调用分析信息**</span><span class="sxs-lookup"><span data-stu-id="81eb2-123">**Information in Call Analytics**</span></span>|<span data-ttu-id="81eb2-124">**第 1 层工程师所看到的内容**</span><span class="sxs-lookup"><span data-stu-id="81eb2-124">**What the Tier 1 agent sees**</span></span>|<span data-ttu-id="81eb2-125">**第 2 层工程师所看到的内容**</span><span class="sxs-lookup"><span data-stu-id="81eb2-125">**What the Tier 2 agent sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81eb2-126">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="81eb2-126">**Calls**</span></span> <br/> |<span data-ttu-id="81eb2-127">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="81eb2-127">Caller name</span></span>  <br/> |<span data-ttu-id="81eb2-128">只为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="81eb2-128">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="81eb2-129">用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="81eb2-129">User name.</span></span>  <br/> |
||<span data-ttu-id="81eb2-130">收件人姓名</span><span class="sxs-lookup"><span data-stu-id="81eb2-130">Recipient name</span></span>  <br/> |<span data-ttu-id="81eb2-131">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="81eb2-131">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="81eb2-132">收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="81eb2-132">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="81eb2-133">呼叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="81eb2-133">Caller phone number</span></span>  <br/> |<span data-ttu-id="81eb2-134">使用星号符号对，除了后三位的完整的电话号码进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-134">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="81eb2-135">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81eb2-135">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="81eb2-136">使用星号符号对，除了后三位的完整的电话号码进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-136">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="81eb2-137">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81eb2-137">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="81eb2-138">收件人电话号码</span><span class="sxs-lookup"><span data-stu-id="81eb2-138">Recipient phone number</span></span>  <br/> |<span data-ttu-id="81eb2-139">使用星号符号对，除了后三位的完整的电话号码进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="81eb2-140">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81eb2-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="81eb2-141">使用星号符号对，除了后三位的完整的电话号码进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="81eb2-142">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81eb2-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="81eb2-143">**呼叫的详细记录** > **高级**选项卡</span><span class="sxs-lookup"><span data-stu-id="81eb2-143">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="81eb2-144">不显示信息。</span><span class="sxs-lookup"><span data-stu-id="81eb2-144">Information not shown.</span></span>  <br/> |<span data-ttu-id="81eb2-145">所示，如设备名称、 IP 地址、 子网映射和所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="81eb2-145">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="81eb2-146">**呼叫的详细记录** > **高级** > **调试**选项卡</span><span class="sxs-lookup"><span data-stu-id="81eb2-146">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="81eb2-147">不显示信息。</span><span class="sxs-lookup"><span data-stu-id="81eb2-147">Information not shown.</span></span>  <br/> |<span data-ttu-id="81eb2-148">所示，如 DNS 后缀和 SSID 的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="81eb2-148">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="81eb2-149">**会议**</span><span class="sxs-lookup"><span data-stu-id="81eb2-149">**Meetings**</span></span> <br/> |<span data-ttu-id="81eb2-150">参与者名称</span><span class="sxs-lookup"><span data-stu-id="81eb2-150">Participant names</span></span>  <br/> |<span data-ttu-id="81eb2-151">只为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="81eb2-151">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="81eb2-152">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="81eb2-152">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="81eb2-153">所示的所有名称。</span><span class="sxs-lookup"><span data-stu-id="81eb2-153">All names shown.</span></span>  <br/> |
||<span data-ttu-id="81eb2-154">参与者计数</span><span class="sxs-lookup"><span data-stu-id="81eb2-154">Participant count</span></span>  <br/> |<span data-ttu-id="81eb2-155">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="81eb2-155">Number of participants.</span></span>  <br/> |<span data-ttu-id="81eb2-156">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="81eb2-156">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="81eb2-157">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="81eb2-157">Session details</span></span>  <br/> |<span data-ttu-id="81eb2-158">会话详细信息显示有例外。</span><span class="sxs-lookup"><span data-stu-id="81eb2-158">Session details shown with exceptions.</span></span> <span data-ttu-id="81eb2-159">只为其代理搜索的用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="81eb2-159">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="81eb2-160">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="81eb2-160">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="81eb2-161">最后三位数字电话号码替换为星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-161">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="81eb2-162">会话详细信息显示。</span><span class="sxs-lookup"><span data-stu-id="81eb2-162">Session details shown.</span></span> <span data-ttu-id="81eb2-163">用户名和会话详细信息显示。</span><span class="sxs-lookup"><span data-stu-id="81eb2-163">User names and session details shown.</span></span> <span data-ttu-id="81eb2-164">最后三位数字电话号码替换为星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="81eb2-164">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
   
 <span data-ttu-id="81eb2-165">**设置调用分析中的分层权限**
 <a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="81eb2-165">**Set up tiered permissions in Call Analytics**
<a name="BKMK_SetUpTier"> </a></span></span>
  
1. <span data-ttu-id="81eb2-166">第 1 层和 2 层，为创建 Office 365 安全组，并向每个组中添加所需的人员。</span><span class="sxs-lookup"><span data-stu-id="81eb2-166">Create Office 365 security groups for Tier 1 and Tier 2, and add the people you want to each group.</span></span> <span data-ttu-id="81eb2-167">您还可以重用现有的安全组。</span><span class="sxs-lookup"><span data-stu-id="81eb2-167">You can also reuse existing security groups.</span></span> <span data-ttu-id="81eb2-168">有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。</span><span class="sxs-lookup"><span data-stu-id="81eb2-168">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>
    
2. <span data-ttu-id="81eb2-169">在 Office 365 管理中心，转到**管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="81eb2-169">In the Office 365 admin center, go to **Admin centers** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81eb2-170">如果您居住在旧 Skype 的业务管理中心，请通过单击**来尝试我们的新管理中心**转到新版本。</span><span class="sxs-lookup"><span data-stu-id="81eb2-170">If you land in the old Skype for Business admin center, go to the new version by clicking **Come try our new admin center**.</span></span> 
  
3. <span data-ttu-id="81eb2-171">在业务管理中心新 Skype，单击**权限**。</span><span class="sxs-lookup"><span data-stu-id="81eb2-171">In the new Skype for Business admin center, click **Permissions**.</span></span>
    
4. <span data-ttu-id="81eb2-172">将 Office 365 安全组添加到**第 1 层**和**2 层**框。</span><span class="sxs-lookup"><span data-stu-id="81eb2-172">Add the Office 365 security groups to the **Tier 1** and **Tier 2** boxes.</span></span> <span data-ttu-id="81eb2-173">您可以为每个角色添加多个组。</span><span class="sxs-lookup"><span data-stu-id="81eb2-173">You can add multiple groups to each role.</span></span>
    
     ![屏幕抓图显示了使用第 1 层和 2 层权限选项调用分析页面的权限。](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 <span data-ttu-id="81eb2-175">通过专用的 URL *https://adminportal.services.skypeforbusiness.com*调用分析获得与这些权限级别的用户。</span><span class="sxs-lookup"><span data-stu-id="81eb2-175">Users with either of these permission levels get to Call Analytics via the dedicated URL *https://adminportal.services.skypeforbusiness.com*.</span></span>
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="81eb2-176">传.tsv 或.csv 文件添加构建，站点，和租户信息</span><span class="sxs-lookup"><span data-stu-id="81eb2-176">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="81eb2-177"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="81eb2-177"></span></span>

<span data-ttu-id="81eb2-178">可以通过上传的.tsv 或.csv 文件构建、 站点和组织信息添加到调用分析。</span><span class="sxs-lookup"><span data-stu-id="81eb2-178">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="81eb2-179">与所有此类信息调用分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="81eb2-179">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="81eb2-180">您或技术支持工程师可能会发现此信息有助于发现在呼叫问题的趋势。</span><span class="sxs-lookup"><span data-stu-id="81eb2-180">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="81eb2-181">例如，为什么很多用户在同一建筑内有类似呼叫质量问题？</span><span class="sxs-lookup"><span data-stu-id="81eb2-181">For example, why are many users in the same building having similar call quality issues?</span></span> 
  
![屏幕抓图显示了具有多站点和子网的数量值网站页和选择文件按钮来上载.tsv 或.csv 文件导入网站数据。](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
<span data-ttu-id="81eb2-183">如果 Skype 业务管理员，您可以使用现有数据文件从 Skype 业务在线呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="81eb2-183">If you're a Skype for Business admin, you can use an existing data file from the Skype for Business Online Call Quality Dashboard.</span></span> <span data-ttu-id="81eb2-184">首先，从呼叫质量面板，下载该文件，然后您将其上载到调用分析。</span><span class="sxs-lookup"><span data-stu-id="81eb2-184">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> <span data-ttu-id="81eb2-185">要下载一个现有的数据文件，请转至**业务管理中心的 Skype** > **工具** > **Skype 业务在线呼叫质量仪表板** > **立即上载**。</span><span class="sxs-lookup"><span data-stu-id="81eb2-185">To download an existing data file, go to the **Skype for Business Admin center** > **Tools** > **Skype for Business Online Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="81eb2-186">在**我上载**列表中，单击所需的文件旁边的**下载**。</span><span class="sxs-lookup"><span data-stu-id="81eb2-186">In the **My uploads** list, click **Download** next to the file you want.</span></span>
  
<span data-ttu-id="81eb2-187">如果您正在从头创建.tsv 或.csv 文件，请参阅[租户的数据文件格式和生成的数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。</span><span class="sxs-lookup"><span data-stu-id="81eb2-187">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="81eb2-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="81eb2-188">Related topics</span></span>
<span data-ttu-id="81eb2-189"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="81eb2-189"></span></span>

[<span data-ttu-id="81eb2-190">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="81eb2-190">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="81eb2-191">通话分析与通话质量仪表板之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="81eb2-191">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a><span data-ttu-id="81eb2-192">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="81eb2-192">Feedback?</span></span>
<span data-ttu-id="81eb2-193">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="81eb2-193">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
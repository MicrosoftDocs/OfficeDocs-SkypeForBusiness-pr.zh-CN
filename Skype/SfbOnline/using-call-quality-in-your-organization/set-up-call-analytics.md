---
title: 设置 Skype for Business 通话分析
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
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
description: 设置和使用调用分析确定并解决 Skype 的业务和 Microsoft 团队呼叫质量问题。
ms.openlocfilehash: d9483d702280bfe7119ff64431e5d42b168f9021
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205012"
---
# <a name="set-up-skype-for-business-call-analytics"></a><span data-ttu-id="83704-103">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="83704-103">Set up Skype for Business Call Analytics</span></span>

<span data-ttu-id="83704-104">为业务联机管理 Skype，您可以使用调用分析解决 for Business 的 Skype 和 Microsoft 团队呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="83704-104">As a Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="83704-105">您可能会发现有用设置呼叫分析中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="83704-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="83704-106">设置让其他人员，如技术支持代理，请使用调用分析的权限，但禁止访问业务管理中心的 Skype 的其余部分。</span><span class="sxs-lookup"><span data-stu-id="83704-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics but prevent them from accessing the rest of the Skype for Business admin center.</span></span> 
    
- <span data-ttu-id="83704-107">上载.tsv 或.csv 数据文件，可以将构建、 网站和租户信息添加到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="83704-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83704-108">呼叫分析现已在 Microsoft 团队和 Skype 的业务管理中心，网址为https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="83704-108">Call Analytics is now available in the Microsoft Teams and Skype for Business admin center at https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="83704-109">帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。</span><span class="sxs-lookup"><span data-stu-id="83704-109">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="83704-110">同时，您可以继续使用上的终结点https://adminportal.services.skypeforbusiness.com1 层和第 2 层帮助台访问。</span><span class="sxs-lookup"><span data-stu-id="83704-110">In the meantime you can continue to use the endpoint at https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span> 
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="83704-111">设置呼叫分析的权限</span><span class="sxs-lookup"><span data-stu-id="83704-111">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="83704-112">作为管理员，您获取的呼叫分析的所有功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="83704-112">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="83704-113">此外，您可以使用帮助台模型中包括层 1 和 2 层权限组的呼叫的分析。</span><span class="sxs-lookup"><span data-stu-id="83704-113">In addition, you can use a helpdesk model in Call Analytics that includes Tier 1 and Tier 2 permission groups.</span></span> <span data-ttu-id="83704-114">具有 1 层权限的用户可以访问仅有限的呼叫分析视图。</span><span class="sxs-lookup"><span data-stu-id="83704-114">Users with Tier 1 permissions can access only a limited view of Call Analytics.</span></span> <span data-ttu-id="83704-115">第 2 层权限的用户可以访问呼叫分析的全部功能。</span><span class="sxs-lookup"><span data-stu-id="83704-115">Users with Tier 2 permissions can access the full functionality of Call Analytics.</span></span> <span data-ttu-id="83704-116">这两个权限级别防止对业务管理中心的 Skype 的其余部分的访问。</span><span class="sxs-lookup"><span data-stu-id="83704-116">Both permission levels prevent access to the rest of the Skype for Business admin center.</span></span> <span data-ttu-id="83704-117">您可以通过添加包含到 Tier 1 或权限页上的第 2 层一部分用户组授予对层的访问。</span><span class="sxs-lookup"><span data-stu-id="83704-117">You can grant access to the tiers by adding a group that contains the user to either the Tier 1 or the Tier 2 section of the Permissions page.</span></span> <span data-ttu-id="83704-118">有关详细信息，请参阅[设置呼叫分析中的分层权限](set-up-call-analytics.md#BKMK_SetUpTier)。</span><span class="sxs-lookup"><span data-stu-id="83704-118">For details, see [Set up tiered permissions in Call Analytics](set-up-call-analytics.md#BKMK_SetUpTier).</span></span>
  
<span data-ttu-id="83704-119">第 1 层帮助台代理处理基本呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="83704-119">Tier 1 helpdesk agents handle basic call-quality problems.</span></span> <span data-ttu-id="83704-120">第 1 层代理不调查问题与会议;它们收集相关的信息，然后升级到第 2 层代理。</span><span class="sxs-lookup"><span data-stu-id="83704-120">Tier 1 agents don't investigate issues with meetings; they collect related information and then escalate to a Tier 2 agent.</span></span> <span data-ttu-id="83704-121">第 2 层代理，请参阅详细的呼叫日志的从 1 层代理处于隐藏状态的信息。</span><span class="sxs-lookup"><span data-stu-id="83704-121">Tier 2 agents see information in detailed call logs that's hidden from Tier 1 agents.</span></span> <span data-ttu-id="83704-122">下表概述了至代理使用调用分析的可用信息。</span><span class="sxs-lookup"><span data-stu-id="83704-122">The following table gives an overview of information available to agents using Call Analytics.</span></span>


|<span data-ttu-id="83704-123">**活动**</span><span class="sxs-lookup"><span data-stu-id="83704-123">**Activity**</span></span>|<span data-ttu-id="83704-124">**呼叫分析中的信息**</span><span class="sxs-lookup"><span data-stu-id="83704-124">**Information in Call Analytics**</span></span>|<span data-ttu-id="83704-125">**第 1 层代理所看到的内容**</span><span class="sxs-lookup"><span data-stu-id="83704-125">**What the Tier 1 agent sees**</span></span>|<span data-ttu-id="83704-126">**第 2 层代理所看到的内容**</span><span class="sxs-lookup"><span data-stu-id="83704-126">**What the Tier 2 agent sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83704-127">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="83704-127">**Calls**</span></span> <br/> |<span data-ttu-id="83704-128">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="83704-128">Caller name</span></span>  <br/> |<span data-ttu-id="83704-129">仅为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="83704-129">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="83704-130">用户名。</span><span class="sxs-lookup"><span data-stu-id="83704-130">User name.</span></span>  <br/> |
||<span data-ttu-id="83704-131">收件人的姓名</span><span class="sxs-lookup"><span data-stu-id="83704-131">Recipient name</span></span>  <br/> |<span data-ttu-id="83704-132">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="83704-132">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="83704-133">收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="83704-133">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="83704-134">呼叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="83704-134">Caller phone number</span></span>  <br/> |<span data-ttu-id="83704-135">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="83704-135">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="83704-136">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83704-136">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="83704-137">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="83704-137">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="83704-138">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83704-138">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="83704-139">收件人的电话号码</span><span class="sxs-lookup"><span data-stu-id="83704-139">Recipient phone number</span></span>  <br/> |<span data-ttu-id="83704-140">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="83704-140">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="83704-141">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83704-141">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="83704-142">除最后三个数字的完整的电话号码是模糊处理星号符号。</span><span class="sxs-lookup"><span data-stu-id="83704-142">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="83704-143">例如，15552823 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83704-143">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="83704-144">**呼叫详细信息** > **高级**选项卡</span><span class="sxs-lookup"><span data-stu-id="83704-144">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="83704-145">不显示的信息。</span><span class="sxs-lookup"><span data-stu-id="83704-145">Information not shown.</span></span>  <br/> |<span data-ttu-id="83704-146">所示，如设备名称、 IP 地址、 子网映射和更多的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="83704-146">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="83704-147">**呼叫详细信息** > **高级** > **调试**选项卡</span><span class="sxs-lookup"><span data-stu-id="83704-147">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="83704-148">不显示的信息。</span><span class="sxs-lookup"><span data-stu-id="83704-148">Information not shown.</span></span>  <br/> |<span data-ttu-id="83704-149">所示，如 DNS 后缀和 SSID 的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="83704-149">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="83704-150">**会议**</span><span class="sxs-lookup"><span data-stu-id="83704-150">**Meetings**</span></span> <br/> |<span data-ttu-id="83704-151">参与者姓名</span><span class="sxs-lookup"><span data-stu-id="83704-151">Participant names</span></span>  <br/> |<span data-ttu-id="83704-152">仅为其代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="83704-152">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="83704-153">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="83704-153">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="83704-154">显示所有名称。</span><span class="sxs-lookup"><span data-stu-id="83704-154">All names shown.</span></span>  <br/> |
||<span data-ttu-id="83704-155">参与者计数</span><span class="sxs-lookup"><span data-stu-id="83704-155">Participant count</span></span>  <br/> |<span data-ttu-id="83704-156">参与者数目。</span><span class="sxs-lookup"><span data-stu-id="83704-156">Number of participants.</span></span>  <br/> |<span data-ttu-id="83704-157">参与者数目。</span><span class="sxs-lookup"><span data-stu-id="83704-157">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="83704-158">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="83704-158">Session details</span></span>  <br/> |<span data-ttu-id="83704-159">显示例外的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="83704-159">Session details shown with exceptions.</span></span> <span data-ttu-id="83704-160">仅为其显示搜索的代理的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="83704-160">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="83704-161">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="83704-161">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="83704-162">最后三个星号符号模糊处理的电话号码的数字。</span><span class="sxs-lookup"><span data-stu-id="83704-162">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="83704-163">显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="83704-163">Session details shown.</span></span> <span data-ttu-id="83704-164">用户的用户名和显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="83704-164">User names and session details shown.</span></span> <span data-ttu-id="83704-165">最后三个星号符号模糊处理的电话号码的数字。</span><span class="sxs-lookup"><span data-stu-id="83704-165">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
   
 <span data-ttu-id="83704-166">**设置呼叫分析中的分层权限**
 <a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="83704-166">**Set up tiered permissions in Call Analytics**
<a name="BKMK_SetUpTier"> </a></span></span>

<span data-ttu-id="83704-167">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="83704-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="83704-168">第 1 层和第 2 层中创建 Office 365 安全组，并将所需的人员添加到每个组。</span><span class="sxs-lookup"><span data-stu-id="83704-168">Create Office 365 security groups for Tier 1 and Tier 2, and add the people you want to each group.</span></span> <span data-ttu-id="83704-169">您还可以重用现有的安全组。</span><span class="sxs-lookup"><span data-stu-id="83704-169">You can also reuse existing security groups.</span></span> <span data-ttu-id="83704-170">有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。</span><span class="sxs-lookup"><span data-stu-id="83704-170">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>
    
2. <span data-ttu-id="83704-171">在 Office 365 管理中心，转到**管理中心** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="83704-171">In the Office 365 admin center, go to **Admin centers** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83704-172">如果您位于业务管理中心的旧的 Skype 中，请通过单击**位于尝试我们的新管理中心**转到新版本。</span><span class="sxs-lookup"><span data-stu-id="83704-172">If you land in the old Skype for Business admin center, go to the new version by clicking **Come try our new admin center**.</span></span> 
  
3. <span data-ttu-id="83704-173">在业务管理中心新 Skype，单击**权限**。</span><span class="sxs-lookup"><span data-stu-id="83704-173">In the new Skype for Business admin center, click **Permissions**.</span></span>
    
4. <span data-ttu-id="83704-174">将 Office 365 安全组添加到**Tier 1**和**2 层**框中。</span><span class="sxs-lookup"><span data-stu-id="83704-174">Add the Office 365 security groups to the **Tier 1** and **Tier 2** boxes.</span></span> <span data-ttu-id="83704-175">您可以将多个组添加到每个角色。</span><span class="sxs-lookup"><span data-stu-id="83704-175">You can add multiple groups to each role.</span></span>
    
     ![屏幕快照显示了调用分析页层 1 和 2 层权限的选项的权限。](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 <span data-ttu-id="83704-177">具有这些权限级别之一的用户获取对呼叫的分析通过专用 URL *https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="83704-177">Users with either of these permission levels get to Call Analytics via the dedicated URL *https://adminportal.services.skypeforbusiness.com*.</span></span>
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="83704-178">上载.tsv 或.csv 文件添加生成，网站和租户信息</span><span class="sxs-lookup"><span data-stu-id="83704-178">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="83704-179"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="83704-179"></span></span>

<span data-ttu-id="83704-180">可以通过上载.csv 或.tsv 文件构建、 网站和租户信息添加到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="83704-180">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="83704-181">与所有此类信息呼叫分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="83704-181">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="83704-182">您或帮助台代理可能会发现有用帮助呼叫问题中的专色趋势的此信息。</span><span class="sxs-lookup"><span data-stu-id="83704-182">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="83704-183">例如，为什么很多用户在同一构建具有类似呼叫质量问题？</span><span class="sxs-lookup"><span data-stu-id="83704-183">For example, why are many users in the same building having similar call quality issues?</span></span> 
  
![屏幕快照显示了网站页的网站数量和子网，数值和选择文件按钮上载.tsv 或.csv 文件导入网站数据。](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
<span data-ttu-id="83704-185">如果您的业务管理 Skype，您可以使用 Skype 从现有数据文件对于业务联机呼叫质量的仪表板。</span><span class="sxs-lookup"><span data-stu-id="83704-185">If you're a Skype for Business admin, you can use an existing data file from the Skype for Business Online Call Quality Dashboard.</span></span> <span data-ttu-id="83704-186">首先，呼叫质量仪表板中下载文件，然后将其上载到呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="83704-186">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> <span data-ttu-id="83704-187">若要下载现有数据文件，请转到**业务管理中心的 Skype** > **工具** > **业务联机呼叫质量仪表板的 Skype** > **立即上载**。</span><span class="sxs-lookup"><span data-stu-id="83704-187">To download an existing data file, go to the **Skype for Business Admin center** > **Tools** > **Skype for Business Online Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="83704-188">在**我上载**列表中，单击所需的文件旁边的**下载**。</span><span class="sxs-lookup"><span data-stu-id="83704-188">In the **My uploads** list, click **Download** next to the file you want.</span></span>
  
<span data-ttu-id="83704-189">如果您正在从头创建.tsv 或.csv 文件，请参阅[租户数据文件格式和构建数据文件结构](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)。</span><span class="sxs-lookup"><span data-stu-id="83704-189">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="83704-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="83704-190">Related topics</span></span>
<span data-ttu-id="83704-191"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="83704-191"></span></span>

[<span data-ttu-id="83704-192">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="83704-192">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="83704-193">呼叫分析和呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="83704-193">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 

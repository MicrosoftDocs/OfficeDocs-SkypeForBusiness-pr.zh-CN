---
title: Skype for Business Online 委派设置和疑难解答
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 本文介绍如何设置 Skype for Business Online 委派和疑难解答。 本文提供了有关设置建议、最佳做法和疑难解答步骤的指南。
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285241"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="07c01-104">Skype for Business Online 委派设置和疑难解答</span><span class="sxs-lookup"><span data-stu-id="07c01-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="07c01-105">本文介绍如何设置 Skype for Business Online 委派和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="07c01-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="07c01-106">本文提供了有关设置建议、最佳做法和疑难解答步骤的指南。</span><span class="sxs-lookup"><span data-stu-id="07c01-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="07c01-107">指南和要求</span><span class="sxs-lookup"><span data-stu-id="07c01-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="07c01-108">委派指南</span><span class="sxs-lookup"><span data-stu-id="07c01-108">Guidelines for delegation</span></span>

<span data-ttu-id="07c01-109">设置并让委派正常工作取决于您遵循以下指南:</span><span class="sxs-lookup"><span data-stu-id="07c01-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="07c01-110">您必须使用 Skype for Business 2015 完全客户端和 "最新更新" 或 "Skype for Business 2016 完全客户端"。</span><span class="sxs-lookup"><span data-stu-id="07c01-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="07c01-111">您必须将 Outlook 2013 客户端与最新更新或 Outlook 2016 客户端配合使用。</span><span class="sxs-lookup"><span data-stu-id="07c01-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="07c01-112">确保委托人进行通话和代理人计算机具有一个作为主要或默认配置文件的 Outlook 邮件配置文件。</span><span class="sxs-lookup"><span data-stu-id="07c01-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="07c01-113">该邮件配置文件应仅包含一个帐户。</span><span class="sxs-lookup"><span data-stu-id="07c01-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="07c01-114">委托人进行通话的 Skype for business 和代理人应为联机用户。</span><span class="sxs-lookup"><span data-stu-id="07c01-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="07c01-115">此外, 每个帐户的 Exchange 服务器邮箱都必须同时联机或都是本地的。</span><span class="sxs-lookup"><span data-stu-id="07c01-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="07c01-116">委托人进行通话和代理人应使用相同的 Outlook 主要版本。</span><span class="sxs-lookup"><span data-stu-id="07c01-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="07c01-117">在客户端策略中, **EnableExchangeDelegateSync**属性值应设置为**true** 。</span><span class="sxs-lookup"><span data-stu-id="07c01-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="07c01-118">你可以通过在 Skype for Business Online PowerShell 模块中运行**set-csclientpolicy** cmdlet 来验证此设置。</span><span class="sxs-lookup"><span data-stu-id="07c01-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="07c01-119">在不同工作站上, 委托人进行通话和代理人必须同时登录到 Skype for Business 和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="07c01-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="07c01-120">Skype for Business Online 委派不支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="07c01-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="07c01-121">这是因为共享邮箱没有**sendonbehalf**访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="07c01-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="07c01-122">Skype for Business 客户端版本支持</span><span class="sxs-lookup"><span data-stu-id="07c01-122">Skype for Business client version support</span></span>

||<span data-ttu-id="07c01-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="07c01-123">**Outlook 2013**</span></span>|<span data-ttu-id="07c01-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="07c01-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07c01-125">**Lync/Skype for Business Basic 客户端**</span><span class="sxs-lookup"><span data-stu-id="07c01-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="07c01-126">不支持</span><span class="sxs-lookup"><span data-stu-id="07c01-126">Not supported</span></span> |<span data-ttu-id="07c01-127">不支持</span><span class="sxs-lookup"><span data-stu-id="07c01-127">Not supported</span></span>
|<span data-ttu-id="07c01-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="07c01-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="07c01-129">支持</span><span class="sxs-lookup"><span data-stu-id="07c01-129">Supported</span></span>| <span data-ttu-id="07c01-130">支持</span><span class="sxs-lookup"><span data-stu-id="07c01-130">Supported</span></span>|
|<span data-ttu-id="07c01-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="07c01-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="07c01-132">支持</span><span class="sxs-lookup"><span data-stu-id="07c01-132">Supported</span></span>| <span data-ttu-id="07c01-133">支持</span><span class="sxs-lookup"><span data-stu-id="07c01-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="07c01-134">许可要求</span><span class="sxs-lookup"><span data-stu-id="07c01-134">Licensing requirements</span></span>

<span data-ttu-id="07c01-135">**企业版 E3 许可方案**</span><span class="sxs-lookup"><span data-stu-id="07c01-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="07c01-136">**许可证**</span><span class="sxs-lookup"><span data-stu-id="07c01-136">**License**</span></span>|<span data-ttu-id="07c01-137">**客户端**</span><span class="sxs-lookup"><span data-stu-id="07c01-137">**Clients**</span></span>|<span data-ttu-id="07c01-138">**注释**</span><span class="sxs-lookup"><span data-stu-id="07c01-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07c01-139">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="07c01-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="07c01-140">适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="07c01-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="07c01-141">Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="07c01-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="07c01-142">Skype for Business 基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="07c01-143">对于 Mac 客户端, 您可以委派呼叫, 但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="07c01-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="07c01-144">企业版 E3 与 Office 365 Phone System + Office 365 xCalling 计划</span><span class="sxs-lookup"><span data-stu-id="07c01-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="07c01-145">适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="07c01-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="07c01-146">Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="07c01-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="07c01-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="07c01-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="07c01-148">Skype for Business 基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="07c01-149">对于 Mac 客户端, 您可以委派呼叫, 但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="07c01-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="07c01-150">**企业版 E5 许可方案**</span><span class="sxs-lookup"><span data-stu-id="07c01-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="07c01-151">**许可证**</span><span class="sxs-lookup"><span data-stu-id="07c01-151">**License**</span></span>|<span data-ttu-id="07c01-152">**客户端**</span><span class="sxs-lookup"><span data-stu-id="07c01-152">**Clients**</span></span>|<span data-ttu-id="07c01-153">**注释**</span><span class="sxs-lookup"><span data-stu-id="07c01-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07c01-154">企业版 E5</span><span class="sxs-lookup"><span data-stu-id="07c01-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="07c01-155">适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 (Skype for Business 2015)。</span><span class="sxs-lookup"><span data-stu-id="07c01-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="07c01-156">Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="07c01-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="07c01-157">Skype for Business 基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="07c01-158">对于 Mac 客户端, 您可以委派呼叫, 但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="07c01-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="07c01-159">企业版 E5 + Office 365 通话计划</span><span class="sxs-lookup"><span data-stu-id="07c01-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="07c01-160">Mac 版 Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="07c01-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="07c01-161">适用于 Outlook 2013 或 Outlook 2016 的 Lync 2013 (Skype for Business 2015)</span><span class="sxs-lookup"><span data-stu-id="07c01-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="07c01-162">Outlook 2013 或 Outlook 2016 使用的 Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="07c01-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="07c01-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="07c01-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="07c01-164">Skype for Business 基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="07c01-165">对于 Mac 客户端, 您可以委派呼叫, 但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="07c01-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="07c01-166">设置和验证委派</span><span class="sxs-lookup"><span data-stu-id="07c01-166">Set up and verify delegation</span></span>

<span data-ttu-id="07c01-167">若要设置 Skype for Business Online 委派, 请按照下列步骤操作:</span><span class="sxs-lookup"><span data-stu-id="07c01-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="07c01-168">对于 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="07c01-168">For Windows clients</span></span>

 <span data-ttu-id="07c01-169">**"呼叫转接" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="07c01-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="07c01-170">选择 "**工具** > "**选项** > "**呼叫转接设置**"。</span><span class="sxs-lookup"><span data-stu-id="07c01-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="07c01-171">选择 **"编辑我的代理人成员"**。</span><span class="sxs-lookup"><span data-stu-id="07c01-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="07c01-172">选择 "**添加**", 选择要添加的代理人, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="07c01-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="07c01-173">**"无呼叫转接" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="07c01-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="07c01-174">在 Outlook 中, 选择 "**文件** > **帐户设置** > "。 "**委派 Access** > **添加**"。</span><span class="sxs-lookup"><span data-stu-id="07c01-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="07c01-175">找到并添加将成为代理人的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="07c01-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="07c01-176">选择 "**日历**" 菜单, 然后选择 "**编辑" (可以阅读、创建和修改项目)**。</span><span class="sxs-lookup"><span data-stu-id="07c01-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="07c01-177">对于 Mac 客户端-Lync</span><span class="sxs-lookup"><span data-stu-id="07c01-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="07c01-178">**"呼叫转接" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="07c01-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="07c01-179">如果客户端没有 "**呼叫转接**" 选项卡具有 "**编辑我的代理人成员**" 链接, 并且委托人进行通话位于 Mac 计算机上, 则委托人进行通话必须登录到基于 Windows 的计算机才能设置委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="07c01-180">这是因为 Mac 客户端无法建立 MAPI 连接, 这是建立来自 Outlook 的 Skype for Business 委派的必要条件。</span><span class="sxs-lookup"><span data-stu-id="07c01-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="07c01-181">验证成功</span><span class="sxs-lookup"><span data-stu-id="07c01-181">Verify success</span></span>

<span data-ttu-id="07c01-182">如果设置成功, 则代理人会看到**你已添加为 _LT_ Name>** 消息的代理人, 并且还会创建 "**我管理的用户**" 组调用。</span><span class="sxs-lookup"><span data-stu-id="07c01-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="07c01-183">委托人进行通话应看到 "**委派**" 组已创建。</span><span class="sxs-lookup"><span data-stu-id="07c01-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07c01-184">委派权限通常在安装过程的30分钟内出现。</span><span class="sxs-lookup"><span data-stu-id="07c01-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="07c01-185">但是, 此过程可能需要长达24小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="07c01-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="07c01-186">疑难解答</span><span class="sxs-lookup"><span data-stu-id="07c01-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="07c01-187">常见问题</span><span class="sxs-lookup"><span data-stu-id="07c01-187">Common issues</span></span>

- > <span data-ttu-id="07c01-188">**问题 1**委托人进行通话删除了 Outlook 客户端中的代理人后, 该代理人条目会继续出现在 "**管理呼叫**" 组中。</span><span class="sxs-lookup"><span data-stu-id="07c01-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="07c01-189">**解决方案 1**在 Skype for Business 客户端上, 右键单击 "**代理人**" 组中的代理人, 然后选择 "**从组中删除**"。</span><span class="sxs-lookup"><span data-stu-id="07c01-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="07c01-190">**问题 2**通过 Outlook 客户端授予代理访问权限后, 将不会为代理人显示确认消息和**我管理**的组调用的人员。</span><span class="sxs-lookup"><span data-stu-id="07c01-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="07c01-191">**解决方案 2**从 Outlook 客户端删除委派, 等待大约15分钟进行复制, 然后再次添加代理人。</span><span class="sxs-lookup"><span data-stu-id="07c01-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="07c01-192">其他常见问题</span><span class="sxs-lookup"><span data-stu-id="07c01-192">Other common issues</span></span>

- <span data-ttu-id="07c01-193">如果超过25个代理和25个委托的阈值, 则委派将不起作用。</span><span class="sxs-lookup"><span data-stu-id="07c01-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="07c01-194">不支持 Skype for Business 基本客户端。</span><span class="sxs-lookup"><span data-stu-id="07c01-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="07c01-195">如果您安装了 Skype for Business 基本客户端, 它将删除并中断委派。</span><span class="sxs-lookup"><span data-stu-id="07c01-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="07c01-196">如果**MAPI 状态**值不**正常**, 请确保**SIP**和**SMTP**值匹配。</span><span class="sxs-lookup"><span data-stu-id="07c01-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="07c01-197">第一次启动 Skype for Business 和 Outlook 后, MAPI 状态可能需要几分钟才能显示为 **"正常"** 。</span><span class="sxs-lookup"><span data-stu-id="07c01-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="07c01-198">不支持创建安全组和为该安全组添加委派权限。</span><span class="sxs-lookup"><span data-stu-id="07c01-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="07c01-199">MAPI 不可用。</span><span class="sxs-lookup"><span data-stu-id="07c01-199">MAPI is unavailable.</span></span> <span data-ttu-id="07c01-200">请参阅[Skype For business 2016 客户端中的 "MAPI 不可用" 错误](https://support.microsoft.com/en-us/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="07c01-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="07c01-201">无法通过 Skype for Business 客户端访问 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="07c01-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="07c01-202">如果出现这种情况, 请运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它通过。</span><span class="sxs-lookup"><span data-stu-id="07c01-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="07c01-203">相关主题</span><span class="sxs-lookup"><span data-stu-id="07c01-203">Related topics</span></span>
[<span data-ttu-id="07c01-204">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="07c01-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="07c01-205">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="07c01-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 本文介绍如何设置和排查联机Skype for Business问题。 本文提供设置建议、最佳做法和故障排除步骤的指导。
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239821"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="e9e70-104">Skype for Business Online 委派设置和疑难解答</span><span class="sxs-lookup"><span data-stu-id="e9e70-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e9e70-105">本文介绍如何设置和排查联机Skype for Business问题。</span><span class="sxs-lookup"><span data-stu-id="e9e70-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="e9e70-106">本文提供设置建议、最佳做法和故障排除步骤的指导。</span><span class="sxs-lookup"><span data-stu-id="e9e70-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="e9e70-107">指南和要求</span><span class="sxs-lookup"><span data-stu-id="e9e70-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="e9e70-108">委派指南</span><span class="sxs-lookup"><span data-stu-id="e9e70-108">Guidelines for delegation</span></span>

<span data-ttu-id="e9e70-109">设置和让委派正常工作取决于你遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="e9e70-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="e9e70-110">必须使用具有最新更新的 Skype for Business 2015 完整客户端或 Skype for Business 2016 完整客户端。</span><span class="sxs-lookup"><span data-stu-id="e9e70-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="e9e70-111">必须使用具有最新更新的 Outlook 2013 客户端或 Outlook 2016 客户端。</span><span class="sxs-lookup"><span data-stu-id="e9e70-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="e9e70-112">确保委派和委派计算机具有一个Outlook配置文件是主要配置文件或默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="e9e70-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="e9e70-113">该邮件配置文件应仅包含一个帐户。</span><span class="sxs-lookup"><span data-stu-id="e9e70-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="e9e70-114">Skype for Business代理人和代理人的用户应为"联机用户"。</span><span class="sxs-lookup"><span data-stu-id="e9e70-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="e9e70-115">此外，Exchange Server帐户的邮箱必须同时为"联机"或两者均位于本地。</span><span class="sxs-lookup"><span data-stu-id="e9e70-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="e9e70-116">委派方和代理人应该使用相同的主要版本Outlook。</span><span class="sxs-lookup"><span data-stu-id="e9e70-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="e9e70-117">在 **客户端策略中，EnableExchangeDelegateSync** 属性值应设置为 true。</span><span class="sxs-lookup"><span data-stu-id="e9e70-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="e9e70-118">可以通过在 Skype for Business Online PowerShell 模块中运行 **Get-CSClientPolicy** cmdlet 来验证此设置。</span><span class="sxs-lookup"><span data-stu-id="e9e70-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="e9e70-119">委托方和代理人必须同时Skype for Business Outlook登录到不同的工作站。</span><span class="sxs-lookup"><span data-stu-id="e9e70-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="e9e70-120">联机委派不支持Skype for Business邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9e70-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="e9e70-121">这是因为共享邮箱没有 ACL 中的 **sendonbehalf** 访问控制列表 (ACL) 。</span><span class="sxs-lookup"><span data-stu-id="e9e70-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="e9e70-122">Skype for Business客户端版本支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-122">Skype for Business client version support</span></span>

||<span data-ttu-id="e9e70-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="e9e70-123">**Outlook 2013**</span></span>|<span data-ttu-id="e9e70-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="e9e70-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9e70-125">**Lync/Skype for Business基本客户端**</span><span class="sxs-lookup"><span data-stu-id="e9e70-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="e9e70-126">不支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-126">Not supported</span></span> |<span data-ttu-id="e9e70-127">不支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-127">Not supported</span></span>
|<span data-ttu-id="e9e70-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="e9e70-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="e9e70-129">支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-129">Supported</span></span>| <span data-ttu-id="e9e70-130">支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-130">Supported</span></span>|
|<span data-ttu-id="e9e70-131">**2016 Skype for Business 2016 年 1 月**</span><span class="sxs-lookup"><span data-stu-id="e9e70-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="e9e70-132">支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-132">Supported</span></span>| <span data-ttu-id="e9e70-133">支持</span><span class="sxs-lookup"><span data-stu-id="e9e70-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="e9e70-134">许可要求</span><span class="sxs-lookup"><span data-stu-id="e9e70-134">Licensing requirements</span></span>

<span data-ttu-id="e9e70-135">**EnterpriseE3 许可方案**</span><span class="sxs-lookup"><span data-stu-id="e9e70-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="e9e70-136">**许可证**</span><span class="sxs-lookup"><span data-stu-id="e9e70-136">**License**</span></span>|<span data-ttu-id="e9e70-137">**客户端**</span><span class="sxs-lookup"><span data-stu-id="e9e70-137">**Clients**</span></span>|<span data-ttu-id="e9e70-138">**注释**</span><span class="sxs-lookup"><span data-stu-id="e9e70-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9e70-139">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="e9e70-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e9e70-140">Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="e9e70-141">Skype for Business 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="e9e70-142">Skype for Business基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="e9e70-143">对于 Mac 客户端，您可以委派呼叫，但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="e9e70-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="e9e70-144">Enterprise具有 Office 365 电话系统 + Office 365 xCalling 计划的 E3</span><span class="sxs-lookup"><span data-stu-id="e9e70-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="e9e70-145">Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="e9e70-146">Skype for Business 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="e9e70-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="e9e70-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="e9e70-148">Skype for Business基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="e9e70-149">对于 Mac 客户端，您可以委派呼叫，但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="e9e70-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="e9e70-150">**EnterpriseE5 许可方案**</span><span class="sxs-lookup"><span data-stu-id="e9e70-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="e9e70-151">**许可证**</span><span class="sxs-lookup"><span data-stu-id="e9e70-151">**License**</span></span>|<span data-ttu-id="e9e70-152">**客户端**</span><span class="sxs-lookup"><span data-stu-id="e9e70-152">**Clients**</span></span>|<span data-ttu-id="e9e70-153">**注释**</span><span class="sxs-lookup"><span data-stu-id="e9e70-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9e70-154">EnterpriseE5</span><span class="sxs-lookup"><span data-stu-id="e9e70-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="e9e70-155">Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="e9e70-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="e9e70-156">Skype for Business 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="e9e70-157">Skype for Business基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="e9e70-158">对于 Mac 客户端，您可以委派呼叫，但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="e9e70-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="e9e70-159">EnterpriseE5 加Office 365呼叫计划</span><span class="sxs-lookup"><span data-stu-id="e9e70-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="e9e70-160">2016 Mac版Skype for Business 2016 年 1 月</span><span class="sxs-lookup"><span data-stu-id="e9e70-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="e9e70-161">Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="e9e70-162">Skype for Business 2016 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9e70-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="e9e70-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="e9e70-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="e9e70-164">Skype for Business基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="e9e70-165">对于 Mac 客户端，您可以委派呼叫，但不能委派会议。</span><span class="sxs-lookup"><span data-stu-id="e9e70-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="e9e70-166">设置并验证委派</span><span class="sxs-lookup"><span data-stu-id="e9e70-166">Set up and verify delegation</span></span>

<span data-ttu-id="e9e70-167">若要设置 Skype for Business Online 委派，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e9e70-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="e9e70-168">对于 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="e9e70-168">For Windows clients</span></span>

 <span data-ttu-id="e9e70-169">**"呼叫转发"选项卡**</span><span class="sxs-lookup"><span data-stu-id="e9e70-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="e9e70-170">选择 **"工具**  >  **选项**  >  **""呼叫设置"。**</span><span class="sxs-lookup"><span data-stu-id="e9e70-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="e9e70-171">选择 **"编辑我的代理人成员"。**</span><span class="sxs-lookup"><span data-stu-id="e9e70-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="e9e70-172">选择 **"添加**"，选择要添加的代理人，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e9e70-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="e9e70-173">**"无呼叫转发"选项卡**</span><span class="sxs-lookup"><span data-stu-id="e9e70-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="e9e70-174">在Outlook，选择 **"文件**  >  **帐户"设置"**  >  **代理访问添加**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="e9e70-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="e9e70-175">找到并添加要成为代理人的人的姓名。</span><span class="sxs-lookup"><span data-stu-id="e9e70-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="e9e70-176">选择" **日历** "菜单，然后选择"编辑器 **(，** 然后即可读取、创建和修改) 。</span><span class="sxs-lookup"><span data-stu-id="e9e70-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="e9e70-177">对于 Mac 客户端 - Lync</span><span class="sxs-lookup"><span data-stu-id="e9e70-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="e9e70-178">**"呼叫转发"选项卡**</span><span class="sxs-lookup"><span data-stu-id="e9e70-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="e9e70-179">如果客户端没有包含"编辑我的代理人成员"链接的"呼叫转发"选项卡，并且代理人位于 Mac 计算机上，则代理人必须登录到基于 Windows 的计算机才能设置委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="e9e70-180">这是因为 Mac 客户端无法建立 MAPI 连接，这是建立从 Skype for Business 委派Outlook。</span><span class="sxs-lookup"><span data-stu-id="e9e70-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="e9e70-181">验证成功</span><span class="sxs-lookup"><span data-stu-id="e9e70-181">Verify success</span></span>

<span data-ttu-id="e9e70-182">如果设置成功，代理人应看到"你已添加为 < 姓名>的代理人消息，并且"我管理呼叫的人 **"** 组已创建。 </span><span class="sxs-lookup"><span data-stu-id="e9e70-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="e9e70-183">委派者应会看到"代理人 **"** 组已创建。</span><span class="sxs-lookup"><span data-stu-id="e9e70-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9e70-184">委派权限通常在设置过程的 30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="e9e70-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="e9e70-185">但是，此过程可能需要 24 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="e9e70-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="e9e70-186">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e9e70-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="e9e70-187">常见问题</span><span class="sxs-lookup"><span data-stu-id="e9e70-187">Common issues</span></span>

- > <span data-ttu-id="e9e70-188">**问题 1** 委派者从代理客户端中删除代理人后，代理人条目将继续显示在"我管理呼叫人员"Outlook组中。</span><span class="sxs-lookup"><span data-stu-id="e9e70-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="e9e70-189">**解决方法 1** 在Skype for Business，右键单击"代理人"组中代理人，然后选择"**从组中删除"。** </span><span class="sxs-lookup"><span data-stu-id="e9e70-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="e9e70-190">**问题 2** 通过代理客户端授予代理访问权限Outlook，确认消息和"我管理呼叫的人"组不会显示给代理人。</span><span class="sxs-lookup"><span data-stu-id="e9e70-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="e9e70-191">**解决方法 2** 从客户端中删除Outlook，等待大约 15 分钟进行复制，然后再次添加委托。</span><span class="sxs-lookup"><span data-stu-id="e9e70-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="e9e70-192">其他常见问题</span><span class="sxs-lookup"><span data-stu-id="e9e70-192">Other common issues</span></span>

- <span data-ttu-id="e9e70-193">如果超过 25 个委派者与 25 个代理人的阈值，则委派不起作用。</span><span class="sxs-lookup"><span data-stu-id="e9e70-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="e9e70-194">不支持Skype for Business基本客户端。</span><span class="sxs-lookup"><span data-stu-id="e9e70-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9e70-195">如果安装基本Skype for Business客户端，它将删除并中断委派。</span><span class="sxs-lookup"><span data-stu-id="e9e70-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="e9e70-196">如果 **MAPI 状态** 值不正常 **，** 请确保 SIP 和 **SMTP** 值匹配。</span><span class="sxs-lookup"><span data-stu-id="e9e70-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9e70-197">首次启动映射和映射后，可能需要几分钟时间才能将MAPI 状态显示为Skype for Business Outlook。</span><span class="sxs-lookup"><span data-stu-id="e9e70-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="e9e70-198">不支持创建安全组并添加该安全组的委派权限。</span><span class="sxs-lookup"><span data-stu-id="e9e70-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="e9e70-199">MAPI 不可用。</span><span class="sxs-lookup"><span data-stu-id="e9e70-199">MAPI is unavailable.</span></span> <span data-ttu-id="e9e70-200">请参阅[2016 客户端中的Skype for Business MAPI 不可用"错误](https://support.microsoft.com/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="e9e70-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="e9e70-201">无法Exchange Online客户端访问Skype for Business邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9e70-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="e9e70-202">如果发生这种情况，[请运行Outlook](https://testconnectivity.microsoft.com/)测试以确保它通过。</span><span class="sxs-lookup"><span data-stu-id="e9e70-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e9e70-203">相关主题</span><span class="sxs-lookup"><span data-stu-id="e9e70-203">Related topics</span></span>
[<span data-ttu-id="e9e70-204">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e9e70-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e9e70-205">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="e9e70-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

---
title: Skype for Business Online 委派设置和疑难解答
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 本文介绍如何设置和 Skype 疑难解答业务联机委派。 本文为您提供了有关安装程序建议、 最佳实践和故障排除步骤指南。
ms.openlocfilehash: e3131b28be1ad01e0965b2739dc152a627826d5e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546672"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="1dd48-104">Skype for Business Online 委派设置和疑难解答</span><span class="sxs-lookup"><span data-stu-id="1dd48-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="1dd48-105">本文介绍如何设置和 Skype 疑难解答业务联机委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="1dd48-106">本文为您提供了有关安装程序建议、 最佳实践和故障排除步骤指南。</span><span class="sxs-lookup"><span data-stu-id="1dd48-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="1dd48-107">准则和要求</span><span class="sxs-lookup"><span data-stu-id="1dd48-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="1dd48-108">委派的指南</span><span class="sxs-lookup"><span data-stu-id="1dd48-108">Guidelines for delegation</span></span>

<span data-ttu-id="1dd48-109">设置并获取正常工作的委派取决于您遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="1dd48-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="1dd48-110">您必须使用最新的更新业务 2015年完整客户端的 Skype 或 Skype for Business 2016 完整客户端。</span><span class="sxs-lookup"><span data-stu-id="1dd48-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="1dd48-111">您必须使用 Outlook 2013 客户端使用最新更新或 Outlook 2016 客户端。</span><span class="sxs-lookup"><span data-stu-id="1dd48-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="1dd48-112">请确保 delegator 和代理计算机上具有一个 Outlook 邮件配置文件的主或的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="1dd48-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="1dd48-113">该邮件配置文件应包含只有一个帐户。</span><span class="sxs-lookup"><span data-stu-id="1dd48-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="1dd48-114">Skype for Business 的代理者和代理人应联机用户。</span><span class="sxs-lookup"><span data-stu-id="1dd48-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="1dd48-115">此外，每个帐户必须同时 Online 或同时为本地 Exchange 服务器邮箱。</span><span class="sxs-lookup"><span data-stu-id="1dd48-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="1dd48-116">Delegator 和代理人都应使用相同的主要版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="1dd48-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="1dd48-117">**EnableExchangeDelegateSync**属性值应设置为**true**的客户端策略。</span><span class="sxs-lookup"><span data-stu-id="1dd48-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="1dd48-118">您可以通过运行中的业务 Online PowerShell 模块 Skype **Get-csclientpolicy** cmdlet 来验证此设置。</span><span class="sxs-lookup"><span data-stu-id="1dd48-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="1dd48-119">Delegator 和代理人必须登录到 Skype 商业和 Outlook 同时在不同的工作站上。</span><span class="sxs-lookup"><span data-stu-id="1dd48-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="1dd48-120">共享的邮箱不支持 Skype 业务联机委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="1dd48-121">这是因为共享的邮箱不具有**sendonbehalf**访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="1dd48-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="1dd48-122">Skype 业务客户端版本支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-122">Skype for Business client version support</span></span>

||<span data-ttu-id="1dd48-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="1dd48-123">**Outlook 2013**</span></span>|<span data-ttu-id="1dd48-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="1dd48-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dd48-125">**Lync/Skype 业务基本客户端**</span><span class="sxs-lookup"><span data-stu-id="1dd48-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="1dd48-126">不支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-126">Not supported</span></span> |<span data-ttu-id="1dd48-127">不支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-127">Not supported</span></span>
|<span data-ttu-id="1dd48-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="1dd48-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="1dd48-129">支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-129">Supported</span></span>| <span data-ttu-id="1dd48-130">支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-130">Supported</span></span>|
|<span data-ttu-id="1dd48-131">**Skype 业务 2016 年**</span><span class="sxs-lookup"><span data-stu-id="1dd48-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="1dd48-132">支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-132">Supported</span></span>| <span data-ttu-id="1dd48-133">支持</span><span class="sxs-lookup"><span data-stu-id="1dd48-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="1dd48-134">许可要求</span><span class="sxs-lookup"><span data-stu-id="1dd48-134">Licensing requirements</span></span>

<span data-ttu-id="1dd48-135">**企业版 E3 授权方案**</span><span class="sxs-lookup"><span data-stu-id="1dd48-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="1dd48-136">**许可证**</span><span class="sxs-lookup"><span data-stu-id="1dd48-136">**License**</span></span>|<span data-ttu-id="1dd48-137">**客户端**</span><span class="sxs-lookup"><span data-stu-id="1dd48-137">**Clients**</span></span>|<span data-ttu-id="1dd48-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="1dd48-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dd48-139">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="1dd48-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="1dd48-140">用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)</span><span class="sxs-lookup"><span data-stu-id="1dd48-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="1dd48-141">用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype</span><span class="sxs-lookup"><span data-stu-id="1dd48-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="1dd48-142">Skype 业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="1dd48-143">Mac 客户端，您可以委派呼叫，但并非会议。</span><span class="sxs-lookup"><span data-stu-id="1dd48-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="1dd48-144">与 Office 365 电话系统 + Office 365 xCalling 计划的企业版 E3</span><span class="sxs-lookup"><span data-stu-id="1dd48-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="1dd48-145">用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)</span><span class="sxs-lookup"><span data-stu-id="1dd48-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="1dd48-146">用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype</span><span class="sxs-lookup"><span data-stu-id="1dd48-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="1dd48-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="1dd48-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="1dd48-148">Skype 业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="1dd48-149">Mac 客户端，您可以委派呼叫，但并非会议。</span><span class="sxs-lookup"><span data-stu-id="1dd48-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="1dd48-150">**企业 E5 授权方案**</span><span class="sxs-lookup"><span data-stu-id="1dd48-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="1dd48-151">**许可证**</span><span class="sxs-lookup"><span data-stu-id="1dd48-151">**License**</span></span>|<span data-ttu-id="1dd48-152">**客户端**</span><span class="sxs-lookup"><span data-stu-id="1dd48-152">**Clients**</span></span>|<span data-ttu-id="1dd48-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="1dd48-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dd48-154">企业 E5</span><span class="sxs-lookup"><span data-stu-id="1dd48-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="1dd48-155">用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)。</span><span class="sxs-lookup"><span data-stu-id="1dd48-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="1dd48-156">用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype</span><span class="sxs-lookup"><span data-stu-id="1dd48-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="1dd48-157">Skype 业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="1dd48-158">Mac 客户端，您可以委派呼叫，但并非会议。</span><span class="sxs-lookup"><span data-stu-id="1dd48-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="1dd48-159">企业 E5 以及 Office 365 呼叫计划</span><span class="sxs-lookup"><span data-stu-id="1dd48-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="1dd48-160">Skype for Mac 2016 年 Business</span><span class="sxs-lookup"><span data-stu-id="1dd48-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="1dd48-161">用于 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)</span><span class="sxs-lookup"><span data-stu-id="1dd48-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="1dd48-162">用于 Outlook 2013 或 Outlook 2016 业务 2016年的 Skype</span><span class="sxs-lookup"><span data-stu-id="1dd48-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="1dd48-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="1dd48-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="1dd48-164">Skype 业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="1dd48-165">Mac 客户端，您可以委派呼叫，但并非会议。</span><span class="sxs-lookup"><span data-stu-id="1dd48-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="1dd48-166">设置和验证委派</span><span class="sxs-lookup"><span data-stu-id="1dd48-166">Set up and verify delegation</span></span>

<span data-ttu-id="1dd48-167">若要设置 Skype 业务联机委派，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="1dd48-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="1dd48-168">Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="1dd48-168">For Windows clients</span></span>

 <span data-ttu-id="1dd48-169">**呼叫转接选项卡**</span><span class="sxs-lookup"><span data-stu-id="1dd48-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="1dd48-170">选择**工具** > **选项** > **呼叫转接设置**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="1dd48-171">选择**编辑我的代理人成员**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="1dd48-172">选择**添加**，请选择您要添加的代理人，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="1dd48-173">**没有呼叫转移选项卡**</span><span class="sxs-lookup"><span data-stu-id="1dd48-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="1dd48-174">在 Outlook 中，选择**文件** > **帐户设置** > **代理访问** > **添加**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="1dd48-175">找到并添加要委派的人员的名称。</span><span class="sxs-lookup"><span data-stu-id="1dd48-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="1dd48-176">选择**日历**菜单，然后选择**编辑器 （可以读取、 创建和修改的项目）**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="1dd48-177">For Mac 客户端的 Lync</span><span class="sxs-lookup"><span data-stu-id="1dd48-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="1dd48-178">**呼叫转接选项卡**</span><span class="sxs-lookup"><span data-stu-id="1dd48-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="1dd48-179">如果客户端没有**呼叫转接**选项卡，具有**编辑我的代理人成员**链接，并且 delegator 位于是 Mac 计算机，代理者必须登录到基于 Windows 的计算机才能设置委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="1dd48-180">这是因为 Mac 客户端无法发出 MAPI 连接，这是 Outlook 中的业务委派建立 Skype 的要求。</span><span class="sxs-lookup"><span data-stu-id="1dd48-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="1dd48-181">验证成功</span><span class="sxs-lookup"><span data-stu-id="1dd48-181">Verify success</span></span>

<span data-ttu-id="1dd48-182">如果成功安装，代理人应该会看到**已将您添加为 < 名称 > 的代理人**消息并且还创建**我管理呼叫的人员**组中。</span><span class="sxs-lookup"><span data-stu-id="1dd48-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="1dd48-183">Delegator 应看到已创建**代理人**组。</span><span class="sxs-lookup"><span data-stu-id="1dd48-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd48-184">委派权限通常显示在安装过程的 30 分钟内。</span><span class="sxs-lookup"><span data-stu-id="1dd48-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="1dd48-185">但是，此过程可能需要 24 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="1dd48-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="1dd48-186">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1dd48-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="1dd48-187">常见问题</span><span class="sxs-lookup"><span data-stu-id="1dd48-187">Common issues</span></span>

- > <span data-ttu-id="1dd48-188">**问题 1**该委托条目继续 delegator 已从 Outlook 客户端删除代理人后，出现在**我管理呼叫的人员**组中。</span><span class="sxs-lookup"><span data-stu-id="1dd48-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="1dd48-189">**解决方案 1**在业务客户端 Skype，右键单击**代理人**组中的委托，然后选择**从组中删除**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="1dd48-190">**问题 2**代理访问授予通过 Outlook 客户端后，确认消息和**我管理呼叫的人员**组中都不显示该委托。</span><span class="sxs-lookup"><span data-stu-id="1dd48-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="1dd48-191">**解决方案 2**从 Outlook 客户端中删除委派和等待 15 分钟的时间进行复制，然后再次添加代理。</span><span class="sxs-lookup"><span data-stu-id="1dd48-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="1dd48-192">其他常见的问题</span><span class="sxs-lookup"><span data-stu-id="1dd48-192">Other common issues</span></span>

- <span data-ttu-id="1dd48-193">如果超过 25 委派人和 25 代理人的阈值，委派不起作用。</span><span class="sxs-lookup"><span data-stu-id="1dd48-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="1dd48-194">业务基本客户端 Skype 不受支持。</span><span class="sxs-lookup"><span data-stu-id="1dd48-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1dd48-195">如果您安装 Skype 业务基本客户端，它将删除和中断委派。</span><span class="sxs-lookup"><span data-stu-id="1dd48-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="1dd48-196">如果**MAPI**状态值不是**确定**，请确保**SIP**和**SMTP**值匹配。</span><span class="sxs-lookup"><span data-stu-id="1dd48-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1dd48-197">可能需要几分钟，以便 MAPI 状态后业务和 Outlook 的首次启动 Skype 显示为**确定**。</span><span class="sxs-lookup"><span data-stu-id="1dd48-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="1dd48-198">创建安全组并添加委派权限的安全组不受支持。</span><span class="sxs-lookup"><span data-stu-id="1dd48-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="1dd48-199">MAPI 不可用。</span><span class="sxs-lookup"><span data-stu-id="1dd48-199">MAPI is unavailable.</span></span> <span data-ttu-id="1dd48-200">请参阅[Skype 业务 2016年客户端中的"MAPI 不可用"错误](https://support.microsoft.com/en-us/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="1dd48-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="1dd48-201">Exchange Online 邮箱不能通过业务客户端 Skype 访问。</span><span class="sxs-lookup"><span data-stu-id="1dd48-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="1dd48-202">如果发生这种情况，运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它可以通过。</span><span class="sxs-lookup"><span data-stu-id="1dd48-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1dd48-203">相关主题</span><span class="sxs-lookup"><span data-stu-id="1dd48-203">Related topics</span></span>
[<span data-ttu-id="1dd48-204">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1dd48-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1dd48-205">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="1dd48-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

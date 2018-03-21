---
title: "设置和疑难解答 Skype 的在线业务委派"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "本文介绍如何设置和疑难解答 Skype 的在线业务委派。 这篇文章为您提供了安装程序的建议、 最佳做法以及故障排除步骤的指南。"
ms.openlocfilehash: 36dde5040471979a95be1ec8c9e0eb30fef739de
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="bcb4b-104">设置和疑难解答 Skype 的在线业务委派</span><span class="sxs-lookup"><span data-stu-id="bcb4b-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="bcb4b-105">本文介绍如何设置和疑难解答 Skype 的在线业务委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="bcb4b-106">这篇文章为您提供了安装程序的建议、 最佳做法以及故障排除步骤的指南。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="bcb4b-107">一些原则和要求</span><span class="sxs-lookup"><span data-stu-id="bcb4b-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="bcb4b-108">委派的准则</span><span class="sxs-lookup"><span data-stu-id="bcb4b-108">Guidelines for delegation</span></span>

<span data-ttu-id="bcb4b-109">设置和获取委派正常工作取决于您遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="bcb4b-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="bcb4b-110">您必须使用与最新的更新业务 2015年完整客户端为 Skype 或 Skype 业务 2016年完整客户端。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="bcb4b-111">您必须使用最新的更新的 Outlook 2013 客户机或 Outlook 2016 客户端。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="bcb4b-112">请确保代理者和代理的计算机具有一个 Outlook 邮件配置文件的主或默认的配置文件。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="bcb4b-113">该邮件配置文件应该包含一个帐户。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="bcb4b-114">Skype 的代理者和代理的业务应该是在线用户。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="bcb4b-115">此外，每个帐户必须同时联机或同时为内部部署的 Exchange Server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="bcb4b-116">代理者和委托应使用 Outlook 的相同主要版本号。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="bcb4b-117">**EnableExchangeDelegateSync**属性值应设置为**true**的客户端策略中。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="bcb4b-118">您可以通过 Skype 业务在线 PowerShell 模块中运行**Get CSClientPolicy** cmdlet 验证此设置。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="bcb4b-119">代理者和委托必须登录到 Skype 业务和 Outlook 在同一时间在不同的工作站上。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="bcb4b-120">共享的邮箱不支持 Skype 的在线业务委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="bcb4b-121">这是因为共享的邮箱没有**sendonbehalf**的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="bcb4b-122">Skype 业务客户端版本支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-122">Skype for Business client version support</span></span>

||<span data-ttu-id="bcb4b-123">**Outlook 的 2013 年**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-123">**Outlook 2013**</span></span>|<span data-ttu-id="bcb4b-124">**Outlook 的 2016 年**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bcb4b-125">**Lync/Skype 业务基本客户端**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="bcb4b-126">不受支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-126">Not supported</span></span> |<span data-ttu-id="bcb4b-127">不受支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-127">Not supported</span></span>
|<span data-ttu-id="bcb4b-128">**Skype 的业务 2015**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="bcb4b-129">支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-129">Supported</span></span>| <span data-ttu-id="bcb4b-130">支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-130">Supported</span></span>|
|<span data-ttu-id="bcb4b-131">**Skype 业务 2016 年**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="bcb4b-132">支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-132">Supported</span></span>| <span data-ttu-id="bcb4b-133">支持</span><span class="sxs-lookup"><span data-stu-id="bcb4b-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="bcb4b-134">授权要求</span><span class="sxs-lookup"><span data-stu-id="bcb4b-134">Licensing requirements</span></span>

<span data-ttu-id="bcb4b-135">**企业 E3 授权方案**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="bcb4b-136">**许可证**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-136">**License**</span></span>|<span data-ttu-id="bcb4b-137">**客户端**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-137">**Clients**</span></span>|<span data-ttu-id="bcb4b-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bcb4b-139">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="bcb4b-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="bcb4b-140">Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bcb4b-141">Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bcb4b-142">Skype 的业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bcb4b-143">对于 Mac 客户端，可以委托调用，但没有会议。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bcb4b-144">企业 E3 Office 365 电话系统 + Office 365 xCalling 计划</span><span class="sxs-lookup"><span data-stu-id="bcb4b-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="bcb4b-145">Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bcb4b-146">Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bcb4b-147">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bcb4b-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bcb4b-148">Skype 的业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bcb4b-149">对于 Mac 客户端，可以委托调用，但没有会议。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="bcb4b-150">**企业 E5 授权方案**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="bcb4b-151">**许可证**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-151">**License**</span></span>|<span data-ttu-id="bcb4b-152">**客户端**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-152">**Clients**</span></span>|<span data-ttu-id="bcb4b-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bcb4b-154">企业 E5</span><span class="sxs-lookup"><span data-stu-id="bcb4b-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="bcb4b-155">使用 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="bcb4b-156">Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bcb4b-157">Skype 的业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bcb4b-158">对于 Mac 客户端，可以委托调用，但没有会议。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bcb4b-159">企业 E5 加上 Office 365 电话计划</span><span class="sxs-lookup"><span data-stu-id="bcb4b-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="bcb4b-160">Skype 业务 Mac 2016 年的</span><span class="sxs-lookup"><span data-stu-id="bcb4b-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="bcb4b-161">Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bcb4b-162">Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bcb4b-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bcb4b-163">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bcb4b-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bcb4b-164">Skype 的业务基本客户端不支持委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bcb4b-165">对于 Mac 客户端，可以委托调用，但没有会议。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="bcb4b-166">设置并验证委派</span><span class="sxs-lookup"><span data-stu-id="bcb4b-166">Set up and verify delegation</span></span>

<span data-ttu-id="bcb4b-167">若要设置 Skype 的在线业务委派，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bcb4b-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="bcb4b-168">对于 Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="bcb4b-168">For Windows clients</span></span>

 <span data-ttu-id="bcb4b-169">**电话转接选项卡**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bcb4b-170">选择**工具** > **选项** > **来电转接设置**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="bcb4b-171">选择**编辑我的代理成员**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="bcb4b-172">选择**添加**，选择您想添加的委托，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="bcb4b-173">**没有来电转接选项卡**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bcb4b-174">在 Outlook 中，选择**文件** > **帐户设置** > **代理访问** > **添加**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="bcb4b-175">找到并添加要委托的人的名称。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="bcb4b-176">选择**日历**菜单，然后选择**编辑器 （可以阅读、 创建和修改项目）**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="bcb4b-177">对于 Mac 客户-Lync</span><span class="sxs-lookup"><span data-stu-id="bcb4b-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="bcb4b-178">**电话转接选项卡**</span><span class="sxs-lookup"><span data-stu-id="bcb4b-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="bcb4b-179">如果客户端没有**来电转接**的选项卡的**编辑我的代理成员**链接，并代理者位于 Mac 计算机，代理者必须登录到基于 Windows 的计算机以设置委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="bcb4b-180">这是因为 Mac 客户端无法使 MAPI 连接，这是建立从 Outlook 的业务委派的 Skype 的要求。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="bcb4b-181">验证成功</span><span class="sxs-lookup"><span data-stu-id="bcb4b-181">Verify success</span></span>

<span data-ttu-id="bcb4b-182">如果安装成功，代理应该看到**已添加为 < 名称 > 的代理人**消息，并显示创建**人我呼叫管理的**组。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="bcb4b-183">代理者应该看到**委托**组已创建。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bcb4b-184">委派权限通常显示在安装过程的 30 分钟内。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="bcb4b-185">但是，此过程可能需要 24 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="bcb4b-186">疑难解答</span><span class="sxs-lookup"><span data-stu-id="bcb4b-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="bcb4b-187">常见的问题</span><span class="sxs-lookup"><span data-stu-id="bcb4b-187">Common issues</span></span>

- > <span data-ttu-id="bcb4b-188">**问题 1**委托人项继续代理者已从 Outlook 客户端中移除委托后出现的**人我呼叫管理的**组中。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="bcb4b-189">**解决方法 1**业务客户端的 Skype，在委托**代理**组中，用鼠标右键单击，然后选择**从组中删除**。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="bcb4b-190">**问题 2**通过 Outlook 客户端授予代理访问权限后，既没有确认消息，也没有**人我呼叫管理的**组将显示为委托。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="bcb4b-191">**解决方案 2**从 Outlook 客户端删除委派、 等待复制，大约 15 分钟，然后再次添加该委托。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="bcb4b-192">其他常见问题</span><span class="sxs-lookup"><span data-stu-id="bcb4b-192">Other common issues</span></span>

- <span data-ttu-id="bcb4b-193">如果超出 25 日委派人和 25 委托的阈值，委派不起作用。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="bcb4b-194">Skype 的业务基本客户端不支持。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcb4b-195">如果您安装 Skype 业务基本客户端，它将移除并中断的委派。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="bcb4b-196">如果**MAPI Status**值不**确定**，请确保**SIP**和**SMTP**值匹配。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcb4b-197">它可能需要几分钟的 MAPI 状态显示为**确定**后第一次对业务和 Outlook 启动 Skype。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="bcb4b-198">不支持创建安全组并添加该安全组委派权限。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="bcb4b-199">MAPI 是不可用的。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-199">MAPI is unavailable.</span></span> <span data-ttu-id="bcb4b-200">看到[Skype 业务 2016年客户端在"MAPI 不可用"错误消息](https://support.microsoft.com/en-us/help/3147130)。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="bcb4b-201">联机 Exchange 邮箱并不是可以通过 Skype 业务客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="bcb4b-202">如果发生这种情况，运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它可以通过。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bcb4b-203">相关主题</span><span class="sxs-lookup"><span data-stu-id="bcb4b-203">Related topics</span></span>
[<span data-ttu-id="bcb4b-204">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bcb4b-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="bcb4b-205">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="bcb4b-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="bcb4b-206">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="bcb4b-206">Feedback?</span></span>
<span data-ttu-id="bcb4b-207">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="bcb4b-207">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
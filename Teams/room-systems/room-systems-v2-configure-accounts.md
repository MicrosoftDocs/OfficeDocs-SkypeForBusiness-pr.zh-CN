---
title: 为 Microsoft 团队聊天室配置帐户
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 阅读本主题, 了解如何在 Exchange 和 Skype for Business 中配置 Microsoft 团队聊天室的帐户。
ms.openlocfilehash: d405214660e34c9cda6e54f0198d0d4477aace9b
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427950"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="7a48a-103">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="7a48a-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="7a48a-104">阅读本主题, 了解 Microsoft 团队聊天室以及它与 Exchange 和 Skype for business 的集成方式。</span><span class="sxs-lookup"><span data-stu-id="7a48a-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="7a48a-105">本主题介绍如何在 Microsoft Exchange 和 Skype for Business 中创建 Microsoft 团队聊天室使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="7a48a-106">有关 Microsoft 团队聊天室设备的部署说明, 请在[配置 Microsoft 团队聊天室控制台](console.md)中介绍。</span><span class="sxs-lookup"><span data-stu-id="7a48a-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="7a48a-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="7a48a-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="7a48a-108">联机部署: 你的组织的环境完全部署在 Office 365 上。</span><span class="sxs-lookup"><span data-stu-id="7a48a-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="7a48a-109">有关详细信息, 请参阅[通过 Office 365 部署 Microsoft 团队聊天室](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="7a48a-110">本地部署: 你的组织具有其控制的服务器, 其中托管了 Active Directory、Exchange 和 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="7a48a-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="7a48a-111">有关详细信息, 请参阅[用 Skype For Business 服务器部署 Microsoft 团队聊天室](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="7a48a-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="7a48a-112">混合部署: 你的组织具有混合服务, 其中一些托管在本地, 而某些托管联机通过 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7a48a-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="7a48a-113">在 Microsoft 团队聊天室中, 支持以下混合方案:</span><span class="sxs-lookup"><span data-stu-id="7a48a-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="7a48a-114">与本地 Skype for business 服务器的 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7a48a-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="7a48a-115">有关详细信息, 请参阅[通过 Exchange Online (混合) 部署 Microsoft 团队聊天室](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="7a48a-116">与 Microsoft 团队或 Skype for business Online 的本地 Exchange。</span><span class="sxs-lookup"><span data-stu-id="7a48a-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="7a48a-117">有关详细信息, 请参阅[通过 Exchange on on-premises (混合) 部署 Microsoft 团队聊天室](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="7a48a-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="7a48a-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="7a48a-119">需要在 Active Directory、Exchange 和 Skype for Business 中为 Microsoft 团队会议室分配 "设备帐户"。</span><span class="sxs-lookup"><span data-stu-id="7a48a-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="7a48a-120">该帐户用于访问其会议日历, 建立 Microsoft 团队或 Skype for business 连接。</span><span class="sxs-lookup"><span data-stu-id="7a48a-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="7a48a-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="7a48a-122">Microsoft 团队聊天室将能够加入该会议并向会议与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="7a48a-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a48a-123">如果没有设备帐户, 这些功能都将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7a48a-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="7a48a-124">每个设备帐户对单个 Microsoft 团队聊天室设备而言都是唯一的, 并且需要一些设置:</span><span class="sxs-lookup"><span data-stu-id="7a48a-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="7a48a-125">必须正确配置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="7a48a-126">你的基础结构必须配置为允许 Microsoft 团队聊天室验证设备帐户, 并访问相应的 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="7a48a-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7a48a-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="7a48a-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="7a48a-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="7a48a-128">Ideally, account preparation is started two to three weeks before installation.</span></span> <span data-ttu-id="7a48a-129">在混合环境中, 用于 Microsoft 团队聊天室的帐户必须在 AAD 同步中启用密码同步, 因为 Microsoft 团队聊天室身份验证需要 Office 365 身份验证。</span><span class="sxs-lookup"><span data-stu-id="7a48a-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in AAD Sync because Microsoft Teams Rooms authentication requires Office 365 authentication.</span></span>
  
<span data-ttu-id="7a48a-130">你可以将设备帐户视为用户将其识别为会议室或会议空间的帐户的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-130">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="7a48a-131">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="7a48a-131">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="7a48a-132">为了最有效地使用 Microsoft 团队聊天室, 您可以使用分配给每个团队聊天室的设备帐户执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="7a48a-132">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="7a48a-133">如果你已为安装 Microsoft 团队聊天室的会议空间设置了资源邮箱帐户, 则可以将该资源帐户更改为设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-133">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="7a48a-134">完成后, 你需要做的就是将设备帐户添加到 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="7a48a-134">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7a48a-135">请参阅下面提供的设备帐户设置示例。</span><span class="sxs-lookup"><span data-stu-id="7a48a-135">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="7a48a-136">有了其他配置, 使用 Microsoft Azure 监视器可以进行远程管理, 如使用[Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)、使用[Azure 监视器部署 microsoft 团队会议室管理](azure-monitor-deploy.md)和[通过 Azure 监视器管理 Microsoft 团队聊天室设备](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-136">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="7a48a-137">基本配置</span><span class="sxs-lookup"><span data-stu-id="7a48a-137">Basic configuration</span></span>

<span data-ttu-id="7a48a-138">这些属性表示用于处理 Microsoft 团队聊天室的设备帐户的最低配置。</span><span class="sxs-lookup"><span data-stu-id="7a48a-138">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="7a48a-139">您的设备帐户可能需要进一步设置。</span><span class="sxs-lookup"><span data-stu-id="7a48a-139">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="7a48a-140">**属性**</span><span class="sxs-lookup"><span data-stu-id="7a48a-140">**Property**</span></span>|<span data-ttu-id="7a48a-141">**用途**</span><span class="sxs-lookup"><span data-stu-id="7a48a-141">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a48a-142">Exchange 邮箱 (Exchange 2013 SP1 或更高版本, 或 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="7a48a-142">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="7a48a-143">启用具有 Exchange 邮箱的帐户将使设备帐户能够接收和发送邮件和会议请求, 并在 Microsoft 团队聊天室设备上显示会议日历。</span><span class="sxs-lookup"><span data-stu-id="7a48a-143">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7a48a-144">Microsoft 团队聊天室邮箱必须是会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="7a48a-144">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="7a48a-145">已启用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7a48a-145">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="7a48a-146">必须启用 Skype for Business 才能使用各种会议功能, 如视频通话、即时消息和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="7a48a-146">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="7a48a-147">Skype for business Online 和 Skype for business 服务器均受支持。</span><span class="sxs-lookup"><span data-stu-id="7a48a-147">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="7a48a-148">已启用密码</span><span class="sxs-lookup"><span data-stu-id="7a48a-148">Password-enabled</span></span>  <br/> |<span data-ttu-id="7a48a-149">必须使用密码启用设备帐户, 或者不能通过 Exchange 或 Skype for business 服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7a48a-149">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="7a48a-150">高级配置</span><span class="sxs-lookup"><span data-stu-id="7a48a-150">Advanced configuration</span></span>

<span data-ttu-id="7a48a-151">虽然基本配置的属性将允许在简单环境中设置设备帐户, 但你的环境可能对必须满足的目录帐户具有其他限制, 以便 Microsoft 团队聊天室成功使用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-151">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="7a48a-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="7a48a-152">**Property**</span></span>|<span data-ttu-id="7a48a-153">**用途**</span><span class="sxs-lookup"><span data-stu-id="7a48a-153">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a48a-154">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="7a48a-154">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="7a48a-155">Exchange 和 Skype for business 服务器可能都需要证书。</span><span class="sxs-lookup"><span data-stu-id="7a48a-155">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="7a48a-156">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="7a48a-156">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="7a48a-157">设置设备帐户最简单的方法是使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="7a48a-157">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7a48a-158">Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105), 该脚本将帮助创建新的设备帐户, 或验证你拥有的现有资源帐户, 以帮助你将它们转换为兼容的 Microsoft 团队聊天室设备帐户。</span><span class="sxs-lookup"><span data-stu-id="7a48a-158">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="7a48a-159">如果你希望通过 Windows PowerShell cmdlet 使用 Office 365 UI, 则可以手动执行某些步骤。</span><span class="sxs-lookup"><span data-stu-id="7a48a-159">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="7a48a-160">请参阅[使用 Office 365 创建设备帐户](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-160">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a48a-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a48a-161">See also</span></span>

[<span data-ttu-id="7a48a-162">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="7a48a-162">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="7a48a-163">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="7a48a-163">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7a48a-164">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="7a48a-164">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)


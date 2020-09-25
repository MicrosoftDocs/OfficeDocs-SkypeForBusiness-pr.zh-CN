---
title: 为 Microsoft 团队聊天室配置帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 阅读本主题，了解如何在 Exchange 和 Skype for Business 中配置 Microsoft 团队聊天室的帐户。
ms.openlocfilehash: 98507b3c5fb2b2d9383bcbff6ddcbdda0de19b9f
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262479"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="2df72-103">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="2df72-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="2df72-104">阅读本主题，了解 Microsoft 团队聊天室以及它与 Exchange 和 Skype for business 的集成方式。</span><span class="sxs-lookup"><span data-stu-id="2df72-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="2df72-105">本主题介绍如何在 Microsoft Exchange 和 Skype for Business 中创建 Microsoft 团队聊天室使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="2df72-106">有关 Microsoft 团队聊天室设备的部署说明，请在 [配置 Microsoft 团队聊天室控制台](console.md)中介绍。</span><span class="sxs-lookup"><span data-stu-id="2df72-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="2df72-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="2df72-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="2df72-108">联机部署：你的组织的环境完全部署在 Microsoft 365 或 Office 365 上。</span><span class="sxs-lookup"><span data-stu-id="2df72-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2df72-109">有关详细信息，请参阅 [通过 microsoft 365 或 Office 365 部署 Microsoft 团队聊天室](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2df72-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="2df72-110">本地部署：你的组织具有其控制的服务器，其中托管了 Active Directory、Exchange 和 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="2df72-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="2df72-111">有关详细信息，请参阅 [用 Skype For Business 服务器部署 Microsoft 团队聊天室](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="2df72-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="2df72-112">混合部署：你的组织有多种服务，其中一些托管在本地，并且某些通过 Microsoft 365 或 Office 365 联机托管。</span><span class="sxs-lookup"><span data-stu-id="2df72-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2df72-113">在 Microsoft 团队聊天室中，支持以下混合方案：</span><span class="sxs-lookup"><span data-stu-id="2df72-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="2df72-114">与本地 Skype for business 服务器的 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2df72-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="2df72-115">有关详细信息，请参阅 [通过 Exchange Online (混合) 部署 Microsoft 团队聊天室 ](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2df72-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="2df72-116">与 Microsoft 团队或 Skype for business Online 的本地 Exchange。</span><span class="sxs-lookup"><span data-stu-id="2df72-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="2df72-117">有关详细信息，请参阅 [在本地 Exchange (混合) 中部署 Microsoft 团队聊天室 ](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="2df72-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="2df72-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="2df72-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="2df72-119">需要在 Active Directory、Exchange 和 Skype for Business 中为 Microsoft 团队会议室分配 "设备帐户"。</span><span class="sxs-lookup"><span data-stu-id="2df72-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="2df72-120">该帐户用于访问其会议日历，建立 Microsoft 团队或 Skype for business 连接。</span><span class="sxs-lookup"><span data-stu-id="2df72-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="2df72-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="2df72-122">Microsoft 团队聊天室将能够加入该会议并向会议与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="2df72-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2df72-123">如果没有设备帐户，这些功能都将不起作用。</span><span class="sxs-lookup"><span data-stu-id="2df72-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="2df72-124">每个设备帐户对单个 Microsoft 团队聊天室设备而言都是唯一的，并且需要一些设置：</span><span class="sxs-lookup"><span data-stu-id="2df72-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="2df72-125">必须正确配置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="2df72-126">你的基础结构必须配置为允许 Microsoft 团队聊天室验证设备帐户，并访问相应的 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="2df72-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="2df72-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="2df72-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="2df72-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="2df72-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="2df72-129">在混合环境中，用于 Microsoft 团队聊天室的帐户必须在 Azure Active Directory 中启用密码同步 (AAD) 同步，因为 Microsoft 团队聊天室身份验证需要 Microsoft 365 或 Office 365 身份验证。</span><span class="sxs-lookup"><span data-stu-id="2df72-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="2df72-130">设置帐户时，请确保帐户的 SIP 地址与 AAD 中的用户主体名称 (UPN) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="2df72-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="2df72-131">你可以将设备帐户视为用户将其识别为会议室或会议空间的帐户的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="2df72-132">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="2df72-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="2df72-133">为了最有效地使用 Microsoft 团队聊天室，您可以使用分配给每个团队聊天室的设备帐户执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="2df72-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="2df72-134">如果你已为安装 Microsoft 团队聊天室的会议空间设置了资源邮箱帐户，则可以将该资源帐户更改为设备帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="2df72-135">完成后，你需要做的就是将设备帐户添加到 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="2df72-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="2df72-136">请参阅下面提供的设备帐户设置示例。</span><span class="sxs-lookup"><span data-stu-id="2df72-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="2df72-137">有了其他配置，使用 Microsoft Azure 监视器可进行远程管理，如使用 [Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)、使用 [Azure 监视器部署 microsoft 团队聊天室管理](azure-monitor-deploy.md)和 [使用 Azure 监视器管理 microsoft 团队室设备的](azure-monitor-manage.md)相关说明。</span><span class="sxs-lookup"><span data-stu-id="2df72-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="2df72-138">基本配置</span><span class="sxs-lookup"><span data-stu-id="2df72-138">Basic configuration</span></span>

<span data-ttu-id="2df72-139">这些属性表示用于处理 Microsoft 团队聊天室的设备帐户的最低配置。</span><span class="sxs-lookup"><span data-stu-id="2df72-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="2df72-140">您的设备帐户可能需要进一步设置。</span><span class="sxs-lookup"><span data-stu-id="2df72-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="2df72-141">**属性**</span><span class="sxs-lookup"><span data-stu-id="2df72-141">**Property**</span></span>|<span data-ttu-id="2df72-142">**用途**</span><span class="sxs-lookup"><span data-stu-id="2df72-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2df72-143">Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="2df72-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="2df72-144">启用具有 Exchange 邮箱的帐户将使设备帐户能够接收和发送邮件和会议请求，并在 Microsoft 团队聊天室设备上显示会议日历。</span><span class="sxs-lookup"><span data-stu-id="2df72-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="2df72-145">Microsoft 团队聊天室邮箱必须是会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="2df72-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="2df72-146">已启用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2df72-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="2df72-147">必须启用 Skype for Business 才能使用各种会议功能，如视频通话、即时消息和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="2df72-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="2df72-148">Skype for business Online 和 Skype for business 服务器均受支持。</span><span class="sxs-lookup"><span data-stu-id="2df72-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="2df72-149">已启用密码</span><span class="sxs-lookup"><span data-stu-id="2df72-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="2df72-150">必须使用密码启用设备帐户，或者不能通过 Exchange 或 Skype for business 服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2df72-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="2df72-151">高级配置</span><span class="sxs-lookup"><span data-stu-id="2df72-151">Advanced configuration</span></span>

<span data-ttu-id="2df72-152">虽然基本配置的属性允许在简单环境中设置设备帐户，但你的环境可能对必须满足的目录帐户有其他限制，才能使 Microsoft 团队聊天室成功使用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="2df72-153">**属性**</span><span class="sxs-lookup"><span data-stu-id="2df72-153">**Property**</span></span>|<span data-ttu-id="2df72-154">**用途**</span><span class="sxs-lookup"><span data-stu-id="2df72-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2df72-155">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="2df72-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="2df72-156">Exchange 和 Skype for business 服务器可能都需要证书。</span><span class="sxs-lookup"><span data-stu-id="2df72-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="2df72-157">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="2df72-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="2df72-158">设置设备帐户最简单的方法是使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="2df72-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="2df72-159">Microsoft 提供 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、帮助创建新设备帐户或验证现有资源帐户的脚本，以帮助你将其转换为兼容的 Microsoft 团队聊天室设备帐户。</span><span class="sxs-lookup"><span data-stu-id="2df72-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="2df72-160">如果你希望在 Windows PowerShell cmdlet 上使用 Microsoft 365 或 Office 365 UI，则可以手动执行某些步骤。</span><span class="sxs-lookup"><span data-stu-id="2df72-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="2df72-161">请参阅 [使用 Microsoft 365 或 Office 365 创建设备帐户](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="2df72-161">See [Creating a device account using Microsoft 365 or Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2df72-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2df72-162">See also</span></span>

[<span data-ttu-id="2df72-163">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="2df72-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="2df72-164">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="2df72-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="2df72-165">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="2df72-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)


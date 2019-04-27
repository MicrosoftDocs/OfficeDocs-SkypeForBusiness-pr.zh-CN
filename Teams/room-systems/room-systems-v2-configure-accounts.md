---
title: 为 Microsoft 团队房间配置帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 阅读本主题以了解如何在 Exchange 配置帐户的 Microsoft 团队聊天室和 Skype 的业务。
ms.openlocfilehash: f276510e633e30d248d5c5d46277e04deaf043b0
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362621"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="a18a4-103">为 Microsoft 团队房间配置帐户</span><span class="sxs-lookup"><span data-stu-id="a18a4-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="a18a4-104">阅读此主题以了解有关 Microsoft 团队聊天室以及它如何与 Exchange 和 Skype 的业务集成。</span><span class="sxs-lookup"><span data-stu-id="a18a4-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="a18a4-105">本主题介绍如何创建 for Business 使用 Microsoft Exchange 和 Skype 中的 Microsoft 团队聊天室的帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="a18a4-106">[配置 Microsoft 团队聊天室控制台](console.md)中介绍了 Microsoft 团队聊天室设备的部署说明。</span><span class="sxs-lookup"><span data-stu-id="a18a4-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="a18a4-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="a18a4-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="a18a4-108">Online 部署： 完全在 Office 365 上部署您的组织的环境。</span><span class="sxs-lookup"><span data-stu-id="a18a4-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="a18a4-109">有关详细信息，请参阅[与 Office 365 部署 Microsoft 团队的聊天室](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a18a4-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="a18a4-110">本地部署： 贵组织拥有的它控制，服务器承载 Active Directory、 Exchange 和 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="a18a4-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="a18a4-111">有关详细信息，请参阅[与 Skype 的业务服务器中部署 Microsoft 团队聊天室](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="a18a4-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="a18a4-112">混合部署： 贵组织拥有一些部署和一些在线承载通过 Office 365 上承载的服务，组合。</span><span class="sxs-lookup"><span data-stu-id="a18a4-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="a18a4-113">与 Microsoft 团队聊天室，支持以下混合方案：</span><span class="sxs-lookup"><span data-stu-id="a18a4-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="a18a4-114">Exchange Online 与 Skype 的本地业务服务器。</span><span class="sxs-lookup"><span data-stu-id="a18a4-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="a18a4-115">有关详细信息，请参阅[与 Exchange Online （混合） 部署 Microsoft 团队的聊天室](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="a18a4-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="a18a4-116">在本地与 Microsoft 团队或 Skype 的 exchange online 业务。</span><span class="sxs-lookup"><span data-stu-id="a18a4-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="a18a4-117">有关详细信息，请参阅[与 Exchange 本地 （混合） 部署 Microsoft 团队的聊天室](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="a18a4-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="a18a4-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="a18a4-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="a18a4-119">Microsoft 团队聊天室需要 Active Directory、 Exchange 和 Skype for Business 中分配"设备帐户"。</span><span class="sxs-lookup"><span data-stu-id="a18a4-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="a18a4-120">帐户用于访问其会议日历并建立业务连接的 Microsoft 团队或 Skype。</span><span class="sxs-lookup"><span data-stu-id="a18a4-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="a18a4-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="a18a4-122">Microsoft 团队聊天室都将能够加入的会议并向会议与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="a18a4-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a18a4-123">没有设备帐户，无这些功能将工作。</span><span class="sxs-lookup"><span data-stu-id="a18a4-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="a18a4-124">每个设备的帐户是唯一的单个 Microsoft 团队聊天室设备，并且需要进行一些设置：</span><span class="sxs-lookup"><span data-stu-id="a18a4-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="a18a4-125">必须正确配置的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="a18a4-126">必须将您的基础结构配置为允许 Microsoft 团队聊天室验证设备帐户，并获得相应的 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="a18a4-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a18a4-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="a18a4-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="a18a4-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="a18a4-128">Ideally, account preparation is started two to three weeks before installation.</span></span> <span data-ttu-id="a18a4-129">在混合环境中用于 Microsoft 团队聊天室的帐户必须具有启用在 AAD 同步，因为 Microsoft 团队聊天室身份验证要求 0ffice 365 身份验证的密码同步。</span><span class="sxs-lookup"><span data-stu-id="a18a4-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in AAD Sync because Microsoft Teams Rooms authentication requires 0ffice 365 authentication.</span></span>
  
<span data-ttu-id="a18a4-130">您可以将设备帐户视为识别为会议会议室的或会议空间的帐户的人员的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-130">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="a18a4-131">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="a18a4-131">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="a18a4-132">为了最有效地使用 Microsoft 团队聊天室，则执行与分配给每个设备帐户相同。</span><span class="sxs-lookup"><span data-stu-id="a18a4-132">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="a18a4-133">如果您已有资源邮箱帐户设置为正在安装 Microsoft 团队会议室的会议空间，可以将该资源帐户更改为设备帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-133">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="a18a4-134">完成后，您需要执行操作是将设备帐户添加到 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="a18a4-134">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="a18a4-135">请参阅下面提供了设备帐户安装程序示例。</span><span class="sxs-lookup"><span data-stu-id="a18a4-135">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="a18a4-136">其他配置远程管理是可以[使用 Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)、[部署 Microsoft 团队聊天室管理使用 Azure 监视器](azure-monitor-deploy.md)和[中所述使用 Microsoft Azure 监视器管理使用 Azure 监视器的 Microsoft 团队聊天室设备](azure-monitor-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="a18a4-136">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="a18a4-137">基本配置</span><span class="sxs-lookup"><span data-stu-id="a18a4-137">Basic configuration</span></span>

<span data-ttu-id="a18a4-138">这些属性表示要使用 Microsoft 团队聊天室的设备帐户的最低配置。</span><span class="sxs-lookup"><span data-stu-id="a18a4-138">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="a18a4-139">您的设备帐户可能需要进一步的安装程序。</span><span class="sxs-lookup"><span data-stu-id="a18a4-139">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="a18a4-140">**属性**</span><span class="sxs-lookup"><span data-stu-id="a18a4-140">**Property**</span></span>|<span data-ttu-id="a18a4-141">**用途**</span><span class="sxs-lookup"><span data-stu-id="a18a4-141">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a18a4-142">Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="a18a4-142">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="a18a4-143">启用 Exchange 邮箱的帐户授予设备帐户接收和发送邮件和会议请求，并显示会议日历 Microsoft 团队聊天室设备上的功能。</span><span class="sxs-lookup"><span data-stu-id="a18a4-143">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="a18a4-144">Microsoft 团队会议室邮箱必须会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="a18a4-144">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="a18a4-145">启用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a18a4-145">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="a18a4-146">若要使用各种会议功能，如视频呼叫、 IM 和屏幕共享，必须启用 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="a18a4-146">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="a18a4-147">支持的业务联机 Skype 和 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="a18a4-147">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="a18a4-148">已启用密码</span><span class="sxs-lookup"><span data-stu-id="a18a4-148">Password-enabled</span></span>  <br/> |<span data-ttu-id="a18a4-149">设备帐户必须启用使用的密码，或进行不能与 Exchange 或 Skype 业务服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="a18a4-149">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="a18a4-150">高级的配置</span><span class="sxs-lookup"><span data-stu-id="a18a4-150">Advanced configuration</span></span>

<span data-ttu-id="a18a4-151">属性时的基本配置将允许设备帐户设置在简单环境中，则可能您的环境有其他限制的顺序的 Microsoft 团队会议室成功使用，必须满足的 directory 帐户设备的帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-151">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="a18a4-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="a18a4-152">**Property**</span></span>|<span data-ttu-id="a18a4-153">**用途**</span><span class="sxs-lookup"><span data-stu-id="a18a4-153">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a18a4-154">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="a18a4-154">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="a18a4-155">Exchange 和 Skype 业务服务器可能需要使用证书。</span><span class="sxs-lookup"><span data-stu-id="a18a4-155">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="a18a4-156">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="a18a4-156">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="a18a4-157">设置设备帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="a18a4-157">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="a18a4-158">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的设备帐户，或验证必须以帮助您将它们转换为兼容的 Microsoft 团队聊天室设备帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="a18a4-158">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="a18a4-159">如果您希望使用 Windows PowerShell cmdlet 通过 Office 365 用户界面，可以手动执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="a18a4-159">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="a18a4-160">请参阅[创建设备帐户使用 Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="a18a4-160">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a18a4-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a18a4-161">See also</span></span>

[<span data-ttu-id="a18a4-162">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a18a4-162">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="a18a4-163">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="a18a4-163">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a18a4-164">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="a18a4-164">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)


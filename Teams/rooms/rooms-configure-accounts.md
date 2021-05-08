---
title: 配置帐户Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
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
description: 阅读本主题，了解如何在 Microsoft Teams 会议室 和 Exchange 中Skype for Business。
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117470"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="c04e9-103">配置帐户Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="c04e9-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="c04e9-104">阅读本主题，了解Microsoft Teams 会议室及其如何与 Exchange Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="c04e9-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="c04e9-105">本主题介绍了如何创建 Microsoft Microsoft Teams 会议室 和 Exchange Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="c04e9-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="c04e9-106">配置 Microsoft Teams 会议室 控制台 中介绍了Microsoft Teams 会议室[设备的部署说明](console.md)。</span><span class="sxs-lookup"><span data-stu-id="c04e9-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="c04e9-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="c04e9-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="c04e9-108">联机部署：组织的环境完全部署在Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c04e9-108">Online deployment: Your organization's environment is deployed entirely on Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c04e9-109">有关详细信息，请参阅使用 Microsoft Teams 会议室[或 Microsoft 365 部署Office 365。](with-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c04e9-109">For more information, see [Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="c04e9-110">本地部署：组织有它所控制的服务器，其中 Active Directory、Exchange和Skype for Business Server托管。</span><span class="sxs-lookup"><span data-stu-id="c04e9-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="c04e9-111">有关详细信息，请参阅使用 Microsoft Teams 会议室[部署Skype for Business Server](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="c04e9-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="c04e9-112">混合部署：组织混合了一些服务，其中一些托管在本地，一些通过本地或 Microsoft 365 联机Office 365。</span><span class="sxs-lookup"><span data-stu-id="c04e9-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c04e9-113">使用Microsoft Teams 会议室，支持以下混合方案：</span><span class="sxs-lookup"><span data-stu-id="c04e9-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span>
    
  - <span data-ttu-id="c04e9-114">Exchange Online本地Skype for Business Server部署。</span><span class="sxs-lookup"><span data-stu-id="c04e9-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="c04e9-115">有关详细信息，请参阅使用混合Microsoft Teams 会议室[部署Exchange Online () 。 ](with-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="c04e9-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="c04e9-116">Exchange Online Microsoft Teams或 Skype for Business 本地。</span><span class="sxs-lookup"><span data-stu-id="c04e9-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="c04e9-117">有关详细信息，请参阅使用本地Microsoft Teams 会议室[部署Exchange混合 (部署) 。 ](with-exchange-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="c04e9-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="c04e9-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="c04e9-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="c04e9-119">Microsoft Teams 会议室 Active Directory、Exchange 和 Skype for Business 中为用户分配"设备帐户"。</span><span class="sxs-lookup"><span data-stu-id="c04e9-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="c04e9-120">该帐户用于访问其会议日历并建立Microsoft Teams Skype for Business连接。</span><span class="sxs-lookup"><span data-stu-id="c04e9-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="c04e9-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="c04e9-122">Microsoft Teams 会议室将能够加入该会议，并为与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="c04e9-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c04e9-123">如果没有设备帐户，这些功能都不起作用。</span><span class="sxs-lookup"><span data-stu-id="c04e9-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="c04e9-124">每个设备帐户对于单个设备Microsoft Teams 会议室唯一，并且需要进行一些设置：</span><span class="sxs-lookup"><span data-stu-id="c04e9-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="c04e9-125">必须正确配置设备帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="c04e9-126">必须将基础结构配置为允许Microsoft Teams 会议室验证设备帐户并访问相应的Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="c04e9-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c04e9-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="c04e9-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="c04e9-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="c04e9-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 

<span data-ttu-id="c04e9-129">在混合环境中，用于 Microsoft Teams 会议室 的帐户必须在 Azure Active Directory (AAD) Sync 中启用密码同步，因为 Microsoft Teams 会议室 身份验证Microsoft 365或Office 365身份验证。</span><span class="sxs-lookup"><span data-stu-id="c04e9-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in Azure Active Directory (AAD) Sync because Microsoft Teams Rooms authentication requires Microsoft 365 or Office 365 authentication.</span></span> <span data-ttu-id="c04e9-130">设置帐户时，请确保帐户的 SIP 地址与 AAD 中的 UPN (用户主体名称) 匹配。</span><span class="sxs-lookup"><span data-stu-id="c04e9-130">When setting up the account, make sure that the account's SIP address matches its User Principal Name (UPN) in AAD.</span></span> 
  
<span data-ttu-id="c04e9-131">可以将设备帐户视为用户识别为会议室或会议空间帐户的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-131">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="c04e9-132">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="c04e9-132">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="c04e9-133">为了最有效地Microsoft Teams 会议室，请对分配给每个帐户的设备帐户执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="c04e9-133">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="c04e9-134">如果已针对要安装资源的会议空间设置了资源邮箱帐户Microsoft Teams 会议室，可以将该资源帐户更改为设备帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-134">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="c04e9-135">完成后，只需将设备帐户添加到 Microsoft Teams 会议室 设备。</span><span class="sxs-lookup"><span data-stu-id="c04e9-135">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c04e9-136">请参阅下面提供的设备帐户设置示例。</span><span class="sxs-lookup"><span data-stu-id="c04e9-136">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="c04e9-137">通过附加配置，Microsoft Azure Monitor 实现远程管理，如使用 Azure [Monitor](azure-monitor-plan.md)规划 Microsoft Teams 会议室 管理、使用[Azure Monitor](azure-monitor-deploy.md)部署 Microsoft Teams 会议室 管理以及使用[Azure Monitor](azure-monitor-manage.md)管理 Microsoft Teams 会议室 设备中所述。</span><span class="sxs-lookup"><span data-stu-id="c04e9-137">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="c04e9-138">基本配置</span><span class="sxs-lookup"><span data-stu-id="c04e9-138">Basic configuration</span></span>

<span data-ttu-id="c04e9-139">这些属性表示设备帐户使用设备帐户的最低配置Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="c04e9-139">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="c04e9-140">你的设备帐户可能需要进一步设置。</span><span class="sxs-lookup"><span data-stu-id="c04e9-140">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="c04e9-141">**属性**</span><span class="sxs-lookup"><span data-stu-id="c04e9-141">**Property**</span></span>|<span data-ttu-id="c04e9-142">**用途**</span><span class="sxs-lookup"><span data-stu-id="c04e9-142">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c04e9-143">Exchange 2013 SP1 (Exchange更高版本的邮箱，或 Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="c04e9-143">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="c04e9-144">启用具有 Exchange 邮箱的帐户使设备帐户能够接收和发送邮件和会议请求，以及向 Microsoft Teams 会议室 显示会议日历。</span><span class="sxs-lookup"><span data-stu-id="c04e9-144">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c04e9-145">Microsoft Teams 会议室邮箱必须是会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="c04e9-145">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="c04e9-146">Skype for Business已启用</span><span class="sxs-lookup"><span data-stu-id="c04e9-146">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="c04e9-147">Skype for Business启用此功能才能使用各种会议功能，例如视频呼叫、即时消息和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="c04e9-147">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="c04e9-148">支持Skype for Business Online 和 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="c04e9-148">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="c04e9-149">已启用密码</span><span class="sxs-lookup"><span data-stu-id="c04e9-149">Password-enabled</span></span>  <br/> |<span data-ttu-id="c04e9-150">设备帐户必须使用密码启用，或者无法使用密码或Exchange Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="c04e9-150">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="c04e9-151">高级配置</span><span class="sxs-lookup"><span data-stu-id="c04e9-151">Advanced configuration</span></span>

<span data-ttu-id="c04e9-152">尽管基本配置的属性允许在简单环境中设置设备帐户，但环境可能对目录帐户具有其他限制，必须满足这些限制，Microsoft Teams 会议室 才能成功使用设备帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-152">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="c04e9-153">**属性**</span><span class="sxs-lookup"><span data-stu-id="c04e9-153">**Property**</span></span>|<span data-ttu-id="c04e9-154">**用途**</span><span class="sxs-lookup"><span data-stu-id="c04e9-154">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c04e9-155">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="c04e9-155">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="c04e9-156">证书可能需要用于Exchange Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="c04e9-156">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="c04e9-157">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="c04e9-157">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="c04e9-158">设置设备帐户的最简单方法是使用远程客户端配置Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c04e9-158">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="c04e9-159">Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的设备帐户或验证现有资源帐户，以帮助你将其转换为兼容的设备Microsoft Teams 会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="c04e9-159">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="c04e9-160">如果你希望使用 Microsoft 365 或 Office 365 UI Windows PowerShell cmdlet，可以手动执行某些步骤。</span><span class="sxs-lookup"><span data-stu-id="c04e9-160">If you prefer to use the Microsoft 365 or Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="c04e9-161">请参阅[使用 Microsoft 365 或 Office 365 创建设备帐户](/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c04e9-161">See [Creating a device account using Microsoft 365 or Office 365](/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c04e9-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c04e9-162">See also</span></span>

[<span data-ttu-id="c04e9-163">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="c04e9-163">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="c04e9-164">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="c04e9-164">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c04e9-165">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="c04e9-165">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
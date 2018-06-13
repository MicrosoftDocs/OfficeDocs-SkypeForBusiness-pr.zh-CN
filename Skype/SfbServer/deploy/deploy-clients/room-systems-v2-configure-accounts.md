---
title: 配置帐户 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: 阅读此主题以了解有关在 Exchange 配置帐户 Skype 会议室系统 v2 和 Skype 的业务服务器 2015年。
ms.openlocfilehash: fb0bbe4b8048bfeda0acf10a0e6cfc73ce8163ea
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2018
ms.locfileid: "19856161"
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a><span data-ttu-id="8754c-103">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="8754c-103">Configure accounts for Skype Room Systems v2</span></span>
 
<span data-ttu-id="8754c-104">阅读本主题可了解 Skype 会议室系统 v2 以及如何将其集成 Exchange 与 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="8754c-104">Read this topic to learn about Skype Room Systems v2 and how it integrates with Exchange and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8754c-105">本主题介绍如何创建用于通过在 Microsoft Exchange 和 Skype 的 Skype 会议室系统 v2 业务服务器 2015年的帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-105">This topic introduces how to create accounts used by Skype Room Systems v2 in Microsoft Exchange and Skype for Business Server 2015.</span></span> <span data-ttu-id="8754c-106">Skype 会议室系统 v2 设备的部署说明涵盖在[配置 Skype 会议室系统 v2 控制台](console.md)。</span><span class="sxs-lookup"><span data-stu-id="8754c-106">Deployment instructions for Skype Room Systems v2 devices is covered in [Configure a Skype Room Systems v2 console](console.md).</span></span> <span data-ttu-id="8754c-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="8754c-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="8754c-108">Online 部署： 完全在 Office 365 上部署您的组织的环境。</span><span class="sxs-lookup"><span data-stu-id="8754c-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="8754c-109">有关详细信息，请参阅[Office 365 的部署 Skype 会议室系统 v2](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8754c-109">For more information, see [Deploy Skype Room Systems v2 with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="8754c-110">本地部署： 贵组织拥有的它控制，服务器承载 Active Directory、 Exchange 和 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="8754c-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server 2015 are hosted.</span></span> <span data-ttu-id="8754c-111">有关详细信息，请参阅[部署 Skype 会议室系统 v2 与 Skype 的业务服务器 2015](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="8754c-111">For more information, see [Deploy Skype Room Systems v2 with Skype for Business Server 2015](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="8754c-112">混合部署： 贵组织拥有一些部署和一些在线承载通过 Office 365 上承载的服务，组合。</span><span class="sxs-lookup"><span data-stu-id="8754c-112">Hybrid deployment: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="8754c-113">与 Skype 会议室系统 v2 支持以下混合方案：</span><span class="sxs-lookup"><span data-stu-id="8754c-113">With Skype Room Systems v2, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="8754c-114">Exchange Online 与 Skype 的本地业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="8754c-114">Exchange Online with Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="8754c-115">有关详细信息，请参阅[与 Exchange Online （混合） 的部署 Skype 会议室系统 v2](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="8754c-115">For more information, see [Deploy Skype Room Systems v2 with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="8754c-116">在本地与 Skype 的 exchange online 业务。</span><span class="sxs-lookup"><span data-stu-id="8754c-116">Exchange on premises with Skype for Business Online.</span></span> <span data-ttu-id="8754c-117">有关详细信息，请参阅[与 Exchange 本地 （混合） 的部署 Skype 会议室系统 v2](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="8754c-117">For more information, see [Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="8754c-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="8754c-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="8754c-119">Skype 会议室系统 v2 需要 Active Directory、 Exchange 和 Skype for Business 中分配"用户帐户"。</span><span class="sxs-lookup"><span data-stu-id="8754c-119">Skype Room Systems v2 needs to be assigned a "User account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="8754c-120">帐户用于访问其会议日历并建立 Skype 业务连接。</span><span class="sxs-lookup"><span data-stu-id="8754c-120">The account is used to access its meeting calendar and establish Skype for Business connectivity.</span></span> <span data-ttu-id="8754c-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="8754c-122">Skype 会议室系统 v2 都将能够加入的会议并向会议与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="8754c-122">Skype Room Systems v2 will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8754c-123">如果没有用户帐户，所有功能都将不能使用。</span><span class="sxs-lookup"><span data-stu-id="8754c-123">Without a user account, none of these features will work.</span></span> 
  
<span data-ttu-id="8754c-124">每个用户帐户是唯一的单个 Skype 会议室系统 v2 设备，并且需要进行一些设置：</span><span class="sxs-lookup"><span data-stu-id="8754c-124">Every user account is unique to a single Skype Room Systems v2 device, and requires some setup:</span></span>
  
- <span data-ttu-id="8754c-125">必须对用户帐户进行正确配置。</span><span class="sxs-lookup"><span data-stu-id="8754c-125">The user account must be configured correctly.</span></span>
    
- <span data-ttu-id="8754c-126">必须将您的基础结构配置为允许 Skype 会议室系统 v2 来验证用户帐户，并获得相应的 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="8754c-126">Your infrastructure must be configured to allow Skype Room Systems v2 to validate the user account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8754c-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="8754c-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="8754c-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="8754c-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 
  
<span data-ttu-id="8754c-129">您可以将用户帐户视为识别为会议会议室的或会议空间的帐户的人员的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-129">You can think of a user account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="8754c-130">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="8754c-130">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="8754c-131">若要最有效地使用 Skype 会议室系统 v2，您将执行与分配给每个用户帐户相同。</span><span class="sxs-lookup"><span data-stu-id="8754c-131">In order to use Skype Room Systems v2 most effectively, you do the same with the user account that's assigned to each one.</span></span>
  
<span data-ttu-id="8754c-132">如果您已有资源邮箱帐户设置为正在安装 Skype 会议室系统 v2 的会议空间，可以将该资源帐户更改为用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-132">If you already have a resource mailbox account set up for the meeting space where you're installing Skype Room Systems v2, you can change that resource account into a user account.</span></span> <span data-ttu-id="8754c-133">完成后，只需执行操作是将用户帐户添加到 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="8754c-133">Once that's done, all you need to do is add the user account to a Skype Room Systems v2 device.</span></span> <span data-ttu-id="8754c-134">请参阅下面提供的用户帐户设置示例。</span><span class="sxs-lookup"><span data-stu-id="8754c-134">See user account setup examples provided below.</span></span>
  
<span data-ttu-id="8754c-135">其他配置远程管理是可以[使用 OMS 的规划 Skype 会议室系统 v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[使用 OMS 的部署 Skype 会议室系统 v2 管理](with-oms.md)和[管理中所述使用 Microsoft 操作管理套件 (OMS)OMS Skype 会议室系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)。</span><span class="sxs-lookup"><span data-stu-id="8754c-135">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](../../manage/skype-room-systems-v2/oms.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="8754c-136">基本配置</span><span class="sxs-lookup"><span data-stu-id="8754c-136">Basic configuration</span></span>

<span data-ttu-id="8754c-137">这些属性表示用户帐户以使用 Skype 会议室系统 v2 的最低配置。</span><span class="sxs-lookup"><span data-stu-id="8754c-137">These properties represent the minimum configuration for a user account to work with Skype Room Systems v2.</span></span> <span data-ttu-id="8754c-138">你的用户帐户可能需要进行更多设置。</span><span class="sxs-lookup"><span data-stu-id="8754c-138">Your user account may require further setup.</span></span>
  
|<span data-ttu-id="8754c-139">**属性**</span><span class="sxs-lookup"><span data-stu-id="8754c-139">**Property**</span></span>|<span data-ttu-id="8754c-140">**用途**</span><span class="sxs-lookup"><span data-stu-id="8754c-140">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8754c-141">Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="8754c-141">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="8754c-142">启用 Exchange 邮箱的帐户提供的用户帐户接收和发送邮件和会议请求，并显示会议日历 Skype 会议室系统 v2 设备上的功能。</span><span class="sxs-lookup"><span data-stu-id="8754c-142">Enabling the account with an Exchange mailbox gives the user account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Skype Room Systems v2 device.</span></span> <span data-ttu-id="8754c-143">Skype 会议室系统 v2 邮箱必须会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="8754c-143">The Skype Room Systems v2 mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="8754c-144">启用 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8754c-144">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="8754c-145">若要使用各种会议功能，如视频呼叫、 IM 和屏幕共享，必须启用 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="8754c-145">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="8754c-146">支持的业务联机 Skype 和 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="8754c-146">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="8754c-147">已启用密码</span><span class="sxs-lookup"><span data-stu-id="8754c-147">Password-enabled</span></span>  <br/> |<span data-ttu-id="8754c-148">必须使用密码，启用的用户帐户或进行不能与 Exchange 或 Skype 业务服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="8754c-148">The user account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="8754c-149">高级的配置</span><span class="sxs-lookup"><span data-stu-id="8754c-149">Advanced configuration</span></span>

<span data-ttu-id="8754c-150">属性时的基本配置将允许在简单环境中，设置的用户帐户，则可能您的环境有其他限制的顺序的 Skype 会议室系统 v2 成功使用，必须满足的 directory 帐户用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-150">While the properties for the basic configuration will allow the user account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Skype Room Systems v2 to successfully use the user account.</span></span>
  
|<span data-ttu-id="8754c-151">**属性**</span><span class="sxs-lookup"><span data-stu-id="8754c-151">**Property**</span></span>|<span data-ttu-id="8754c-152">**用途**</span><span class="sxs-lookup"><span data-stu-id="8754c-152">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8754c-153">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="8754c-153">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="8754c-154">Exchange 和 Skype 业务服务器可能需要使用证书。</span><span class="sxs-lookup"><span data-stu-id="8754c-154">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="8754c-155">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="8754c-155">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="8754c-156">设置用户帐户的最佳方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8754c-156">The best way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="8754c-157">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomProvisioningScript.ps1.txt)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8754c-157">Microsoft provides [SkypeRoomProvisioningScript.ps1](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomProvisioningScript.ps1.txt), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span>
  
<span data-ttu-id="8754c-158">如果您希望使用 Windows PowerShell cmdlet 通过 Office 365 用户界面，可以手动执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="8754c-158">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="8754c-159">请参阅[创建设备帐户使用 Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="8754c-159">See [Creating a device account using Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8754c-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8754c-160">See also</span></span>

[<span data-ttu-id="8754c-161">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="8754c-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="8754c-162">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="8754c-162">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="8754c-163">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="8754c-163">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


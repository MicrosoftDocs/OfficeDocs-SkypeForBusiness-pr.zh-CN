---
title: 部署 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本主题以了解有关 Skype 的空间系统 v2 和如何将其集成与交换和 Skype 的业务服务器 2015年。
ms.openlocfilehash: 54dc3d42d406fea2bdefcac5eb726dd77fde078f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2"></a><span data-ttu-id="33a42-103">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="33a42-103">Deploy Skype Room Systems v2</span></span>
 
<span data-ttu-id="33a42-104">阅读本主题以了解有关 Skype 的空间系统 v2 和如何将其集成与交换和 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="33a42-104">Read this topic to learn about Skype Room Systems v2 and how it integrates with Exchange and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="33a42-105">本主题介绍如何创建帐户的业务服务器 2015年使用 Microsoft Exchange 和 Skype 的 Skype 的空间系统 v2。</span><span class="sxs-lookup"><span data-stu-id="33a42-105">This topic introduces how to create accounts used by Skype Room Systems v2 in Microsoft Exchange and Skype for Business Server 2015.</span></span> <span data-ttu-id="33a42-106">[Skype 的空间系统 v2 控制台配置](console.md)中介绍了 Skype 的空间系统 v2 设备的部署说明。</span><span class="sxs-lookup"><span data-stu-id="33a42-106">Deployment instructions for Skype Room Systems v2 devices is covered in [Configure a Skype Room Systems v2 console](console.md).</span></span> <span data-ttu-id="33a42-107">你的基础结构很可能属于以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="33a42-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="33a42-108">联机部署： 完全在 Office 365 上部署您的组织环境。</span><span class="sxs-lookup"><span data-stu-id="33a42-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="33a42-109">有关详细信息，请参阅[部署 Skype 的空间系统 v2 与 Office 365](with-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="33a42-109">For more information, see [Deploy Skype Room Systems v2 with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="33a42-110">内部部署： 它控制，您的组织有承载 Active Directory、 交换和业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="33a42-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server 2015 are hosted.</span></span> <span data-ttu-id="33a42-111">有关详细信息，请参阅[部署 Skype 的空间系统具有的业务服务器 2015 Skype 的 v2](with-skype-for-business-server-2015.md)</span><span class="sxs-lookup"><span data-stu-id="33a42-111">For more information, see [Deploy Skype Room Systems v2 with Skype for Business Server 2015](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="33a42-112">混合部署： 您的组织有一些位于内部部署和联机寄宿通过 Office 365 提供一些服务，混合。</span><span class="sxs-lookup"><span data-stu-id="33a42-112">Hybrid deployment: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="33a42-113">与 Skype 的空间系统 v2 支持下面的混合方案：</span><span class="sxs-lookup"><span data-stu-id="33a42-113">With Skype Room Systems v2, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="33a42-114">Exchange 联机使用内部部署的业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="33a42-114">Exchange Online with Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="33a42-115">有关详细信息，请参阅[部署 Skype 的空间系统 v2 使用 Exchange Online （混合）](with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="33a42-115">For more information, see [Deploy Skype Room Systems v2 with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="33a42-116">在线业务交换在与 Skype 的场所。</span><span class="sxs-lookup"><span data-stu-id="33a42-116">Exchange on premises with Skype for Business Online.</span></span> <span data-ttu-id="33a42-117">有关详细信息，请参阅[部署 Skype 的空间系统 v2 交换在场所 （混合）](with-exchange-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="33a42-117">For more information, see [Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="33a42-118">你所拥有的配置类型将影响设备设置的准备方式。</span><span class="sxs-lookup"><span data-stu-id="33a42-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="33a42-119">Skype 的空间系统 v2 需要分配一个"用户帐户"在 Active Directory、 交换和业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="33a42-119">Skype Room Systems v2 needs to be assigned a "User account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="33a42-120">此帐户用于访问其会议日历，并建立 Skype 业务连接性。</span><span class="sxs-lookup"><span data-stu-id="33a42-120">The account is used to access its meeting calendar and establish Skype for Business connectivity.</span></span> <span data-ttu-id="33a42-121">用户可通过使用此帐户安排会议来预订此帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="33a42-122">Skype 的空间系统 v2 将能够参加该会议并向与会者提供各种功能。</span><span class="sxs-lookup"><span data-stu-id="33a42-122">Skype Room Systems v2 will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33a42-123">如果没有用户帐户，所有功能都将不能使用。</span><span class="sxs-lookup"><span data-stu-id="33a42-123">Without a user account, none of these features will work.</span></span> 
  
<span data-ttu-id="33a42-124">每个用户帐户是唯一的一个 Skype 的空间系统 v2 设备，并且需要一些设置：</span><span class="sxs-lookup"><span data-stu-id="33a42-124">Every user account is unique to a single Skype Room Systems v2 device, and requires some setup:</span></span>
  
- <span data-ttu-id="33a42-125">必须对用户帐户进行正确配置。</span><span class="sxs-lookup"><span data-stu-id="33a42-125">The user account must be configured correctly.</span></span>
    
- <span data-ttu-id="33a42-126">您的基础结构必须被配置为允许 Skype 的空间系统 v2 来验证用户帐户，并达到相应的 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="33a42-126">Your infrastructure must be configured to allow Skype Room Systems v2 to validate the user account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="33a42-127">强烈建议你在实际安装硬件之前完成帐户创建。</span><span class="sxs-lookup"><span data-stu-id="33a42-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="33a42-128">理想情况下，应在安装之前两至三周开始帐户准备工作。</span><span class="sxs-lookup"><span data-stu-id="33a42-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 
  
<span data-ttu-id="33a42-129">可以是用户帐户看作人作为大会文件室或会议空间的帐户识别资源帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-129">You can think of a user account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="33a42-130">当你要使用该会议室安排会议时，可邀请帐户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="33a42-130">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="33a42-131">为了最有效地使用 Skype 的空间系统 v2，则执行相同的操作使用分配给每个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-131">In order to use Skype Room Systems v2 most effectively, you do the same with the user account that's assigned to each one.</span></span>
  
<span data-ttu-id="33a42-132">如果您已经有资源邮箱帐户设置为位置安装 Skype 的空间系统 v2 的会议空间，可该资源帐户更改为用户帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-132">If you already have a resource mailbox account set up for the meeting space where you're installing Skype Room Systems v2, you can change that resource account into a user account.</span></span> <span data-ttu-id="33a42-133">完成后，所有您需要做是将用户帐户添加到 Skype 的空间系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="33a42-133">Once that's done, all you need to do is add the user account to a Skype Room Systems v2 device.</span></span> <span data-ttu-id="33a42-134">请参阅下面提供的用户帐户设置示例。</span><span class="sxs-lookup"><span data-stu-id="33a42-134">See user account setup examples provided below.</span></span>
  
<span data-ttu-id="33a42-135">与其他配置，远程管理是可能使用 Microsoft 操作管理套件 (OMS)，所述[计划 Skype 的空间系统 OMS v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[部署 Skype 的空间系统 v2 管理与 OMS](with-oms.md)和[管理Skype 的空间系统 OMS 的 v2 设备](../../manage/skype-room-systems-v2/oms.md)。</span><span class="sxs-lookup"><span data-stu-id="33a42-135">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](../../manage/skype-room-systems-v2/oms.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="33a42-136">基本配置</span><span class="sxs-lookup"><span data-stu-id="33a42-136">Basic Configuration</span></span>

<span data-ttu-id="33a42-137">这些属性表示为用户帐户以使用 Skype 的空间系统 v2 的最低配置。</span><span class="sxs-lookup"><span data-stu-id="33a42-137">These properties represent the minimum configuration for a user account to work with Skype Room Systems v2.</span></span> <span data-ttu-id="33a42-138">你的用户帐户可能需要进行更多设置。</span><span class="sxs-lookup"><span data-stu-id="33a42-138">Your user account may require further setup.</span></span>
  
|<span data-ttu-id="33a42-139">**属性**</span><span class="sxs-lookup"><span data-stu-id="33a42-139">**Property**</span></span>|<span data-ttu-id="33a42-140">**目的**</span><span class="sxs-lookup"><span data-stu-id="33a42-140">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33a42-141">Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或者 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="33a42-141">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="33a42-142">启用 Exchange 邮箱的帐户为用户帐户提供能力来接收和发送邮件和会议要求，并在 Skype 的空间系统 v2 设备上显示会议日历。</span><span class="sxs-lookup"><span data-stu-id="33a42-142">Enabling the account with an Exchange mailbox gives the user account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Skype Room Systems v2 device.</span></span> <span data-ttu-id="33a42-143">Skype 的空间系统 v2 邮箱必须会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="33a42-143">The Skype Room Systems v2 mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="33a42-144">为业务 Skype 已启用</span><span class="sxs-lookup"><span data-stu-id="33a42-144">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="33a42-145">Skype 业务必须启用才能使用各种会议功能，如视频电话、 IM 和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="33a42-145">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="33a42-146">Skype 的在线业务和 Skype 业务服务器的支持。</span><span class="sxs-lookup"><span data-stu-id="33a42-146">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="33a42-147">已启用密码</span><span class="sxs-lookup"><span data-stu-id="33a42-147">Password-enabled</span></span>  <br/> |<span data-ttu-id="33a42-148">必须启用用户帐户有密码保护，或者它不能与 Exchange 或 Skype 业务服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="33a42-148">The user account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="33a42-149">高级配置</span><span class="sxs-lookup"><span data-stu-id="33a42-149">Advanced Configuration</span></span>

<span data-ttu-id="33a42-150">属性时基本配置将允许用户帐户设置在简单的环境中，很可能您的环境必须满足为 Skype 的空间系统 v2，为了能够成功使用的目录帐户上有其他限制用户帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-150">While the properties for the basic configuration will allow the user account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Skype Room Systems v2 to successfully use the user account.</span></span>
  
|<span data-ttu-id="33a42-151">**属性**</span><span class="sxs-lookup"><span data-stu-id="33a42-151">**Property**</span></span>|<span data-ttu-id="33a42-152">**目的**</span><span class="sxs-lookup"><span data-stu-id="33a42-152">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33a42-153">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="33a42-153">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="33a42-154">用于交换和 Skype 业务服务器可能需要使用证书。</span><span class="sxs-lookup"><span data-stu-id="33a42-154">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="33a42-155">要部署证书，可以在以管理员身份登录时加载它们。</span><span class="sxs-lookup"><span data-stu-id="33a42-155">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="33a42-156">设置用户帐户的最佳方法是使用远程 Windows PowerShell 配置。</span><span class="sxs-lookup"><span data-stu-id="33a42-156">The best way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="33a42-157">[Microsoft 提供的脚本](https://go.microsoft.com/fwlink/?linkid=870105)将帮助创建新的用户帐户，或验证现有资源帐户可以帮助您将它们转换为兼容的 Skype 的空间系统 v2 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="33a42-157">[Microsoft provides scripts](https://go.microsoft.com/fwlink/?linkid=870105) that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span>
  
<span data-ttu-id="33a42-158">如果您希望在 Windows PowerShell cmdlet 使用 Office 365 用户界面，可以手动执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="33a42-158">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="33a42-159">请参阅[创建设备帐户使用 Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365)。</span><span class="sxs-lookup"><span data-stu-id="33a42-159">See [Creating a device account using Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33a42-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33a42-160">See also</span></span>

#### 

[<span data-ttu-id="33a42-161">Skype 的空间规划系统 v2</span><span class="sxs-lookup"><span data-stu-id="33a42-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="33a42-162">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="33a42-162">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="33a42-163">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="33a42-163">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


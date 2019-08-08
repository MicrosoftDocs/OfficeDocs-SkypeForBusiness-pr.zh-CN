---
title: 在 Office 365 中设置 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: 5df77e9a9e5e3ca67eb831596c12516457a15c45
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235062"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="d6649-103">在 Office 365 中设置 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="d6649-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="d6649-104">阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="d6649-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="d6649-105">以下部分介绍 Office 365 租户的 Skype 会议室系统帐户预配。</span><span class="sxs-lookup"><span data-stu-id="d6649-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="d6649-106">Office 365 先决条件</span><span class="sxs-lookup"><span data-stu-id="d6649-106">Office 365 prerequisites</span></span>

<span data-ttu-id="d6649-107">你的联机租户必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="d6649-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="d6649-108">Office 365 计划必须包括 Skype for Business Online 计划2或 Office 365 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="d6649-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="d6649-109">有关 Skype for Business Online 计划的详细信息, 请参阅[skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d6649-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="d6649-110">你的租户必须具有启用 Skype for Business 的会议功能。</span><span class="sxs-lookup"><span data-stu-id="d6649-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="d6649-111">你的租户必须启用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d6649-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="d6649-112">你的租户远程管理员必须具有以下 PowerShell 访问：</span><span class="sxs-lookup"><span data-stu-id="d6649-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="d6649-113">Exchange 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="d6649-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d6649-114">Skype for Business Online 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="d6649-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d6649-115">用于 Windows PowerShell 的 windows Azure Active Directory 模块以访问 Office 365 目录访问</span><span class="sxs-lookup"><span data-stu-id="d6649-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="d6649-116">对于 Skype 会议室帐户，需要以下许可：</span><span class="sxs-lookup"><span data-stu-id="d6649-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="d6649-117">要启用 Skype 会议, 需要有 Skype for Business Online 计划2或 Office 365 E1 或 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="d6649-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="d6649-118">若要使用企业语音功能 entitle 房间, 以便可以使用电话号码启用会议室, 需要具有电话系统许可证或 Office 365 E5 的 Skype for business Online 计划 2 (1)。</span><span class="sxs-lookup"><span data-stu-id="d6649-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="d6649-119">如果需要来自会议的电话拨入式功能, 您需要音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="d6649-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="d6649-120">如果需要来自会议的拨出功能, 您将需要国内或国内和国际通话计划。</span><span class="sxs-lookup"><span data-stu-id="d6649-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="d6649-121">Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="d6649-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="d6649-122">设置概述</span><span class="sxs-lookup"><span data-stu-id="d6649-122">Provisioning overview</span></span>

<span data-ttu-id="d6649-123">下图概括介绍了 Office 365 中的 Skype 会议室系统帐户预配流。</span><span class="sxs-lookup"><span data-stu-id="d6649-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 的 Skype 会议室系统设置步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="d6649-125">识别新的会议室</span><span class="sxs-lookup"><span data-stu-id="d6649-125">Identify a new conference room</span></span>

<span data-ttu-id="d6649-126">您可能在 Exchange 中已经有一个资源室邮箱可提供日程安排功能, 或者你可能是第一次创建资源邮箱来促进 Skype 会议室系统部署。</span><span class="sxs-lookup"><span data-stu-id="d6649-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="d6649-127">在任何情况下，你必须识别要在你的租户中使用的会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="d6649-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="d6649-128">Exchange Online 设置和 Skype for business 预配部分提供两种类型的帐户的指南。</span><span class="sxs-lookup"><span data-stu-id="d6649-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="d6649-129">例如, 假设你有以下两个会议室, 并且想要为两个会议室部署 Skype 会议室系统:</span><span class="sxs-lookup"><span data-stu-id="d6649-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="d6649-130">现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6649-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="d6649-131">新的资源邮箱帐户：confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6649-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="d6649-132">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="d6649-132">Exchange Online provisioning</span></span>

<span data-ttu-id="d6649-133">首先, 按照主题中的 "[连接到 Exchange Online powershell](https://go.microsoft.com/fwlink/p/?LinkId=396554)" 中的说明连接到 Exchange online powershell。</span><span class="sxs-lookup"><span data-stu-id="d6649-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="d6649-134">若要为 Skype 会议室系统设置现有的资源室邮箱帐户, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="d6649-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d6649-135">若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="d6649-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d6649-136">通过启用帐户, 以前的命令为 Skype 会议室系统使用设置或创建新的 Exchange 资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="d6649-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="d6649-137">创建邮箱后, 您可以使用 Exchange Online PowerShell 中的 CalendarProcessing cmdlet 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="d6649-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="d6649-138">有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="d6649-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="d6649-139">分配 Skype for Business Online 许可证</span><span class="sxs-lookup"><span data-stu-id="d6649-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="d6649-140">现在, 你可以使用 Office 365 管理门户分配 Skype for business Online (计划 2) 或 Skype for business Online (计划 3) 许可证, 如[分配或删除 office 365 for](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) Business 或[Skype for business 加载项的许可证中所述许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="d6649-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="d6649-141">为 Skype for business Online 分配许可证后, 你将能够登录并使用任何 Skype for Business 客户端验证帐户是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d6649-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="d6649-142">Skype for Business Online 设置</span><span class="sxs-lookup"><span data-stu-id="d6649-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="d6649-143">在创建并启用资源室邮箱帐户之前 (如上所示), 并且已授权 Skype For Business Online 帐户时, 该帐户将从 Exchange Online 林同步到 Skype for business Online 林, 方法是使用Windows Azure Active Directory 林。</span><span class="sxs-lookup"><span data-stu-id="d6649-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="d6649-144">在 Skype for business Online 池中预配 Skype 会议室系统帐户需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d6649-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="d6649-145">对于现有资源邮箱帐户或新创建的帐户 (confrm1 或 confrm2), 这些步骤是相同的, 因为在 Exchange Online 中启用这些帐户后, 这两个帐户将以同样的方式同步到 Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="d6649-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="d6649-146">创建远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="d6649-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="d6649-147">请注意, 你将需要下载 Skype for Business Online 连接器模块和 Microsoft Online Services 登录助手, 并确保你的计算机已配置。</span><span class="sxs-lookup"><span data-stu-id="d6649-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="d6649-148">有关详细信息, 请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d6649-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="d6649-149">若要为 Skype for business 启用 Skype 会议室系统帐户, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="d6649-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="d6649-150">你可以使用以下命令返回此属性, 获取你的 Skype for Business 用户从现有帐户之一驻留的 RegistrarPool 地址:</span><span class="sxs-lookup"><span data-stu-id="d6649-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="d6649-151">密码过期</span><span class="sxs-lookup"><span data-stu-id="d6649-151">Password expiration</span></span>

<span data-ttu-id="d6649-152">在 Office 365 中，所有用户帐户的默认密码过期策略是 90 天，除非你配置不同的密码过期策略。</span><span class="sxs-lookup"><span data-stu-id="d6649-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="d6649-153">对于 Skype 会议室系统帐户, 您可以通过以下步骤选择 "密码永不过期" 设置。</span><span class="sxs-lookup"><span data-stu-id="d6649-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="d6649-154">使用你的租户全局管理员凭据创建 Windows Azure Active Directory 会话。</span><span class="sxs-lookup"><span data-stu-id="d6649-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="d6649-155">为以前使用以下命令创建的 Skype 聊天室系统帐户设置密码永不过期设置:</span><span class="sxs-lookup"><span data-stu-id="d6649-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="d6649-156">有关详细信息, 请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d6649-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="d6649-157">复核</span><span class="sxs-lookup"><span data-stu-id="d6649-157">Validate</span></span>

<span data-ttu-id="d6649-158">对于验证, 你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="d6649-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>


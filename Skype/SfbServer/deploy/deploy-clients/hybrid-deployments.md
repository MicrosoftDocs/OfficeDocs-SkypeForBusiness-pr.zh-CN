---
title: Skype 会议室系统混合部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。
ms.openlocfilehash: f6364f7bb96ddf2b25aaaef2a341fce5b71372f5
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003492"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="1192f-103">Skype 会议室系统混合部署</span><span class="sxs-lookup"><span data-stu-id="1192f-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="1192f-104">阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="1192f-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="1192f-105">混合部署</span><span class="sxs-lookup"><span data-stu-id="1192f-105">Hybrid deployments</span></span>

<span data-ttu-id="1192f-106">如果你的拓扑具有 Skype for Business 服务器和 Exchange Online，并且想要在 Exchange Online 上托管 Skype 会议室系统资源邮箱，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1192f-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="1192f-107">此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。</span><span class="sxs-lookup"><span data-stu-id="1192f-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="1192f-108">为了便于说明，我们将 LyncSample.com 用于本地域，而 LyncSample.ccstp.net 用于联机域。</span><span class="sxs-lookup"><span data-stu-id="1192f-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="1192f-109">如 Exchange Online 设置中所述，通过连接到 Exchange Online Management shell，在 Exchange 管理中心（LyncSample.ccsctp.net）中创建资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="1192f-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="1192f-110">你可以使用 lrstest5@LyncSample.ccsctp.net 验证 OWA 连接，以登录。</span><span class="sxs-lookup"><span data-stu-id="1192f-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="1192f-111">在 Office 365 Exchange 管理中心中，添加电子邮件地址 lrstest5@LyncSample.com （在本地域上），并将其设置为答复地址。</span><span class="sxs-lookup"><span data-stu-id="1192f-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="1192f-112">创建本地 Active Directory 用户 lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，并将目标地址设置为 lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="1192f-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="1192f-113">触发器目录同步，并且在同步完成后，验证用户是否在 AAD 中合并以及你无法在 Office365 Exchange 管理中心中更改收件人的资源中的属性。</span><span class="sxs-lookup"><span data-stu-id="1192f-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="1192f-114">使用 lrstest5@LyncSample.com 验证 OWA 连接。</span><span class="sxs-lookup"><span data-stu-id="1192f-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="1192f-115">（更早版本，您使用联机域验证了 OWA 连接。）</span><span class="sxs-lookup"><span data-stu-id="1192f-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="1192f-p103">在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="1192f-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="1192f-118">如果你有 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 命令行管理程序并启用-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。</span><span class="sxs-lookup"><span data-stu-id="1192f-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="1192f-119">随后将触发目录同步。</span><span class="sxs-lookup"><span data-stu-id="1192f-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="1192f-120">如果您想要在 Exchange Online 中托管 Skype 会议室系统邮箱，则不需要这些 Exchange 管理外壳步骤，您可以继续执行步骤6。</span><span class="sxs-lookup"><span data-stu-id="1192f-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="1192f-121">通过在 Skype for business Management Shell 上运行以下 cmdlet，为 Skype for business 启用 Skype 会议室系统帐户：</span><span class="sxs-lookup"><span data-stu-id="1192f-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="1192f-122">如果在上述方案中有 Skype for business Online 而不是 Skype for business 服务器，则在预配 Exchange 资源邮箱后，请按照 Skype for Business Online 设置中所述设置 Skype for business 帐户。</span><span class="sxs-lookup"><span data-stu-id="1192f-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  


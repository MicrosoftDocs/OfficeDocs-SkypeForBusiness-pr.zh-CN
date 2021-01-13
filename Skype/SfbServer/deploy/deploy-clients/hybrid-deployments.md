---
title: Skype 会议室系统混合部署
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805892"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="540af-103">Skype 会议室系统混合部署</span><span class="sxs-lookup"><span data-stu-id="540af-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="540af-104">阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="540af-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="540af-105">混合部署</span><span class="sxs-lookup"><span data-stu-id="540af-105">Hybrid deployments</span></span>

<span data-ttu-id="540af-106">如果你的拓扑具有 Skype for Business Server 和 Exchange Online，并且你想要在 Exchange Online 上托管 Skype 会议室系统资源邮箱，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="540af-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="540af-107">本节还介绍了一种混合方案，其中同时部署了 Exchange Online 和 Exchange Server部署。</span><span class="sxs-lookup"><span data-stu-id="540af-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="540af-108">出于说明目的，我们将LyncSample.com域和LyncSample.ccstp.net域的域。</span><span class="sxs-lookup"><span data-stu-id="540af-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="540af-109">通过连接到 Exchange Online 命令行管理程序 (LyncSample.ccsctp.net) Exchange Online 设置中所述，在 Exchange 管理中心创建资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="540af-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="540af-110">可以使用登录lrstest5@LyncSample.ccsctp.net OWA 连接。</span><span class="sxs-lookup"><span data-stu-id="540af-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="540af-111">在 Microsoft 365 或 Office 365 Exchange 管理中心中，添加lrstest5@LyncSample.com (本地域) 并设置为回复地址。</span><span class="sxs-lookup"><span data-stu-id="540af-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="540af-112">创建内部 Active Directory lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，将目标地址设置为 lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="540af-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="540af-113">触发目录同步，同步完成后，验证用户是否合并到 AAD 中，并且你无法更改 Microsoft 365 或 Office 365 Exchange 管理中心中收件人资源中的属性。</span><span class="sxs-lookup"><span data-stu-id="540af-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="540af-114">使用应用程序验证 OWA lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="540af-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="540af-115"> (之前，您验证了使用联机域.) </span><span class="sxs-lookup"><span data-stu-id="540af-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="540af-116">创建邮箱后，可以使用 Exchange Online 命令行Set-CalendarProcessing命令行管理程序上的配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="540af-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="540af-117">有关更多详细信息，请参阅单林部署下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="540af-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="540af-118">如果混合环境具有 Exchange Server 和 Exchange Online，请转到 Exchange 命令行管理程序，Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room。</span><span class="sxs-lookup"><span data-stu-id="540af-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="540af-119">然后触发目录同步。</span><span class="sxs-lookup"><span data-stu-id="540af-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="540af-120">如果要在 Exchange Online 中托管 Skype 会议室系统邮箱，则不需要执行这些 Exchange 命令行管理程序步骤，可以继续执行步骤 6。</span><span class="sxs-lookup"><span data-stu-id="540af-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="540af-121">在 Skype for Business 命令行管理程序 上运行以下 cmdlet，为 Skype for Business 启用 Skype 会议室系统帐户：</span><span class="sxs-lookup"><span data-stu-id="540af-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="540af-122">如果你在以上方案中拥有 Skype for Business Online 而不是 Skype for Business Server，则预配 Exchange 资源邮箱后，设置 Skype for Business 帐户，如 Skype for Business Online 预配中所述。</span><span class="sxs-lookup"><span data-stu-id="540af-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  


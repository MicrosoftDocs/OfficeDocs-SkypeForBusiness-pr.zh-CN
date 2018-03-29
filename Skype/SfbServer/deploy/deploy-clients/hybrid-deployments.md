---
title: Skype 会议室系统混合部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题，以了解如何在混合环境中部署 Skype 的空间系统。
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="12d55-103">Skype 会议室系统混合部署</span><span class="sxs-lookup"><span data-stu-id="12d55-103">Skype Room System hybrid deployments</span></span>
 
<span data-ttu-id="12d55-104">阅读本主题，以了解如何在混合环境中部署 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="12d55-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="12d55-105">混合部署</span><span class="sxs-lookup"><span data-stu-id="12d55-105">Hybrid deployments</span></span>

<span data-ttu-id="12d55-106">如果您的拓扑结构有 Skype 业务服务器和 Exchange 联机，并且要承载 Exchange Online 上的 Skype 的空间系统资源邮箱，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="12d55-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="12d55-107">此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。</span><span class="sxs-lookup"><span data-stu-id="12d55-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="12d55-108">出于演示目的，我们使用 LyncSample.com 的内部域和 LyncSample.ccstp.net 联机域。</span><span class="sxs-lookup"><span data-stu-id="12d55-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="12d55-109">通过连接到 Exchange 的联机管理外壳，Exchange 的联机资源调配中所述创建 Exchange 管理员中心 (LyncSample.ccsctp.net) 中的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="12d55-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    <span data-ttu-id="12d55-110">可以使用 lrstest5@LyncSample.ccsctp.net 来登录 OWA 连接来验证。</span><span class="sxs-lookup"><span data-stu-id="12d55-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="12d55-111">在 Office 365 Exchange 管理员中心，添加电子邮件地址 lrstest5@LyncSample.com （prem 上域），并将其设置为答复地址。</span><span class="sxs-lookup"><span data-stu-id="12d55-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="12d55-112">创建 prem 在 Active Directory 用户 lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，并将目标地址设置为 lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="12d55-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="12d55-113">目录同步触发，并同步完成后，验证用户合并 AAD 中并且您不能更改属性，在收件人的资源在 Office365 Exchange 管理员中心。</span><span class="sxs-lookup"><span data-stu-id="12d55-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="12d55-114">请验证 OWA 连接使用 lrstest5@LyncSample.com。（早期版本，您验证 OWA 连接使用联机域）。</span><span class="sxs-lookup"><span data-stu-id="12d55-114">Verify OWA connectivity using lrstest5@LyncSample.com. (Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="12d55-p102">在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="12d55-p102">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12d55-117">如果 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 管理外壳程序并启用 RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-房间。</span><span class="sxs-lookup"><span data-stu-id="12d55-117">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="12d55-118">随后将触发目录同步。</span><span class="sxs-lookup"><span data-stu-id="12d55-118">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="12d55-119">如果您想要驻留在 Exchange 在联机 Skype 的空间系统邮箱，这些 Exchange 管理外壳程序步骤不是必需的可以继续到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="12d55-119">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="12d55-120">通过对业务管理外壳在 Skype 上运行以下 cmdlet 让 Skype 业务 Skype 的空间系统帐户：</span><span class="sxs-lookup"><span data-stu-id="12d55-120">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="12d55-121">如果有 Skype 的而不是 Skype 业务在线业务服务器在上述方案中，设置 Exchange 资源邮箱后, 中调配业务帐户业务联机资源调配所述 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="12d55-121">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  


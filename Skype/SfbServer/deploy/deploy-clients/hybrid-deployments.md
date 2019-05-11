---
title: Skype 会议室系统混合部署
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题可了解如何在混合环境中部署 Skype 会议室系统。
ms.openlocfilehash: 2f48707fd4e247a952bc17d26284a8a29eba025a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895171"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="22d70-103">Skype 会议室系统混合部署</span><span class="sxs-lookup"><span data-stu-id="22d70-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="22d70-104">阅读本主题可了解如何在混合环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="22d70-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="22d70-105">混合部署</span><span class="sxs-lookup"><span data-stu-id="22d70-105">Hybrid deployments</span></span>

<span data-ttu-id="22d70-106">如果您的拓扑具有 Skype Business Server 和 Exchange Online 中，并且您希望承载 Exchange Online 上的 Skype 会议室系统资源邮箱，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="22d70-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="22d70-107">此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。</span><span class="sxs-lookup"><span data-stu-id="22d70-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="22d70-108">为便于演示的目的，我们使用 LyncSample.com 内部部署域和 LyncSample.ccstp.net online 域。</span><span class="sxs-lookup"><span data-stu-id="22d70-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="22d70-109">通过 Exchange Online 设置中所述，连接到 Exchange Online 命令行管理程序创建 Exchange 管理员中心 (LyncSample.ccsctp.net) 中的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="22d70-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="22d70-110">您可以验证 OWA 连接使用 lrstest5@LyncSample.ccsctp.net 登录。</span><span class="sxs-lookup"><span data-stu-id="22d70-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="22d70-111">在 Office 365 Exchange 管理中心中，添加电子邮件地址 lrstest5@LyncSample.com （上 prem 域），并将其设置为其作为回复地址。</span><span class="sxs-lookup"><span data-stu-id="22d70-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="22d70-112">创建上 prem Active Directory 用户 lrstest5@LyncSample.com、 设置电子邮件地址为 lrstest5@LyncSample.com，并设置为 lrstest5@LyncSample.com 的目标地址。</span><span class="sxs-lookup"><span data-stu-id="22d70-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="22d70-113">触发目录同步，并且同步完成后，验证用户合并 AAD 中并且您不能在 Office365 Exchange 管理中心中的收件人的资源中更改属性。</span><span class="sxs-lookup"><span data-stu-id="22d70-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="22d70-114">确认使用 lrstest5@LyncSample.com OWA 连接。</span><span class="sxs-lookup"><span data-stu-id="22d70-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="22d70-115">（更早版本，验证使用 online 域的 OWA 连接。）</span><span class="sxs-lookup"><span data-stu-id="22d70-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="22d70-p103">在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="22d70-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="22d70-118">如果您有与 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 命令行管理程序和 Enable-remotemailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-聊天室。</span><span class="sxs-lookup"><span data-stu-id="22d70-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="22d70-119">随后将触发目录同步。</span><span class="sxs-lookup"><span data-stu-id="22d70-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="22d70-120">如果您想要驻留在 Exchange 在联机 Skype 会议室系统邮箱，这些 Exchange 命令行管理程序步骤不需要，可以继续执行步骤 6。</span><span class="sxs-lookup"><span data-stu-id="22d70-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="22d70-121">通过运行以下 cmdlet 上 Skype 业务命令行管理程序启用 for Business 的 Skype Skype 会议室系统帐户：</span><span class="sxs-lookup"><span data-stu-id="22d70-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="22d70-122">如果您有 Skype 而不是 Skype 业务 online 业务服务器在上述情况，然后设置 Exchange 资源邮箱后, 设置业务帐户中所述 Skype 业务联机资源调配 Skype。</span><span class="sxs-lookup"><span data-stu-id="22d70-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  


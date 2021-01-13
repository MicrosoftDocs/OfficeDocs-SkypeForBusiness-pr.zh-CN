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
# <a name="skype-room-system-hybrid-deployments"></a>Skype 会议室系统混合部署

阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果你的拓扑具有 Skype for Business Server 和 Exchange Online，并且你想要在 Exchange Online 上托管 Skype 会议室系统资源邮箱，请按照以下步骤操作。 本节还介绍了一种混合方案，其中同时部署了 Exchange Online 和 Exchange Server部署。
  
出于说明目的，我们将LyncSample.com域和LyncSample.ccstp.net域的域。
  
1. 通过连接到 Exchange Online 命令行管理程序 (LyncSample.ccsctp.net) Exchange Online 设置中所述，在 Exchange 管理中心创建资源邮箱。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    可以使用登录lrstest5@LyncSample.ccsctp.net OWA 连接。
    
2. 在 Microsoft 365 或 Office 365 Exchange 管理中心中，添加lrstest5@LyncSample.com (本地域) 并设置为回复地址。
    
3. 创建内部 Active Directory lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，将目标地址设置为 lrstest5@LyncSample.com。
    
4. 触发目录同步，同步完成后，验证用户是否合并到 AAD 中，并且你无法更改 Microsoft 365 或 Office 365 Exchange 管理中心中收件人资源中的属性。
    
5. 使用应用程序验证 OWA lrstest5@LyncSample.com。  (之前，您验证了使用联机域.) 
    
    创建邮箱后，可以使用 Exchange Online 命令行Set-CalendarProcessing命令行管理程序上的配置邮箱。 有关更多详细信息，请参阅单林部署下的步骤 3 至 6。
    
   > [!NOTE]
   > 如果混合环境具有 Exchange Server 和 Exchange Online，请转到 Exchange 命令行管理程序，Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room。 然后触发目录同步。 
  
    如果要在 Exchange Online 中托管 Skype 会议室系统邮箱，则不需要执行这些 Exchange 命令行管理程序步骤，可以继续执行步骤 6。
    
6. 在 Skype for Business 命令行管理程序 上运行以下 cmdlet，为 Skype for Business 启用 Skype 会议室系统帐户：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果你在以上方案中拥有 Skype for Business Online 而不是 Skype for Business Server，则预配 Exchange 资源邮箱后，设置 Skype for Business 帐户，如 Skype for Business Online 预配中所述。 
  


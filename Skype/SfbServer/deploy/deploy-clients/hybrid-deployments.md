---
title: Skype 会议室系统混合部署
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219672"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 会议室系统混合部署

阅读本主题，了解如何在混合环境中部署 Skype 会议室系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果拓扑具有 Skype for Business Server 和 Exchange Online，并且要在 Exchange Online 上托管 Skype 会议室系统资源邮箱，请执行以下步骤。 本节还介绍了同时部署了 Exchange Online 和 Exchange 服务器的混合方案。
  
出于说明目的，我们将 LyncSample.com 用于本地域，将 LyncSample.ccstp.net 用于联机域。
  
1. 通过连接到 Exchange online Management shell (LyncSample.ccsctp.net) （如 Exchange Online 设置中所述），在 Exchange 管理中心中创建资源邮箱。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以使用 lrstest5@LyncSample.ccsctp.net 验证 OWA 连接以进行登录。
    
2. 在 Microsoft 365 或 Office 365 Exchange 管理中心中，添加一个电子邮件地址 lrstest5@LyncSample.com (本地 domain) 并将其设置为答复地址。
    
3. 创建本地 Active Directory user lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，并将目标地址设置为 lrstest5@LyncSample.com。
    
4. 触发目录同步，并且在同步完成后，请验证用户是否在 AAD 中进行了合并，以及您无法更改 Microsoft 365 或 Office 365 Exchange 管理中心中收件人的资源的属性。
    
5. 使用 lrstest5@LyncSample.com 验证 OWA 连接性。  (之前，您使用联机域验证了 OWA 连接。 ) 
    
    创建邮箱后，您可以使用 Exchange Online 命令行管理程序上的 Set-calendarprocessing 配置邮箱。 有关更多详细信息，请参阅本地部署下的步骤3至6。
    
   > [!NOTE]
   > 如果您具有与 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 命令行管理程序并 New-remotemailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-聊天室。 然后，触发目录同步。 
  
    如果要在 Exchange Online 中托管 Skype 会议室系统邮箱，则不需要这些 Exchange 命令行管理程序步骤，您可以继续执行步骤6。
    
6. 通过在 Skype for Business 命令行管理程序上运行以下 cmdlet 来为 Skype for business 启用 Skype 会议室系统帐户：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果在上述方案中有 Skype for business Online 而不是 Skype for business Server，则在设置 Exchange 资源邮箱之后，请按照 Skype for Business Online 设置中所述设置 Skype for business 帐户。 
  


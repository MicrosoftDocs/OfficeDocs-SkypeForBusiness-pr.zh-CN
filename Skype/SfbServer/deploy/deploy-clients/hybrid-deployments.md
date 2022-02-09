---
title: Skype会议室系统混合部署
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题，了解如何在混合Skype部署会议室系统。
ms.openlocfilehash: 0592d2cb22eb0a8f34e93dc812f011d13b31a53f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400758"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype会议室系统混合部署

阅读本主题，了解如何在混合Skype部署会议室系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果您的拓扑具有 Skype for Business Server 和 Exchange Online，并且您希望在 Exchange Online 上托管 Skype 会议室系统资源邮箱，请按照Exchange Online。 本节还介绍了混合方案，其中你已部署Exchange Online Exchange Server部署。
  
为便于说明，我们将 LyncSample.com 用于本地域，LyncSample.ccstp.net 用于联机域。
  
1. 通过连接到 Exchange 管理 (LyncSample.ccsctp.net) 命令行管理程序Exchange Online在管理中心Exchange Online邮箱。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以验证 OWA 连接，lrstest5@LyncSample.ccsctp.net 登录。
    
2. 在Microsoft 365或Office 365 Exchange管理中心，添加本地域 lrstest5@LyncSample.com (电子邮件地址) 并设置为回复地址。
    
3. 创建一个内部 Active Directory lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，将目标地址设置为 lrstest5@LyncSample.com。
    
4. 触发目录同步，同步完成后，验证用户是否合并到 AAD 以及您是否无法更改 Microsoft 365 或 Office 365 Exchange 管理中心中收件人资源中的属性。
    
5. 使用 OWA 连接验证 lrstest5@LyncSample.com。  (之前，您验证了使用联机域的 OWA ) 
    
    创建邮箱后，可以在命令行Set-CalendarProcessing命令行管理Exchange Online配置邮箱。 有关更多详细信息，请参阅单林就地部署下的步骤 3 至 6。
    
   > [!NOTE]
   > 如果您的混合环境具有 Exchange Server 和 Exchange Online，请转到 Exchange 命令行管理程序，Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room。 然后触发目录同步。 
  
    如果要在 Exchange Online 中托管Skype会议室系统邮箱，Exchange命令行管理程序步骤，您可以继续执行步骤 6。
    
6. 在命令行Skype程序上运行以下 cmdlet，Skype for Business会议室系统帐户Skype for Business帐户：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果已Skype for Business Online 而不是 Skype for Business Server，则设置 Exchange 资源邮箱后，设置 Skype for Business 帐户，如Skype for Business 联机预配。 
  


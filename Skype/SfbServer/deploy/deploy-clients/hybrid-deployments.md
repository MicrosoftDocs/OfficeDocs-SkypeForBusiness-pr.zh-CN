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
# <a name="skype-room-system-hybrid-deployments"></a>Skype 会议室系统混合部署
 
阅读本主题，以了解如何在混合环境中部署 Skype 的空间系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果您的拓扑结构有 Skype 业务服务器和 Exchange 联机，并且要承载 Exchange Online 上的 Skype 的空间系统资源邮箱，请执行以下步骤。 此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。
  
出于演示目的，我们使用 LyncSample.com 的内部域和 LyncSample.ccstp.net 联机域。
  
1. 通过连接到 Exchange 的联机管理外壳，Exchange 的联机资源调配中所述创建 Exchange 管理员中心 (LyncSample.ccsctp.net) 中的资源邮箱。
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    可以使用 lrstest5@LyncSample.ccsctp.net 来登录 OWA 连接来验证。
    
2. 在 Office 365 Exchange 管理员中心，添加电子邮件地址 lrstest5@LyncSample.com （prem 上域），并将其设置为答复地址。
    
3. 创建 prem 在 Active Directory 用户 lrstest5@LyncSample.com，将电子邮件地址设置为 lrstest5@LyncSample.com，并将目标地址设置为 lrstest5@LyncSample.com。
    
4. 目录同步触发，并同步完成后，验证用户合并 AAD 中并且您不能更改属性，在收件人的资源在 Office365 Exchange 管理员中心。
    
5. 请验证 OWA 连接使用 lrstest5@LyncSample.com。（早期版本，您验证 OWA 连接使用联机域）。
    
    在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。
    
    > [!NOTE]
    > 如果 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 管理外壳程序并启用 RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-房间。 随后将触发目录同步。 
  
    如果您想要驻留在 Exchange 在联机 Skype 的空间系统邮箱，这些 Exchange 管理外壳程序步骤不是必需的可以继续到步骤 6。
    
6. 通过对业务管理外壳在 Skype 上运行以下 cmdlet 让 Skype 业务 Skype 的空间系统帐户：
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果有 Skype 的而不是 Skype 业务在线业务服务器在上述方案中，设置 Exchange 资源邮箱后, 中调配业务帐户业务联机资源调配所述 Skype Skype。 
  


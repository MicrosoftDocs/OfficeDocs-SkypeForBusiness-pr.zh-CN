---
title: Skype 会议室系统混合部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题可了解如何在混合环境中部署 Skype 会议室系统。
ms.openlocfilehash: 40cbcd7cd95b6a5dc7542f913fe7599bedc7eb85
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699670"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 会议室系统混合部署

阅读本主题可了解如何在混合环境中部署 Skype 会议室系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果您的拓扑具有 Skype Business Server 和 Exchange Online 中，并且您希望承载 Exchange Online 上的 Skype 会议室系统资源邮箱，请按照以下步骤。 此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。
  
为便于演示的目的，我们使用 LyncSample.com 内部部署域和 LyncSample.ccstp.net online 域。
  
1. 通过 Exchange Online 设置中所述，连接到 Exchange Online 命令行管理程序创建 Exchange 管理员中心 (LyncSample.ccsctp.net) 中的资源邮箱。
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以验证 OWA 连接使用 lrstest5@LyncSample.ccsctp.net 登录。
    
2. 在 Office 365 Exchange 管理中心中，添加电子邮件地址 lrstest5@LyncSample.com （上 prem 域），并将其设置为其作为回复地址。
    
3. 创建上 prem Active Directory 用户 lrstest5@LyncSample.com、 设置电子邮件地址为 lrstest5@LyncSample.com，并设置为 lrstest5@LyncSample.com 的目标地址。
    
4. 触发目录同步，并且同步完成后，验证用户合并 AAD 中并且您不能在 Office365 Exchange 管理中心中的收件人的资源中更改属性。
    
5. 确认使用 lrstest5@LyncSample.com OWA 连接。 （更早版本，验证使用 online 域的 OWA 连接。）
    
    在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。
    
   > [!NOTE]
   > 如果您有与 Exchange Server 和 Exchange Online 的混合环境，请转到 Exchange 命令行管理程序和 Enable-remotemailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-聊天室。 随后将触发目录同步。 
  
    如果您想要驻留在 Exchange 在联机 Skype 会议室系统邮箱，这些 Exchange 命令行管理程序步骤不需要，可以继续执行步骤 6。
    
6. 通过运行以下 cmdlet 上 Skype 业务命令行管理程序启用 for Business 的 Skype Skype 会议室系统帐户：
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果您有 Skype 而不是 Skype 业务 online 业务服务器在上述情况，然后设置 Exchange 资源邮箱后, 设置业务帐户中所述 Skype 业务联机资源调配 Skype。 
  


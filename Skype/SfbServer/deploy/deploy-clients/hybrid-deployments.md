---
title: Skype 会议室系统混合部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 阅读本主题, 了解如何在混合环境中部署 Skype 会议室系统。
ms.openlocfilehash: 37ed625ca97ba34a30ec6f4acbabce272ef6ac50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293618"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 会议室系统混合部署

阅读本主题, 了解如何在混合环境中部署 Skype 会议室系统。
  
## <a name="hybrid-deployments"></a>混合部署

如果你的拓扑具有 Skype for Business 服务器和 Exchange Online, 并且想要在 Exchange Online 上托管 Skype 会议室系统资源邮箱, 请执行以下步骤。 此部分还介绍部署了 Exchange Online 和 Exchange Server 的混合方案。
  
为了便于说明, 我们将 LyncSample.com 用于本地域, 而 LyncSample.ccstp.net 用于联机域。
  
1. 如 Exchange Online 设置中所述, 通过连接到 Exchange Online Management shell, 在 Exchange 管理中心 (LyncSample.ccsctp.net) 中创建资源邮箱。
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    你可以使用 lrstest5@LyncSample.ccsctp.net 验证 OWA 连接, 以登录。
    
2. 在 Office 365 Exchange 管理中心中, 添加电子邮件地址 lrstest5@LyncSample.com (在本地域上), 并将其设置为答复地址。
    
3. 创建本地 Active Directory 用户 lrstest5@LyncSample.com, 将电子邮件地址设置为 lrstest5@LyncSample.com, 并将目标地址设置为 lrstest5@LyncSample.com。
    
4. 触发器目录同步, 并且在同步完成后, 验证用户是否在 AAD 中合并以及你无法在 Office365 Exchange 管理中心中更改收件人的资源中的属性。
    
5. 使用 lrstest5@LyncSample.com 验证 OWA 连接。 (更早版本, 您使用联机域验证了 OWA 连接。)
    
    在创建邮箱之后，你可以在 Exchange Online 命令行管理程序上使用 Set-CalendarProcessing 来配置邮箱。有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。
    
   > [!NOTE]
   > 如果你有 Exchange Server 和 Exchange Online 的混合环境, 请转到 Exchange 命令行管理程序并启用-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。 随后将触发目录同步。 
  
    如果您想要在 Exchange Online 中托管 Skype 会议室系统邮箱, 则不需要这些 Exchange 管理外壳步骤, 您可以继续执行步骤6。
    
6. 通过在 Skype for business Management Shell 上运行以下 cmdlet, 为 Skype for business 启用 Skype 会议室系统帐户:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果在上述方案中有 Skype for business Online 而不是 Skype for business 服务器, 则在预配 Exchange 资源邮箱后, 请按照 Skype for Business Online 设置中所述设置 Skype for business 帐户。 
  


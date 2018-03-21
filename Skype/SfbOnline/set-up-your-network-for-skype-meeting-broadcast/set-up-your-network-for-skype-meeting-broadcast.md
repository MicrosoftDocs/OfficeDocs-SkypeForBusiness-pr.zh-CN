---
title: "设置 Skype 会议直播网络"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 9dab3a7e74b9f69a3df6bd06c3ad868d109343fe
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>设置 Skype 会议直播网络

[启用 Skype 会议广播](enable-skype-meeting-broadcast.md)Skype 会议广播之后，您需要配置您的网络。 如果要为您的公司外部的人员担任研讨会和其他广播，请执行此步骤。
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
若要跳过此步骤，以便对广播邀请到您联盟改为添加另一个业务按照中[允许用户与外部的业务用户的 Skype](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步骤。
  
## <a name="step-1-set-up-allowed-domains"></a>步骤 1： 设置允许域

使用**一个**下列方法之一来设置允许的域：
  
### 

 **方法 1： 使用 Office 365 管理中心**
  
1. 请转到**Office 365 管理的中心**，然后在左侧的导航中，单击**设置** > **服务&amp;的外接程序**，然后选择**为公司 Skype**。
    
2. 在**域的例外情况**下**外部共享**页中，选择**所有域都被都阻止，但**，并输入下面的域中，使用逗号 （，） 分隔：
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. 单击" **保存**"。
    
### 

 **方法 2： 使用 Windows PowerShell**
  
- 从**开始菜单**中，用鼠标右键单击**Windows PowerShell** ，单击**以管理员身份运行**。 In the **Windows PowerShell** window, type each line and press Enter.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>步骤 2： 添加 Skype 会议广播域、 Url 和 IP 地址

在安装过程中的第二步是第一次添加域的需要然后添加 IP 地址和 Url 所需的 Skype 会议广播工作。
  
- **添加所需的 Skype 的在线业务的端点 Url，都需要通过查看哪些 IP 地址**[这里](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合部署和组织中设置 Skype 会议直播

如果您具有的业务服务器 2015年 Skype 的在线业务的组织和内部部署 Lync Server 2010、 Microsoft Lync Server 2013 和 Skype 和具有两个用户在线，内部，有需要为在其他安装步骤除了上面来使您的内部组织与 Skype 通信业务在线，并允许所有的用户能够创建并加入 Skype 会议广播的。 若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](https://go.microsoft.com/fwlink/?LinkId=617070)。
  
## <a name="related-topics"></a>相关主题

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)
  
[Office 365 URL 和 IP 地址范围](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  


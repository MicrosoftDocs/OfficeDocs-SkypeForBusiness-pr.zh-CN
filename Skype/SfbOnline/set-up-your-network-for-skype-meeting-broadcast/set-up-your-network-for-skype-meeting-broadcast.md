---
title: 设置 Skype 会议直播网络
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: f9a85a1f64f88b55d99c7a27694a46b7ea885849
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301285"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>设置 Skype 会议直播网络

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)Skype 会议直播后, 您需要配置您的网络。 如果要为您的企业外部的人员保留网络研讨会和其他广播, 请执行此步骤。

如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。

若要跳过此步骤, 改为将其他企业添加到联盟, 以便邀请他们进行广播, 请按照[允许用户联系外部 Skype For business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)中的步骤操作。

## <a name="step-1-set-up-allowed-domains"></a>步骤 1: 设置允许的域

使用下列方法**之一**设置允许的域:

## #

 **方法 1: 使用 Office 365 管理中心**

1. 转到**Office 365 管理中心**, 然后在左侧导航栏中, 单击 "**设置** > **服务&amp;加载项**", 然后选择 " **Skype for**business"。

2. 在 "**外部共享**" 页面上的 "**域例外**" 下, 选择 "**所有域均被阻止, 但不**包括", 然后输入以逗号 (,) 分隔的以下域:

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. 单击" **保存**"。

## #

 **方法 2: 使用 Windows PowerShell**

- 在 "**开始" 菜单**上, 右键单击 " **Windows PowerShell** ", 然后单击 "**以管理员身份运行**"。 In the **Windows PowerShell** window, type each line and press Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>步骤 2: 添加 Skype 会议直播域、Url 和 IP 地址

安装过程中的第二个步骤是: 首先添加所需的域, 然后添加要使用的 Skype 会议直播所需的 IP 地址和 Url。

- **通过查看所需的 Skype for Business Online 终结点 url 和 IP 地址来添加这些 url 和 IP 地址**[此处](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合部署和组织中设置 Skype 会议直播

如果你有 Skype for Business Online 组织和 Lync Server 2010、Microsoft Lync Server 2013 和 Skype for Business Server 2015 的本地部署, 并且用户已联机和本地使用, 则需要执行其他设置步骤除了上面的组织, 让您的本地组织能够与 Skype for business Online 通信, 并允许所有用户加入 Skype 会议直播。 若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](https://go.microsoft.com/fwlink/?LinkId=617070)。

## <a name="related-topics"></a>相关主题

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)

[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)




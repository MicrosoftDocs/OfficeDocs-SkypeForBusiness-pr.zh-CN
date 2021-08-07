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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: e5248ca2f8b8bb8080eae5eebe44e3d7c5bc01f5
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725355"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>设置 Skype 会议直播网络

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

启用[Skype 会议 广播](enable-skype-meeting-broadcast.md)Skype 会议广播后，需要配置网络。 如果要为企业外部人员举办网络研讨会和其他直播，请执行此步骤。

> [!IMPORTANT]
> Skype for BusinessOnline 将于 2021 年 7 月 31 日停用，此时将结束对服务的访问。 我们鼓励客户开始升级到 Microsoft Teams（Microsoft 365 中通信和团队合作的核心Microsoft 365。

如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。

若要跳过此步骤，改为将另一个企业添加到联合身份验证，以便可以邀请他们加入直播，请按照允许用户与外部用户Skype for Business[中的步骤](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)操作。

## <a name="step-1-set-up-allowed-domains"></a>步骤 1：设置允许的域

使用以下 **方法** 之一设置允许的域：

### <a name="method-1-use-the-admin-center"></a>方法 1：使用管理中心

1. 转到管理中心，然后在左侧导航中单击"设置服务加载项"，  >  然后选择 **&amp;****"Skype for Business"。**

2. 在"**外部** 共享"页面上的"域例外"下，选择"阻止所有域（除 ）"，然后输入以下域，用逗号分隔 (，) ：

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. 单击" **保存**"。

### <a name="method-2-use-windows-powershell"></a>方法 2：使用Windows PowerShell

- 在"**开始"菜单中**，**右键单击** Windows PowerShell并单击"**以管理员角色运行"。** In the **Windows PowerShell** window, type each line and press Enter.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>步骤 2：Skype 会议广播域、URL 和 IP 地址

设置过程的第二步是先添加所需的域，然后添加运行广播所需的 IP Skype 会议 URL。

- **通过在此处Skype for Business** 所需的终结点 URL 和 IP 地址，添加所需的 [终结点和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合部署和组织中设置 Skype 会议直播

如果您有一个 Skype for Business Online 组织和 Lync Server 2010、Microsoft Lync Server 2013 和 Skype for Business Server 2015 本地部署，并且用户同时在线和本地，则除了上述设置步骤之外，还需要执行其他设置步骤，以使您的本地组织能够与 Skype for Business Online 通信并允许所有用户加入 Skype 会议 Broadcast。 若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。

## <a name="related-topics"></a>相关主题

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)

[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

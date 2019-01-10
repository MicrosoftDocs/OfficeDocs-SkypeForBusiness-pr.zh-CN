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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: b29ec51ddcb672f6727f7bc43958872962245ebb
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788972"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>设置 Skype 会议直播网络

[启用 Skype 会议广播](enable-skype-meeting-broadcast.md)Skype 会议广播后，您需要配置您的网络。 如果您想要保留的您的公司外部的人员的网络研讨会和其他广播，请执行此步骤。

如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。

若要跳过此步骤和改为将另一个业务添加到您的联合身份验证，以便您可以邀请他们加入广播，按照中[允许用户为企业用户的外部 Skype 联系人](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步骤。

## <a name="step-1-set-up-allowed-domains"></a>步骤 1： 设置允许的域

使用**一个**下列方法之一来设置允许的域：

## #

 **方法 1： 使用 Office 365 管理中心**

1. 转到**Office 365 管理中心**，然后在左侧导航窗格中，单击**设置** > **服务&amp;外接程序**，然后选择**for Business 的 Skype**。

2. 在下**域例外****外部共享**页上，选择**除阻止所有域**，并输入下列域，以逗号 （，） 分隔：

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. 单击" **保存**"。

## #

 **方法 2： 使用 Windows PowerShell**

- 从**开始菜单**中，右键单击**Windows PowerShell** ，然后单击**以管理员身份运行**。 In the **Windows PowerShell** window, type each line and press Enter.

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

您可以先添加所需，然后添加 IP 地址和所需的 Skype 会议广播工作的 Url 的域是安装过程的第二步。

- **添加业务联机终结点 Url 的所需的 Skype 和都需要通过查看哪些的 IP 地址**[此处](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合部署和组织中设置 Skype 会议直播

如果您具有业务服务器 2015年业务 Online 组织和 Lync Server 2010、 Microsoft Lync Server 2013 和 Skype 的内部部署 Skype 联机具有两个用户和内部部署，您将需要中实现的其他安装步骤除了上文启用内部部署组织与 Skype 的业务联机通信并允许所有用户加入 Skype 会议广播所示。 若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](https://go.microsoft.com/fwlink/?LinkId=617070)。

## <a name="related-topics"></a>相关主题

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)

[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)




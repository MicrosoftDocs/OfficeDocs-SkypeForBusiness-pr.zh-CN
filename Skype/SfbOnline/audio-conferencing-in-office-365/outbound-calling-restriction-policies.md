---
title: 音频会议和用户 PSTN 呼叫的出站呼叫限制策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 呼叫可以做的用户的类型。
ms.openlocfilehash: ab6f34e46ceb6a9811830ba1444278db667de73c
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 呼叫的出站呼叫限制策略

作为管理员，可以使用出站呼叫控制来限制音频会议和最终用户 PSTN 呼叫，可以由组织中的用户的类型。 

出站呼叫控制可以在每用户基础上应用，并提供以下两个控件分别限制出站呼叫的每个类型。 默认情况下，这两个控件设置为允许国际和国内的出站调用。 

|控件|说明|控制选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制类型的出站 </br>从允许的调用 </br>组织的用户的会议。|国际和国内 （默认值）</br>国内</br>无|
|最终用户 PSTN 呼叫|限制类型的调用 </br>可以由用户进行的。|国际和国内 （默认值）</br>国内</br>无|

   > [!NOTE]
   > 确定调用是如果被调用的电话号码是 （对于音频会议） 会议或最终用户 （如果是最终用户 PSTN 呼叫） 的组织设置 Office 365 中的国家/地区作为同一个国家在国内。 


## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议的出站调用 

**使用 Microsoft 小组和 Skype 业务管理中心**

1. 在左侧的导航中，单击**用户**，然后从可用的用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 单击**会议桥**边上的菜单，然后在下拉列表中单击**编辑**。

4. 在**桥的会议提供程序**窗格中的**限制到此用户的会议中拨出**下,，选择所需的拨出限制选项。

5. 单击“**应用**”。 

**使用 Skype 业务管理中心**

1.  在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，然后选择可用的用户列表中用户。

2.  在"操作"窗格中，单击" **编辑**"。

3.  在**限制到此用户的会议中拨出**选择所需的拨出限制选项。

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. 单击" **保存**"。

**使用 PowerShell**

由一个称为 OnlineDialOutPolicy 具有限制属性为每个策略控制出站呼叫限制。 不能自定义策略，而是在预定义的策略情况下，每个组合的设置。 

可以使用 Get CSOnlineDialOutPolicy cmdlet 以查看出站调用策略并将它们分配给用户，通过授予 CSDialOutPolicy cmdlet。 （请注意，授予 cmdlet 不包含单词"联机"Get cmdlet 一样。） 

下表概述了每个策略。

|||
|:-----|:-----|
|标识 = 标记： DialoutCPCandPSTNInternational    |    会议中的用户可以对国际和国内数字拨出，该用户还可以为国际和国内的数字的出站调用。    |
|标识 = 标记： DialoutCPCDomesticPSTNInternational  |    在会议中的用户只能拨出对国内数字，和此用户可以进行出站呼叫的国际和国内的号码。    |
|    标识 = 标记： DialoutCPCDisabledPSTNInternational    |    在会议中的用户无法进行任何拨。此用户可以制作出站呼叫的国际和国内的号码。    |
|    标识 = 标记： DialoutCPCInternationalPSTNDomestic    |    用户在大会于国际和国内的号码，可拨出和此用户只能使国内 PSTN 号码的出站调用。    |
|    标识 = 标记： DialoutCPCInternationalPSTNDisabled    |    于国际和国内的号码，用户在会议中的可以拨出，该用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。    |
|    标识 = 标记： DialoutCPCandPSTNDomestic    |    在会议中的用户只能拨出对国内数字，和该用户只能使国内 PSTN 号对出站调用。    |
|    标识 = 标记： DialoutCPCDomesticPSTNDisabled    |    在会议中的用户只能拨出对国内数字，和此用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。    |
|    标识 = 标记： DialoutCPCDisabledPSTNDomestic    |    在会议中的用户不能进行任何拨出，并且此用户只能使国内 PSTN 号对出站调用。    |
|    标识 = 标记： DialoutCPCandPSTNDisabled    |    在会议中的用户不能进行任何拨出，并且此用户不能进行任何出站呼叫 PSTN 数字除了紧急号码。    |

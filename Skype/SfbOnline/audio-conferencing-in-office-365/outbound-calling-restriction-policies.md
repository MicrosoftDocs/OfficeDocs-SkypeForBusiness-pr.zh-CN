---
title: 出站调用的限制策略的音频会议和用户 PSTN 呼叫
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: 0533a15d6c60720f37c859f110b30af617d95774
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703421"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>出站调用的限制策略的音频会议和用户 PSTN 呼叫

作为管理员，您可以使用出站呼叫控件来限制的音频会议和最终用户 PSTN 的呼叫可以由组织中用户的类型。 

出站呼叫控件可以应用基于每个用户，并提供了下列两个控件，以便独立限制每种类型的出站呼叫。 默认情况下，这两个控件设置为允许国际和国内出站呼叫。 

|控件|说明|控制选项|
|:-----|:-----|:-----|
|音频会议的 PSTN 呼叫|限制的出站的类型 </br>从中允许的呼叫 </br>由用户组织的会议。|国际和国内 （默认值）</br>国内</br>无|
|最终用户 PSTN 呼叫|限制呼叫的类型 </br>可以由用户进行的。|国际和国内 （默认值）</br>国内</br>无|

   > [!NOTE]
   > 呼叫被确定为国内如果的呼叫的电话号码位于相同的国家/地区作为会议 （对于音频会议） 或最终用户 （对于最终用户 PSTN 呼叫） 的组织者设置 Office 365 中的国家或地区。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫 

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 单击**会议网桥**，旁边的菜单，然后单击下拉列表中的**编辑**。

4. 在**会议桥提供程序**窗格中的**为此用户的会议的电话拨出的限制**下,，选择所需的电话拨出式限制选项。

5. 单击“**应用**”。 

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

1.  在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。

2.  在"操作"窗格中，单击" **编辑**"。

3.  在**为此用户的会议的电话拨出的限制**选择所需的电话拨出式限制选项。

    ![电话拨出选项限制](../images/restrictions-to-dial-outs.png)

5. 单击" **保存**"。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站呼叫限制由一个策略调用 OnlineDialOutPolicy 其中每个具有限制属性控制。 不能自定义策略，而是有预定义的策略设置的每个组合的实例。 

Get CSOnlineDialOutPolicy cmdlet 可用于查看的出站呼叫的策略和使用授予 CSDialOutPolicy cmdlet 将其分配给用户。 （请注意，授予 cmdlet 不包含单词"联机"Get cmdlet 一样。） 

下表概述了每个策略。

|||
|:-----|:-----|
|标识 = 标记： DialoutCPCandPSTNInternational    |    在会议中的用户可以发起电话拨出到国际和国内号码和此用户还可以发出对国际和国内号码的出站呼叫。    |
|标识 = 标记： DialoutCPCDomesticPSTNInternational  |    用户在会议中的只能拨出到国内号码和此用户只能发出对国际和国内号码的出站呼叫。    |
|    标识 = 标记： DialoutCPCDisabledPSTNInternational    |    在会议中的用户无法使任意电话拨。此用户可以发起出站呼叫对国际和国内号码。    |
|    标识 = 标记： DialoutCPCInternationalPSTNDomestic    |    在会议中的用户可以发起电话拨出到国际和国内号码和此用户只能出国内 PSTN 号码的出站呼叫。    |
|    标识 = 标记： DialoutCPCInternationalPSTNDisabled    |    在会议中的用户可以发起电话拨出到国际和国内号码和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。    |
|    标识 = 标记： DialoutCPCandPSTNDomestic    |    用户在会议中的只能拨出到国内号码和此用户可以仅出站呼叫国内 PSTN 号码。    |
|    标识 = 标记： DialoutCPCDomesticPSTNDisabled    |    用户在会议中的只能拨出到国内号码和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。    |
|    标识 = 标记： DialoutCPCDisabledPSTNDomestic    |    在会议中的用户无法使任意拨出和该用户可以仅出站呼叫国内 PSTN 号码。    |
|    标识 = 标记： DialoutCPCandPSTNDisabled    |    在会议中的用户无法使任意拨出和此用户无法进行任何出站呼叫紧急号码除了 PSTN 号码。    |

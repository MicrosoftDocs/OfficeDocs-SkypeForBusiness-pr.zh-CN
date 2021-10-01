---
title: 设置组织内的电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: 分步指南详细介绍了如何在 电话系统 (或) 中为组织Microsoft 365云 PBX Office 365。
ms.openlocfilehash: 51884f63485b1509dbf9ee72739bc0e85385e940
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046138"
---
# <a name="set-up-phone-system-in-your-organization"></a>在组织中设置电话系统

下面是有关在 电话系统 或 Microsoft 365 中设置Office 365 的分步指南。 在每个步骤的末尾都提供指向其他详细信息的链接。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步骤 1： 请确保您的国家或地区可用使用电话系统

1.    首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。 
2.    在 **电话系统** ，下查看的功能和详细信息的列表。 
3.    如果可用电话系统，转到步骤 2。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步骤 2： 购买和分配电话系统和通话套餐许可证

若要将电话系统和呼叫计划许可证分配给单个用户，步骤与分配Microsoft 365或Office 365相同。  也可以批量向多个用户分配许可证。 有关详细信息，请参阅[分配Microsoft Teams许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

如果呼叫计划不适用于你的国家/地区，请考虑使用直接路由将本地电话基础结构连接到电话系统。  有关详细信息，请参阅直接[电话系统路由](direct-routing-landing-page.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3：获取用户的电话号码

在将组织中用户设置为拨打和接听电话之前，必须获取其电话号码。

有三种方法可获取用户的数字：

- 使用管理中心获取Teams号码。
- 获取在管理中心内不可用Teams号码。
- 将现有号码从当前服务提供商或电话运营商转Microsoft 365或Office 365。

必须使用"添加 **号码"** 页面查看、搜索、获取和保留这些数字。 可以按"国家/地区、省/市/自治区"和"城市"进行搜索，然后输入用户所需的电话号码数。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>使用管理中心获取Teams电话号码

1. 使用工作Microsoft 365登录帐户。

2. 转到 **"Teams管理中心"。**
    
3. 在左侧导航中，转到"语音  >  电话"，单击"**添加**"，然后按照提示操作。
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>获取在管理中心内不可用Teams号码
  
有时 (你的国家/地区) 你将无法使用管理中心获取新Teams号码。 在这种情况下，需要下载表单并将其发回给我们。 若要了解如何请求新用户号码，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果你的用户需要的电话号码数少于 999 个，可以在管理中心使用"新建本地号码Teams向导。 按照[将电话号码转接](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)到 Teams中的步骤转移电话号码。
    
- 如果需要移植超过 999 个电话号码，请参阅管理组织[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的电话号码以提交移植订单服务请求或订单。 

有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）

除了从 Microsoft 365 或 Office 365 获取用户的电话号码外，还可以搜索和获取音频会议 (会议网桥) 、自动助理和呼叫队列等服务的收费或免费电话号码。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>使用管理中心获取Teams号码


1. 使用工作或学校帐户登录。

2. 转到 **"Teams管理中心"。**

3. 在左侧导航窗格中，转到"语音转电话  >    >  **号码""** 添加新号码"，然后单击"新建 **服务号码"。**

    > [!IMPORTANT]
    > 若要在 Teams管理中心的左侧导航窗格中查看"语音"选项，必须先购买至少一个 **Enterprise E5** 许可证、一个 **电话系统** 附加许可证或一个音频会议附加许可证。 

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>获取在管理中心内不可用Teams号码
  
有时 (你的国家/地区) 你将无法使用管理中心获取新Teams号码。 在这种情况下，需要下载表单并将其发回给我们。 若要了解如何请求新号码，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。 需要针对每种类型的服务号码（收费 (收费和免费）提交单独的转) 订单，使用授权书 (LOA) 。 在 LOA (授权书) ，必须选择正确的服务编号类型。 联系 Microsoft 支持部门时，请指定要转移服务号码 (而不是用户或订阅者号码 *) ，* 否则并发呼叫容量可能不足以处理呼叫量。 如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步骤 5： 如果您想要设置调用计划

如果你一直在遵循以上步骤，您已购买并分配电话系统和许可证以及通话套餐 （第 2 步）并且为用户获取电话号码（第 3 步），因此您通话套餐i已部分设置。 若要完成设置呼叫计划的过程，请参阅 [设置呼叫计划](set-up-calling-plans.md)。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步骤 6： 如果您想要设置音频会议

有时，组织中的人员需要使用电话拨入会议。 Microsoft Teams音频会议功能仅针对这种情况。 用户可以使用电话Teams会议，而不是使用移动设备Teams或电脑上的 Teams 应用。
若要了解如何设置音频会议，请参阅为会议设置[音频Teams。](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>步骤 7：如果要设置云呼叫队列

云呼叫队列包括当某人呼叫你的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的能力，以及搜索下一个可用的呼叫代理以在呼叫者正在收听保持音乐时处理呼叫的能力。 你可以为组织创建单个或多个呼叫队列。

有关呼叫队列的信息，请参阅 [创建云呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>步骤 8：如果要设置云自动助理

自动助理允许呼叫组织并导航菜单系统以将其转到正确的部门、呼叫队列、人员或接线员。 可以使用管理中心为组织创建Teams助理。

有关设置云自动出席者的信息，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md)。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）

一旦您从 **上面的步骤 4** 获得服务号码后，您需要将其分配给所需每种类型服务。 例如，如果你想要收费或免费 (专用服务电话号码) ，则需要将号码分配给会议网桥。

- 对于音频会议，你可以为会议网桥分配专用号码，Teams管理中心  >  **会议** 网桥并按照  >  提示。  有关详细信息，请参阅更改音频  [会议](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)网桥上的收费或免费号码。

- 对于自动助理，你可以向自动助理分配专用号码，Teams管理中心语音自动助理并按照  >    >  提示进行分配。  有关详细信息，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md)。

- 对于呼叫队列，可以通过访问管理中心语音呼叫队列Teams呼叫队列并按照提示操作，为呼叫 **队列** 分配专用  >    >  号码。 有关详细信息，请参阅 [创建云呼叫队列](create-a-phone-system-call-queue.md)。

有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步骤 10：为组织设置通信信用额度

如果要将免费电话号码与 Microsoft Teams，则需要设置通信信用额度。 Microsoft 建议你为呼叫计划设置通信 (国内或国际) 和音频会议用户，这些用户需要能够拨出到任何目的地。 包括许多国家/地区，但某些目的地可能不包含在呼叫计划或音频会议订阅中。 

如果未设置通信信用额度计费并将通信信用额度许可证分配给用户，并且你的组织 (根据你的呼叫计划或音频会议计划在你的国家/地区) 中用完了分钟数，则这些用户将无法进行呼叫或从音频会议会议拨出。 有关详细信息，包括建议的资金金额，请参阅 [什么是通信信用额度？](what-are-communications-credits.md) 和为组织设置通信 [信用额度](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>相关主题
[以下是在电话系统或Microsoft 365 Office 365](here-s-what-you-get-with-phone-system.md)

[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 

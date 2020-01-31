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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为你的组织设置电话系统（云 PBX）。 '
ms.openlocfilehash: d4d8927e2abda35ff8cb3346218cb3c4cda9c049
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628398"
---
# <a name="set-up-phone-system-in-your-organization"></a>在组织中设置电话系统

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步骤 1： 请确保您的国家或地区可用使用电话系统

1.  首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。 
2.  在 **电话系统** ，下查看的功能和详细信息的列表。 
3.  如果可用电话系统，转到步骤 2。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步骤 2： 购买和分配电话系统和通话套餐许可证

若要向单个用户分配电话系统和呼叫计划许可证，步骤与分配 Office 365 许可证相同。  您还可以批量将许可证分配给多个用户。 有关详细信息，请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。

如果通话计划不适用于您所在的国家或地区，请考虑使用直接路由将本地电话基础结构连接到电话系统。  有关详细信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤3：为用户获取电话号码

在您可以将组织中的用户设置为拨打和接收电话呼叫之前，您必须为他们获取电话号码。

有三种方法可为用户获取号码：
- 使用团队管理中心获取新号码。
- 获取团队管理中心中不可用的新号码。
- 将您的现有服务提供商或电话运营商中的现有号码移植或转移到 Office 365。

您必须使用 "**添加号码**" 页面查看、搜索、获取和保留这些号码。 您可以按国家/地区、省/市/县和市/县进行搜索，然后输入您需要的用户电话号码的数量。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>使用团队管理中心获取新的用户电话号码

1. 使用你的工作或学校帐户登录 Microsoft 365。

2. 转到 "**团队管理中心**"。
    
3. 在左侧导航中，转到 "**语音** > **电话号码**"，单击 "**添加**"，然后按照提示进行操作。
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>获取团队管理中心中不可用的新号码
  
有时（取决于您所在的国家/地区）您将无法使用团队管理中心获取您的新号码。 在这种情况下，你需要下载表单并将其发送给我们。 若要了解如何申请新的用户号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- 如果您需要999或更少的用户电话号码，您可以使用团队管理中心中的 "**新的本地号码" 端口订单**向导。 按照将[电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)转移电话号码中找到的步骤进行操作。
    
- 如果您需要移植超过999的电话号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交 "订单" 服务请求或订单。 

有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）

除了从 Office 365 中获取用户的电话号码之外，您还可以搜索和获取服务的收费电话号码或免费电话号码，如音频会议（适用于会议桥）、自动助理和呼叫队列。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，服务号码可以同时处理数百个通话，而用户的电话号码只能同时处理多个通话。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>使用团队管理中心获取新的服务号码


1. 使用你的工作或学校帐户登录 Office 365。

2. 转到 "**团队管理中心**"。

3. 在左侧导航窗格中，转到 "**语音** > **电话号码** > "**添加新号码**，然后单击 "**新的服务号码**"。

    > [!IMPORTANT]
    > 要在团队管理中心的左侧导航窗格中看到 "**语音**" 选项，您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>获取团队管理中心中不可用的新号码
  
有时（取决于您所在的国家/地区）您将无法使用团队管理中心获取您的新号码。 在这种情况下，你将需要下载表单并将其发送给我们。 若要了解如何申请新号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。 您需要为每种类型的服务号码（如收费电话）提交单独的端口订单，您将使用授权书（LOA）进行转移。 在授权书（LOA）中，您必须选择正确的服务号码类型。 联系 Microsoft 支持时，请指定你正在转移服务号码（*而不是用户或订阅者号码*），或者同时拨打的通话量可能不足以处理呼叫卷。 如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步骤 5： 如果您想要设置调用计划

如果你一直在遵循以上步骤，您已购买并分配电话系统和许可证以及通话套餐 （第 2 步）并且为用户获取电话号码（第 3 步），因此您通话套餐i已部分设置。 若要完成设置呼叫计划的过程，请参阅[设置呼叫计划](set-up-calling-plans.md)。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步骤 6： 如果您想要设置音频会议

您的组织中的人员有时需要使用电话拨入会议。 Microsoft 团队仅为此情况提供音频会议功能。 用户可以使用电话呼叫团队会议，而不是在移动设备或电脑上使用 "团队" 应用。
有关如何设置音频会议的信息，请参阅[设置团队的音频会议](set-up-audio-conferencing-in-teams.md)。

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>步骤7：要设置云呼叫队列

云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能，以及搜索下一个可用的呼叫代理以处理呼叫，而通话的人员在保持状态时收听音乐。 您可以为您的组织创建单个或多个通话队列。

有关通话队列的详细信息，请参阅[创建云呼叫队列](create-a-phone-system-call-queue.md)。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>步骤8：如果要设置云自动助理

自动助理允许与你的组织进行通话的人员，并导航到相应的菜单系统以将其转到相应的部门、呼叫队列、人员或运营商。 您可以使用 Skype for Business 管理中心为您的组织创建自动助理。

有关设置云自动 attendendant 的信息，请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）

一旦您从 **上面的步骤 4** 获得服务号码后，您需要将其分配给所需每种类型服务。 例如，如果您需要专用服务电话号码（收费或免费），您需要将该号码分配给会议桥。

- 对于音频会议，您可以通过转到**团队管理中心** > **会议** > **桥**并按照提示将专用号码分配给会议桥。  有关详细信息，请参阅[在音频会议网桥上更改收费或免费号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 对于自动助理，你可以通过转到 "**团队管理中心** > "**语音** > **自动助理**，将专用号码分配给自动助理，然后按照提示进行操作。  有关详细信息，请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)。

- 对于呼叫队列，您可以通过转到 "**团队管理员中心** > **语音** > **呼叫" 队列**将专用号码分配给呼叫队列，然后按照提示进行操作。 有关详细信息，请参阅[创建云呼叫队列](create-a-phone-system-call-queue.md)。

有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步骤10：为你的组织设置通讯信用点数

如果您想要与 Microsoft 团队一起使用免费电话号码，您需要设置通讯信用点数。 Microsoft 建议为您的呼叫计划（国内或国际）和需要拨出到任何目的地的音频会议用户设置通讯信用点数。 包括许多国家/地区，但某些目的地可能不包括在您的通话计划或音频会议套餐中。 

如果您不设置通讯信用帐单并为您的用户分配**通讯信用**许可证，而您的组织的分钟数（取决于您所在国家/地区的通话计划或音频会议计划），这些用户将无法通过音频会议会议进行呼叫或拨出。 有关详细信息（包括推荐的融资金额），请参阅[什么是通讯信用点数？](what-are-communications-credits.md)并[为您的组织设置通讯信用点数](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>相关主题
[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 

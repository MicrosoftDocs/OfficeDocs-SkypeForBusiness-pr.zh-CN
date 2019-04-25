---
title: Microsoft Teams 中的呼叫策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 了解调用中的 Microsoft 团队的策略设置。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e56f0c89859b940a82e76f8de35ff524a757ec9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224997"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams 中的呼叫策略
==========================================

在 Microsoft 团队中，调用策略控制的呼叫和呼叫转接功能是对用户可用。 呼叫策略确定是否用户可以接听私人电话，使用呼叫转接或同时响铃到其他用户或外部电话号码，将呼叫路由到语音邮件，呼叫组发送呼叫使用的入站和出站呼叫委派，依此类推。 默认全局策略自动创建的但管理员还可以创建和分配调用的自定义策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义调用策略

按照以下步骤创建自定义调用策略。

1. 在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。
2. 选择**新策略**。
3. 打开要调用策略中使用的功能。 默认情况下，所有选项都包括**关闭**。
4. 若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。 若要阻止传送到语音邮件，请选择**总是禁用**。
5. 选择**保存**。

## <a name="modify-an-existing-calling-policy"></a>修改现有的调用策略

按照以下步骤修改现有的调用策略。

1. 在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。
2. 单击您想要修改，然后选择**编辑**策略旁边。
3. 打开要调用策略中使用的功能。 默认情况下，所有选项都包括**关闭**。
4. 若要控制用户是否可以将到语音邮件的入站的呼叫路由，请选择**始终启用**或**用户控制**。 若要阻止传送到语音邮件，请选择**总是禁用**。
5. 选择**保存**。

## <a name="assign-a-calling-policy-to-a-user"></a>调用策略分配给用户

按照以下步骤将自定义调用策略分配给用户。

1. 在 Microsoft 团队管理中心中，选择**语音** > **调用策略**。
2. 单击以选中它，然后选择**管理用户**的策略名称旁边。
3. 在**管理用户**窗格中，搜索用户的名称。 （您必须输入至少三个字符）。
4. 选择用户的名称，然后选择**添加**。
5. 选择**保存**。

## <a name="calling-policy-settings"></a>调用策略设置

使用以下设置创建自定义调用策略。

### <a name="user-can-make-private-calls"></a>用户可以接听私人电话

此设置控制团队中的所有呼叫功能。 禁用此选项，将会关闭团队中的所有呼叫功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>呼叫转接和同时响铃向其他用户

此设置控制传入呼叫可以转移到其他用户还是可以同时拨打其他人。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接和同时响铃到外部电话号码

此设置控制传入呼叫可以转移到外部号码还是可以同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>语音邮件是可用于向用户的入站呼叫路由

此设置，入站的呼叫就可以发送到语音邮件。 有效的选项为：

   - **始终启用**语音邮件始终是适用于入站调用的。 
   - **始终禁用** 不可用入站呼叫的语音邮件。 
   - **用户控制**。 用户可以确定是否需要能够使用的语音邮件。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>入站的呼叫可以路由到呼叫组 

此设置控制是否可以将传入呼叫转接到的呼叫组。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允许入站和出站呼叫的委派

此设置使入站的呼叫路由到允许代理人发起代表他们具有其委派权限的用户的出站呼叫的代理人。 有关详细信息，请参阅[共享与代理人的电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>阻止收费绕过和发送通过 PSTN 呼叫 

将其设置为**上**将发送通过 PSTN 呼叫，并会导致费用而不是将其发送网络通过和绕过费。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>忙闲上的有时呼叫

忙碌 （忙选项） 的忙碌） 是，您可以配置如何传入呼叫的呼叫策略处理用户已在呼叫或会议，或具有呼叫时，团队中的新设置置于保持状态。 新的或传入呼叫可以被拒绝，并繁忙信号。 您可以启用忙选项在租户级别或用户级别。 无论其忙选项的配置方式，呼叫或会议或呼叫置于保持状态的那些将不阻止用户发起新呼叫或会议。 默认情况下禁用此设置。


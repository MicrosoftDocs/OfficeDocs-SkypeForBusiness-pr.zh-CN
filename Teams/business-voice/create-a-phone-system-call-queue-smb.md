---
title: 在小型企业教程中Microsoft Teams呼叫队列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: 了解如何在 Microsoft 365 商务语音 中为小型企业设置呼叫Microsoft 365 商务语音。
ms.openlocfilehash: 7267d2d7116f40d29405510a924b5ec560037d0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605981"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>创建呼叫队列 - 小型企业教程

呼叫队列提供了将呼叫者路由到组织中可以解决特定问题或问题的人的方法。 呼叫一次一个地分配给队列中 (称为代理 *) 。* 

呼叫队列提供：

- 问候消息。

- 音乐排入队列等待时，将打开队列。

- 调用路由 - 在 *"先* 到先出" (FIFO) 顺序 - 到代理。

- 处理队列溢出和超时的选项。

#### <a name="video-demonstration"></a>视频演示

此视频演示如何在 Teams 中创建呼叫队列。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a>开始之前

获取电话系统[-](../teams-add-on-licensing/virtual-user.md)虚拟用户许可证（如果还没有）。 为计划设置的每个呼叫队列和自动助理获取一个。 这些许可证是免费的，因此如果你决定在将来对设置进行更改，我们建议额外获取一些许可证。

由于呼叫队列中的代理可能会拨出以返回客户呼叫，因此请考虑将呼叫代理的呼叫者 ID 设置为主电话号码或相应的自动助理号码。 有关详细信息[，请参阅管理](../caller-id-policies.md)Microsoft Teams 中的来电显示策略。

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>按照以下步骤设置呼叫队列

# <a name="step-1brcreate-a-team"></a>[步骤 1 <br> 创建团队](#tab/create-team)

创建呼叫队列时，可以将单个用户添加到队列，或者可以使用现有的安全组、Microsoft 365组或Microsoft Teams团队。 建议使用 [团队频道](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。 这样，队列的成员可以彼此聊天、分享想法以及创建文档或其他资源，以帮助他们帮助客户。 团队还提供语音邮箱，让呼叫者在数小时后或队列达到最大容量时留下消息。

创建团队

1. 首先 **，Teams** 左侧单击"团队"，然后单击团队列表底部的"加入或创建团队"。

2. 然后单击" **创建团队** (第一张卡片（左上角）) 。

3. 选择 **"从头开始构建团队"。**

4. 接下来，选择是需要公共团队还是专用团队。 建议 **为** 呼叫队列使用"专用"，以避免用户通过加入团队无意中成为队列的一部分。

5. 命名团队并添加可选说明。

6. 完成后，单击"创建 **"。**

8. 键入您希望在呼叫队列中拥有的人的姓名，然后单击"添加 **"。**

9. 单击“关闭”。 添加到团队的人将收到一封电子邮件，让他们知道他们现在是团队的成员，并且团队会显示在团队列表中。

接下来，我们将添加用于呼叫队列的通道。

添加频道

1. 在Teams中，找到刚创建的团队，单击"更多选项" (...) ，然后单击"添加 **频道"。** 

2. 键入频道的名称和说明。

3. 在 **"隐私**"**下，选择"标准 - 可供团队中所有人访问"，** 然后单击"添加 **"。**

> [!div class="nextstepaction"]
> [步骤 2 - 资源帐户>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[步骤 2 <br> 资源帐户](#tab/resource-account)

创建的每个呼叫队列都需要一个资源帐户。 这类似于用户帐户，但该帐户与自动助理或呼叫队列（而不是人员）相关联。 在此步骤中，我们将创建帐户，为其分配Microsoft 365 电话系统 - 虚拟 *用户* 许可证，然后使用它开始创建呼叫队列。

### <a name="create-a-resource-account"></a>创建资源帐户

可以在管理中心内创建Teams帐户。

1. 在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**

2. 单击“**添加**”。

3. 在"**添加资源帐户"** 窗格中，填写"**显示名称**、**用户名"，** 然后选择"呼叫队列 **"作为"** 资源帐户 **类型"。** 当代理收到显示名称传入呼叫时，代理将看到该请求。

    ![添加资源帐户用户界面的屏幕截图](../media/resource-account-add-cq.png)

4. 单击“**保存**”。

   新帐户将显示在帐户列表中。

   ![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>分配许可证

必须为资源帐户 *Microsoft 365 电话系统 - 虚拟* 用户许可证。

1. 在Microsoft 365 管理中心"**活动用户"** 列表中，单击要为其分配许可证的资源帐户。

2. 在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**

3. 单击 **保存更改**。

    !["许可证分配"用户界面的屏幕截图Microsoft 365 管理中心](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>创建呼叫队列

接下来，我们将开始创建新的呼叫队列并分配资源帐户。

1. 在Teams中心，展开"**语音**"，单击"**呼叫队列**"，然后单击"添加 **"。**

1. 键入呼叫队列的名称。

2. 单击 **"添加** 帐户"，搜索要用于此呼叫队列的资源帐户，单击"添加 **"，然后单击**"添加 **"。**

3.  (可选) "分配呼叫 **ID"** 下，单击"添加"，搜索为自动助理创建的资源帐户，单击"添加 **"，然后单击**"添加 **"。** 这将在呼叫代理进行呼叫时为呼叫代理提供主线呼叫者 ID。

    ![调用 ID 设置的屏幕截图](../media/call-queue-assign-calling-id.png)

3. 选择一种语言。 如果启用语音提示和语音邮件听录，此语言 (系统生成的语音提示) 。

    ![资源帐户设置的屏幕截图](../media/call-queue-name-language.png)

4. 指定是否要在呼叫者到达队列时播放问候语。 必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。

5. Teams在队列中保持时向呼叫者提供默认音乐。 如果要播放特定音频文件，请选择"播放音频文件 **"并** 上传 MP3、WAV 或 WMA 文件。

   > [!NOTE]
   > 上传的录制内容不能大于 5 MB。
   > 呼叫队列中提供的默认Teams不收取组织支付的任何版权费。 

> [!div class="nextstepaction"]
> [步骤 3 - 呼叫>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[步骤 3 <br> 呼叫代理](#tab/call-agents)

若要将代理添加到呼叫队列，我们会将它们添加到我们之前创建的团队和频道。 你需要是团队的成员来这样做。

1. 选择"**选择团队"选项，** 然后单击 **"添加频道"。**
2. 键入创建的团队的名称，将其选中，然后单击"添加 **"。**
3. 选择为队列创建的通道。
3. 单击“**应用**”。

    ![呼叫队列的用户和组设置的屏幕截图](../media/call-queue-users-groups.png)

> [!NOTE]
> 将新用户添加到团队后，最多可能需要八个小时才能第一次呼叫到达。

> [!div class="nextstepaction"]
> [步骤 4 - 资源帐户>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[步骤 4 <br> 呼叫路由](#tab/call-routing)

选择想要使用的呼叫路由方法。

1. 将 **"会议模式"设置为**"**自动"。**

2. 选择 **想要使用的** 路由方法。 这会确定代理从队列接收调用的顺序。 我们建议使用 **串行路由或****轮循机制**。 从以下选项中进行选择：

    - **助理路由** 同时将队列中的所有代理环环。 第一个接电话的呼叫代理获取呼叫。

    - **串行路由** 将一个接一个地拨打所有呼叫代理。 如果代理关闭或未接回呼叫，该调用将拨打下一个代理，并尝试所有代理，直到它被选取或退出。

    - **轮循** 机制平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。 在入站销售环境中可能需要这样做，以确保所有呼叫代理之间的机会相等。

    - **最长空闲** 时间将每次调用路由到空闲时间最长的代理。  (状态为"离开"超过 10 分钟的代理不包括。) 

    ![会议模式和路由方法设置的屏幕截图](../media/call-queue-conference-mode-routing-method.png)

3. 打开 **基于状态路由** 。 这会将调用路由到状态为"可用"的 **代理**。

4. 选择是否允许代理选择退出呼叫。

5. 设置 **代理警报** 时间，指定在队列将呼叫重定向到下一个代理之前，代理的电话响铃的时间。

    ![路由、选择退出和警报时间设置的屏幕截图](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [步骤 5 - 调用溢出>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[步骤 5 <br> 调用溢出](#tab/call-overflow)

选择要如何处理队列中超过最大值的调用。

1. 在 **队列中设置最大调用数**。

2. 选择达到最大呼叫数时要执行哪些工作。 你可以断开呼叫或重定向它。 建议将调用重定向到以下目标之一：
    - **组织中的人** - 组织中能够接收语音呼叫的人
    - **语音应用** - 自动助理或其他呼叫队列。  (选择此目标时选择与自动助理或呼叫队列关联的资源帐户) 
    - **外部电话号码** - 任何电话号码。 使用此格式：+[国家/地区代码][区号][电话号码]
    - **语音邮件** - 您可以使用创建的团队的语音邮箱。

    ![呼叫溢出设置的屏幕截图](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [步骤 6 - 调用超时>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[步骤 6 <br> 调用超时](#tab/call-timeout)

选择当通话在队列中等待太长时间时要发生的情况。

1. 设置"**最长等待时间"。**

2. 选择通话打时要执行哪些工作。你可以断开呼叫或重定向它。 建议将调用重定向到以下目标之一：
    - **组织中的人** - 组织中能够接收语音呼叫的人
    - **语音应用** - 自动助理或其他呼叫队列。  (选择此目标时选择与自动助理或呼叫队列关联的资源帐户) 
    - **外部电话号码** - 任何电话号码。 使用此格式：+[国家/地区代码][区号][电话号码]
    - **语音邮件** - 您可以使用创建的团队的语音邮箱。

    ![通话超时设置的屏幕截图](../media/call-queue-timeout-handling.png)

3. 单击“**保存**”。

这将完成呼叫队列的设置。 接下来，你可能希望 [设置自动助理](create-a-phone-system-auto-attendant-smb.md)。

---


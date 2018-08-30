---
title: 在您组织中设置电话系统
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为组织设置电话系统 （云 PBX）。 '
ms.openlocfilehash: 2566bfcef892767f89afb28643deb91942596e76
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244627"
---
# <a name="setting-up-phone-system-in-your-organization"></a>在您组织中设置电话系统

以下是 Office 365 中的电话系统的分步设置 指南。 在每个步骤的末尾都提供指向其他详细信息的链接。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步骤 1： 请确保您的国家或地区可用使用电话系统

1.  首先转到 [国家和地区的音频会议和呼叫计划的可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。
2.  在 **电话系统** ，下查看的功能和详细信息的列表。
3.  如果可用电话系统，转到步骤 2。

**若要了解有关电话系统和音频会议的区域可用性的详细信息，请参阅 [国家和地区音频会议和调用计划的可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) 。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步骤 2： 购买和分配电话系统和通话套餐许可证

若要将电话系统和通话套餐许可证分配给单个用户的步骤与分配 Office 365 许可证相同。 请参阅 [分配 Skype for Business 和 Microsoft Teams 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  。 如果您想要分配批量的多个用户，请参阅 [分配 Skype for Business 和 Microsoft Teams 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤 3： 为用户获取电话号码

在您可以设置组织中的用户来拨打和接收电话之前，您必须为他们获取电话号码。

有三种方法可为用户获取号码：
- 从 Skype for Business 管理中心获得新号码。
- 获取在Skype for Business管理中心不可用的新号码。
- 将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。

必须使用" **新号码** 页面查看、搜索、获取和预留这些号码。 您可以按国家/地区、州和城市进行搜索，然后输入用户需要的电话号码数。

### <a name="get-new-user-phone-numbers"></a>获取新的电话号码

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**


1. 使用你的工作或学校帐户登录 Office 365。

2. 转到 **Office 365 管理中心** > **Skype for Business** 。

3. 在左侧导航窗格中转到 **语音** > **电话号码**，单击 **添加新号码** ![添加按钮](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)，然后单击**新的用户数量**。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在Skype for Business管理中心不可用的新号码

有时 （根据您的国家/地区）您将无法使用Skype for Business管理中心 获取新号码。 在这种情况下，您需要下载表单并将其发送回给我们。 请参阅 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) ，以了解如何请求新的用户号码。

### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移

- 如果您的用户需要999或更少的电话号码，您可以使用 Skype for Business 管理中心的 **新建本地号码迁移订单** 向导。 按照在 [将电话号码转移至  Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) 中的步骤将您的号码转移到 Skype for Business Online。

- 如果您需要迁移超过999个电话号码，请参阅 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 提交的转网订单服务请求或获取所有这些电话号码移植到 Office 365的订单。

**有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md) 。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）

除了从 Office 365 用户获取电话号码，您还可以搜索和获取服务的电话费或免费电话号码，例如音频会议 （会议网桥）、 自动助理等呼叫队列 （也称为服务号码）。 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 例如，一个服务号码可同时处理 100 个呼叫，而用户电话号码只能同时处理几个呼叫。

### <a name="get-new-service-numbers"></a>获取新服务号码

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**


1. 使用你的工作或学校帐户登录 Office 365。

2. 转到 **Office 365 管理中心** > **Skype for Business** 。

3. 在左侧导航窗格中转到**语音** > **电话号码** > **添加新号码**，然后单击 **新服务号码**。

    > [!IMPORTANT]
    > 重要提示 ：若要在 Skype for Business 管理中心的左侧导航中显示 **语音**选项，必须先购买至少一个 **Enterprise E5 许可证**、一个 **电话系统**附加设备许可证，或一个 **音频会议**附加设备许可证。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在Skype for Business管理中心不可用的新号码

有时 （根据您的国家/地区）您将无法使用Skype for Business管理中心 获取新号码。 在这种情况下，您需要下载表单并将其发送回给我们。 请参阅 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) ，以了解如何请求新的用户号码。

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。 必须为每种服务号码（收费与免费）分别提交不同的转网订单，并使用授权书（LOA）转移这些号码。 在授权书（LOA）中，必须选择正确的服务号码类型。 联系 Microsoft 支持部门时，请务必指明你要转移的是服务号码（*不是用户或订阅者号码*  ），否则并发呼叫容量可能不足以处理呼叫容量。 如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步骤 5： 如果您想要设置调用计划

如果你一直在遵循以上步骤，您已购买并分配电话系统和许可证以及通话套餐 （第 2 步）并且为用户获取电话号码（第 3 步），因此您通话套餐i已部分设置。 按照下面的三过程完成通话套餐 的设置。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>为你的组织添加紧急地址和位置

1. 在**语音**页面上，选择 **紧急位置** > **添加新地址**。

2. 在 **新地址** 窗格中，输入你的地址名称，然后填写剩余框。

     ![当您输入新的紧急地址时，街道名称的格式可能会导致错误。](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)

    > [!TIP]
    > [!提示] 对于英语客户，如果街道名称是数字，请务必在结尾加上"st"或"th"，如上图所示。

3. 选择" **验证**"。

    如果需要，系统将提示你对地址进行更改。

    > [!CAUTION]
    > 验证街道或公民地址涉及确保其合法且格式正确。 可能有一个部分正确的紧急地址，如您键入的城市名称错误，仍可能通过验证。 即使拼写错误并通过验证，拼错的城市名称和地址的其他正确部分相结合也足以将呼叫路由到合适的紧急派遣中心。

    > [!TIP]
    > [!提示] 如果地址需要更正才能处理紧急响应，系统将显示一个绿色横幅，通知你地址已更新。

4. 验证地址之后，请选择 **保存** 。

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>为用户分配电话号码和紧急地址

> [!TIP]
> [!提示] 如果在执行此步骤前刚刚向企业添加了更多人员，这些人员可能需要 **几小时** 才会显示在" **语音用户**"页面。 系统存在延迟。

1. 在 **语音用户** 页面，选择要为其分配电话号码和紧急地址的人员。

2. 在操作窗格中，单击 **分配号码** 。

3. 在  **分配号码** 页面上的 **选择要分配的号码** 列表中，为该用户选择电话号码。

4. 要选择紧急地址，请在框中输入城市名称然后选择 **搜索** 。

    > [!IMPORTANT]
    > 如果你在美国以外，你的号码已经有一个紧急地址，但是你现在可以更改此地址。 请参阅[为用户分配或更改紧急地址](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md)。

5. 在分配电话号码和紧急地址之后，选择  **保存** 。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>告诉用户他们的新电话号码


我们建议通过发送邮件或使用企业的首选通信方式，将新电话号码告知用户。

以下是他们如何在 **Skype for Business** 应用程序中看到该电话号码：

1. 登录桌面上的 Skype for Business。

2. 选择 **设置** > **工具选项** > **选项**。

     ![要查看您的电话号码，请转到设置 > 工具 > 选项。](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)

3. 然后，选择" **电话**"。

    ![用户可以通过选择设置 > 工具 > 选项 > 电话在 Skype for Business 应用程序看到他们的分配号码。](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)

在**Microsoft Teams** 中，用户通过单击左侧导航窗格中的**呼叫**，可以看到他们的电话号码。 电话号码显示在拨号板上方。

![通过单击左侧导航窗格中的呼叫，用户可以在 Microsoft Teams 中看到其号码。](../images/teams-phone-number.png)

**有关设置通话套餐所涉及的所有步骤的更详细信息，请参阅 [设置通话套餐](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) 。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步骤 6： 如果您想要设置音频会议

有时，组织中的用户需要使用电话拨入会议。 Skype for Business 和 Microsoft Teams 包括适用于这种情况的音频会议功能！ 人们可以通过电话致电 Skype for Business 和 Microsoft Team 会议，而无需使用移动设备或电脑上的 Skype for Business 或 Microsoft Team 应用程序。

您只需为计划要安排或主持会议的人员设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。

有关音频会议的常见问题，请参阅 [音频会议的常见问题](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md) 。

1. 如果购买了 **音频会议** 外接程序许可证和通信点数许可证，也要分配它们。 有关说明，请参阅 [分配 Skype for Business 和 Microsoft Teams 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 。

    决定您的音频会议提供商。 音频会议提供商提供音频会议桥。 会议网桥会设置会议的拨入电话号码、PIN 和会议 ID。 决定是否使用 Microsoft 或第三方音频会议提供商：

    > [!NOTE]
    > Microsoft Teams 用户不能用户第三方音频会议提供商。

    - **Microsoft 作为您的音频会议提供商**： 如果您希望音频会议的最简单的解决方案，选择 Microsoft 作为您的音频会议提供商。

    - **第三方音频会议提供商作为**： 如果您所在的国家的音频会议在 Office 365 中不可用，由于其位置服务质量不好，或您有一个现有的合同，请选择第三方音频会议提供商。 要查找提供商，请转到 [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) 。

2.  将音频会议提供商分配给领导或安排会议的人员。 请参阅 [将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md) 。

3. 设置会议邀请。 以下步骤是可选的，但很多管理员喜欢执行这些操作：

    1. [自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md) 。 为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。 但是，你也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。

    2. [为包含在邀请中的会议组织者设置音频会议电话号码](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) 。 此电话号码将显示在由用户安排的会议中。

    3. [设置音频会议自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) ，音频会议自动助理将用这种语言在致电者拨入音频会议电话号码时向其发出问候。 此步骤仅在使用 Microsoft 作为音频会议提供商时适用。

    4. [设置音频会议的 PIN 的长度](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md) 。

    > [!NOTE]
    > 由中国世纪互联运营的 Office 365 用户暂无法使用此功能。 如需了解更多信息，请参阅 [了解由世纪互联运营的 Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE) 。

**有关音频会议的详细信息，请参阅 [设置音频会议](../audio-conferencing-in-office-365/set-up-audio-conferencing.md) 。**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>步骤 7：如果您想要设置电话系统呼叫队列

电话系统调用队列包括当有人呼叫您的组织的电话号码时使用的问候语、自动将呼叫挂起的能力以及搜索下一个可用呼叫代理以处理呼叫的能力，而那些电话正在收听音乐。 您可以为您的组织创建单个或多个呼叫队列。

在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。 获得收费电话或免费电话服务电话号码后，他们会显示在 **Skype for Business 管理中心** > **语音** > **电话号码**，**号码类型**将列出**服务—免费电话**。 若要获取服务号码，请参阅 [从 Skype for Business 和 Microsoft Teams 获取服务电话号码](getting-service-phone-numbers.md) 或如果您希望进行转移现有服务号码，请参阅  [传输电话号码到 Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) 。

> [!NOTE]
> 如果你是在美国以外，你不能使用 Skype for Business 管理中心获得服务号码。 如需了解如何在美国以外的国家/地区获取服务号码，请访问 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。

若要创建新的呼叫队列，在**Skype for Business 管理中心** 中， 单击 **呼叫路由** > **呼叫队列**，请单击 **添加新**，然后按照在 **步骤 3**中  [创建电话系统呼叫队列]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue) 的说明。

**有关呼叫队列的详细信息，请参阅 [创建电话系统呼叫队列](create-a-phone-system-call-queue.md) 。**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>步骤 8： 如果您想要设置电话系统自动助理

自动助理允许调用您的组织的人员并导航菜单系统，以便将它们带到正确的部门、呼叫队列、人员或操作员。 您可以使用Skype for Business管理中心为您的组织创建自动助理。

若要创建新的自动助理，在 Skype for Business管理中心，单击 **呼叫路由** > **自动助理**，单击 **添加新**，然后按照**步骤 2** 中每页的说明 [设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant)。

**有关电话系统自动助理的详细信息，请参阅 [设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md) 。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）

一旦您从 **上面的步骤 4** 获得服务号码后，您需要将其分配给所需每种类型服务。 例如，如果您希望专用的服务电话号码（收费电话或免费），您将需要分配会议桥的数量。

- 音频会议，您可以通过 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议**分配专用号码会议桥并单击会议桥或查看[更改音频会议桥上的收费或免费电话](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 自动助理，您可以通过 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **呼叫路由** > **自动助理**分配专用的号码到自动助理并单击自动助理。 在 **常规** 页上您已经拥有的服务号码将在 **电话号码** 中下拉列表中列出。 有关详细信息，请参阅 [设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md) 。

- 对于呼叫的队列，您可以通过 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **呼叫路由** > **呼叫队列** 分配专用的号码呼叫队列并单击呼叫队列。 在  **常规** 页上您已经拥有的服务号码将在 **电话号码** 中下拉列表中列出。 有关详细信息，请参阅 [创建电话系统呼叫队列](create-a-phone-system-call-queue.md) 。

**有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步骤 10：为您的组织设置通信点数

您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。 此外，我们建议您为通话套餐 （国内或国际）和需要拨号到 **任何目的地** 的音频会议用户设置通信点数。 您的通话套餐或音频会议套餐涵盖很多国家/地区，但有些目的地可能未涵盖。 如果您不会设置通信点数帐单且将 **通信点数** 许可证分配给用户，并且您用完您的组织的可用分钟（具体取决于您在您的国家/地区的通话套餐或音频会议套餐），这些用户将无法发起呼叫或从音频会议拨出。 你可以阅读[通信点数是什么？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) 了解更多信息，包括建议的金额。

> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。

### <a name="to-set-up-communications-credits"></a>设置通信点数

1. 使用你的工作或学校帐户登录 Office 365。

2. 在 Office 365 管理中心的左侧导航窗格中，转到 **帐单** > **订阅** > **加载项** > **购买加载项**，然后选择 **通信点数** > **立即购买**。

3. 在**通信点数**订阅页中，填写您的信息，然后单击**下一步**。

4. 输入您的付款信息并单击 **下订单** 。
    >[!IMPORTANT]
    >如果您是批量授权客户，则可以选择您的企业协议编号进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。

**有关通信点数设置的详细信息，请参阅 [为您的组织设置通信点数](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) 。**

### <a name="assign-a-communications-credits-license-to-users"></a>将通信点数许可证分配给用户

1. 使用你的工作或学校帐户登录 Office 365。

2. 在 Office 365 管理中心的左侧导航中，转到 **用户** > **活动用户** ，然后从列表中选择一个用户或多个用户。

3. 在操作窗格中，在**PIN**下单击 **重置**。

4. 在**产品许可证**页上，将**通信点数**切换到**On**以分配此许可证，然后单击**保存**。

    > [!NOTE]
    > 即使您的用户被分配了**Enterprise E5**许可证，建议你仍执行此操作。

**若要了解有关分配通信点数许可证的详细信息，请参阅 [为您的组织设置通信点数](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) 。**

## <a name="related-topics"></a>相关主题
[Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)



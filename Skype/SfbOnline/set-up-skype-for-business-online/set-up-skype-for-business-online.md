---
title: 设置 Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: '了解如何为你的组织设置域、用户、即时消息和状态以安装 Skype for Business。另请参阅如何设置音频会议、电话系统和通话套餐以及 Skype 会议直播。 '
ms.openlocfilehash: d712fd0bf02e770c15f1c6dcf61789dcf0fd27e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613251"
---
# <a name="set-up-skype-for-business-online"></a>设置 Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

必须具有全局管理员权限才能设置Skype for Business。 如果你有限制访问部分 Web 的防火墙或代理服务器，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你设置 Skype for Business。

## <a name="setting-up-skype"></a>设置 Skype

在订阅或订阅中设置Skype时Microsoft 365 Office 365帮助。 你可以按照本文中的步骤完成设置。

## <a name="1-plan-for-skype-for-business"></a>1. 规划 Skype for Business

如果你有标准 **[Microsoft 365 商业高级版](https://products.office.com/business/office-365-business-premium)****或商业** 基础版，可以使用 Skype for Business 向你的订阅中的企业中的其他人进行在线呼叫。 例如，如果企业有 10 个人，则在执行下面的步骤 2-6 之后，即可相互[开始使用 Skype for Business 进行即时消息通信和联机会议](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)，并[使用 Skype for Business 召开会议](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)。 而且你还可以[在 Outlook 中设置 Skype for Business 会议](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)以召开联机会议！

如果你想使用 Skype for Business 与组织 **外部** 的用户进行 *通话*  ，则有下列选项：

- **选项 1。使用免费的 [Skype 应用](https://www.skype.com/)** 。 如果企业的规模很小（例如，1-2 人），则使用 Skype 应用比较好。 进行国内和国际呼叫时更便宜。 你仍可以召开电话会议、进行视频通话以及共享桌面以进行演示。 [检查费率和付款选项](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。

- **选项 2. 升级你的计划，并购买 Office 365 的电话系统和通话套餐**。 了解费用然后进行切换最简单的方式是[联系商业版产品的支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)，让他们为你执行所有操作。

若要了解更多信息，请参阅[规划 Office 365 商业版的设置](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。

## <a name="2-sign-in-to-office-365"></a>2. 登录 Office 365
<a name="bkmk_signin"> </a>

Skype for Business Online 是 Office 365 服务套件的一部分。要设置 Skype for Business Online，你需要登录到 Office 365。下面介绍了如何操作：

1. 找到Microsoft 365或Office 365用户 ID (例如<em>，rob@fourthcoffee.com) 。</em> 你收到了来自 Microsoft Online Services 团队的电子邮件，其中包含Microsoft 365或Office 365购买 Skype for Business Online 时创建的用户 ID。 邮件内容如下所示：

    ![在你注册 Skype for Business Online 之后收到的欢迎电子邮件的示例。 它包含你的Microsoft 365或Office 365 ID。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 登录到管理[中心，](https://admin.microsoft.com)输入Microsoft 365或Office 365 ID 和密码。 

## <a name="3-set-up-your-domain-and-users"></a>3. 设置域和用户
<a name="bkmk_users"> </a>

在登录到 Office 365 之后，你可以将你的域和你的组织中的用户设置为使用 Skype for Business Online。

1. [为 Office 365 添加域和用户](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)：使用 Office 365 设置向导为 Office 365 设置自定义域（例如 *fourthcoffee.com*）。 **By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.** If you already used the wizard to set up your domain for Office 365, then you've completed this step.

2. [检查你的域和 DNS 连接](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)：使用我们的工具（域疑难解答）检查你的域和 DNS 设置是否正确。执行此操作将发挥较大作用，可帮助解决任何安装问题，因为你可以避免 DNS 设置将来引起问题。

3. [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)：大多数小型企业不需要执行此步骤。 **但是，如果你有限制访问部分 Web 的防火墙或代理服务器** ，你必须创建规则来允许访问 Skype for Business Online 终结点。 这是最好由有配置防火墙和代理服务器经验的人执行的高级步骤。 如果你之前未执行此操作，请考虑雇用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你设置 Skype for Business。

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 在组织中设置即时消息和状态
<a name="bkmk_IM"> </a>

即时消息 (IM) 和状态（[在 Skype for Business 中控制对你状态信息的访问](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)）是 Skype for Business 附带的基本功能。默认情况下，你的企业中的人员可以相互进行 Skype 和即时消息通信。

1. **选择你的 Skype for Business 用户可以进行通信的人员：**

   - [允许用户联系外部 Skype for Business 用户](allow-users-to-contact-external-skype-for-business-users.md) 你 *和*  其他企业将需要配置你的系统。

     **重要** ：如果你的企业有两个域，例如 rob@contosowest.com 和 ina@contosoeast.com，你需要执行此操作，让你的所有用户之间都可以通信。

   - [允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

2. **选择哪些人是否可以看到同事是否在线：** 状态功能显示谁处于在线状态及其可用性，例如有空、忙碌、离开或正在演示。

    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    你可以为你的企业中的每个人选择默认设置：

   - 自动向组织中的所有人显示某个用户的联机状态

   - 仅向某个用户的联系人显示其联机状态

有关说明，请参阅[在 Skype for Business Online 中配置状态](configure-presence-in-skype-for-business-online.md)。

## <a name="5-download-and-install-skype-for-business"></a>5. 下载并安装 Skype for Business
<a name="bkmk_download"> </a>

要在你的电脑、Mac 或移动设备上使用 Skype for Business，你和你的企业中的其他人必须首先在你的设备上安装 Skype for Business。

- [安装Skype for Business：](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)有关如何从应用商店下载应用Microsoft 365 管理中心，以及如何在电脑或 Mac 上安装该应用的说明。

- [在 Office 365 中部署 Skype for Business 客户端](deploy-the-skype-for-business-client-in-office-365.md)：在大型企业中部署应用的说明。

- [安装 Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)：在 Android 设备、iOS 设备和 Windows 手机上下载、安装和登录 Skype for Business。

- [打开或关闭移动电话通知](turn-on-or-off-mobile-phone-notifications.md)：当在移动设备上安装了 Skype for Business 时，你和你的企业中的其他人可以接收有关传入消息和错过的即时消息的通知。

## <a name="6-test-to-make-sure-everything-is-working"></a>6. 执行测试以确保一切正常运行
<a name="bkmk_test"> </a>

首先，测试你和你的企业中的其他人是否可以[登录和注销 Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。检查你们是否相互收发即时消息、查看彼此的状态，并尝试召开快速会议。

有问题？请执行下列操作：

- [需要帮助登录到 Skype for Business 吗？](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)。

- [联系 Office 365 商业版支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。我们随时为你提供帮助！

## <a name="do-you-want-to-set-up-other-available-features"></a>是否想要设置其他可用功能？
<a name="bkmk_more"> </a>

设置更多功能之前，请确保你拥有它们的许可证。 [Skype for Business 和 Microsoft Teams 加载项许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>设置音频会议

有时组织中的人员会需要使用电话呼入会议。Skype for Business 包含了正是针对此种情况的音频会议功能。人们可以使用电话呼入 Skype for Business 会议，而无需使用移动设备或电脑上的 Skype for Business 应用。

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>在 Office 365 中设置电话系统和通话套餐

Office 365 中的电话系统功能提供了适用于你的业务的电话系统。呼叫组织中的其他 Skype for Business 人员是免费的，而且你的员工可以互相并从外部呼叫方接收语音邮件。以下是使用电话系统可获得的功能。

添加呼叫计划服务时，员工会在 Skype for Business 中获得主电话号码。他们可以拨打和接听公司外部的电话。他们可以通过 VolP 电话、电脑和移动设备进行语音呼叫，并且在紧急情况下，他们还可以呼叫 911 求助。

有关分步设置说明，请参阅设置呼叫计划。

### <a name="set-up-skype-meeting-broadcast"></a>设置 Skype 会议直播

Skype 会议广播 是一项功能，允许你针对最多 10,000 个与会者制作、主持和直播会议。 **要了解其工作方式的详细信息，请参阅 [什么是 Skype 会议直播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

以下是设置 Skype 会议广播 的步骤概述：

1. [如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)：为将 **主持** 直播会议的每个人分配 **Skype for Business Online** 或 **企业版计划** 许可证。

2. [启用 Skype 会议直播](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)：此功能默认不会启用。 将其打开后，你的用户将能够与组织中的其他人一起主持直播会议。

3. [设置 Skype 会议直播网络](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)：如果你希望与组织外部的与会者一起主持网络研讨会和其他直播，你需要配置网络。

4. [计划 Skype 会议直播](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)并让用户 [加入 Skype 会议直播](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)：通过在 *https://portal.broadcast.skype.com* 上安排 Skype 会议直播，然后让用户尝试加入会议，确保直播会议正常进行。

## <a name="learn-about-network-connectivity-requirements"></a>了解网络连接要求
<a name="bkmk_more"> </a>

Skype for Business 中音频、视频和应用程序共享的质量很大程度上受端到端网络连接质量的影响。为获得最佳体验，必须确保公司网络和 Skype for Business Online 间有高质量网络连接。有关网络和优化的信息，请参见 [优化 Skype for Business Online 性能](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>全部设置已完成？开始使用 Skype for Business
<a name="bkmk_more"> </a>

[Skype for Business 培训](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba)：查看此培训主题列表，以帮助你快速入门！

[开始 Skype for Business 电话会议](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[在 Skype for Business 中设置视频设备选项](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[使用 Skype for Business 拨打和接听视频呼叫](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相关主题
<a name="bkmk_more"> </a>

[计划 Skype for Business Server 与 Skype for Business Online 之间的混合连接](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

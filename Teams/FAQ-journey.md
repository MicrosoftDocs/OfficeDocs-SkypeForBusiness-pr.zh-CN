---
title: 从 Skype for Business 升级到 Teams 的常见问题解答
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 有关从 Skype for Business 到 Microsoft Teams 的升级旅程的常见问题。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc99ac35344ff0628ec16c474d849320cf931afe
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "46596997"
---
# <a name="faq--upgrading-from-skype-for-business-to-microsoft-teams"></a>常见问题解答 - 从 Skype for Business 升级到 Microsoft Teams


## <a name="general-questions"></a>一般问题

**客户从 Skype for Business Online 迁移至 Teams 是否有严格的最后期限？**<br>
是。 [Skype for Business Online 将于 2021 年 7 月 31 日停用](skype-for-business-online-retirement.md)，在此日期之后它将不再可用或受支持。 我们鼓励 Skype for Business Online 客户立即开始使用 Teams 并开始计划他们的升级，以便有充足的时间在停用日期之前完成升级。


**我的组织升级到 Teams 需要多长时间？**<br>
贵组织从 Skype for Business 到 Teams 的旅程可由你制定。 为了帮助你规划和执行升级，我们基于经验证的框架制定了全面的升级指南，旨在帮助你了解变更的技术和组织要素。 通过熟悉我们的[升级成功框架](upgrade-framework.md)和相关资源开启你的旅程，这些资源是开启从 Skype for Business 到 Teams 迁移之旅的基石。


**Skype for Business 是否有推荐的升级路径？**<br>
我们鼓励你计划从 Skype for Business 到 Teams 的迁移之旅，利用 [aka.ms/SkypetoTeams](upgrade-start-here.md) 上提供的指南和资源并参加免费的[升级规划研讨会](upgrade-workshops-landing-page.yml)，以确定并实施最符合组织需求的升级路径。

**我可以从哪里了解 Microsoft Teams 管理中心内的共存模式的详细信息？**<br>
在 Microsoft Teams 管理中心，你将看到共存模式选项，这些选项使贵组织能够管理其所需的 Skype for Business 到 Teams 的迁移之旅。 了解有关[共存和升级模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)的详细信息。

**我应该为升级做哪些准备？**<br>
要成功升级，要验证技术就绪情况以及用户接受就绪情况。 即使你确定贵组织尚未准备好升级到 Teams，你现在仍可以开始规划过程。 此外，你可以同时启用 Teams 和 Skype for Business 以开始利用 Teams 的价值。 现在就开始进行 [Skype 到 Teams 的旅程](https://aka.ms/skypetoteams-home))。

Microsoft 还提供实时互动研讨会，我们将分享指导、最佳实践和资源，以帮助你开始升级规划和实施。 [了解升级规划研讨会](https://aka.ms/SkypeToTeamsPlanning)。


**我的组织已在同时运行 Teams 和 Skype for Business。是否可以直接禁用 Skype for Business？**<br>
不可以，你将需要将用户切换到“仅 Teams”模式来完成到 Teams 的升级。 如果贵组织已准备好升级到 Teams，请花时间与用户沟通，让他们了解将要发生的情况，让他们可以适应 Teams。 这将有利于确保其拥有正面的升级体验，以及有利于减少拨打给技术支持人员的电话。 如需示例沟通模板，请下载我们的 [Upgrade Success Kit](https://aka.ms/UpgradeSuccessKit)。


**如果我有升级过程方面的问题，可以联系谁？**<br>
如果你有与升级有关的问题，请联系你当前的联系点，可能包括为你分配的 Microsoft 帐户团队、合作伙伴或 [FastTrack](https://www.microsoft.com/en-us/fasttrack?rtc=1)。 或者，你可以从 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)内通过单击“**需要帮助**”按钮来开立一个帮助票证。

![“需要帮助”按钮](media/need-help-button.png)


**是要一起升级我的租户上的所有用户，还是可以选择一次升级选定的用户？**<br>
你可以根据需要灵活地将用户升级到 Teams，无论是个人、多组用户还是整个组织。 为了帮助了解最适合贵组织的方法，请查看你可以启用的各种[共存和升级模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。


**我的用户升级后会发生什么情况？**<br>

在你的用户升级到 Teams（**仅 Teams** 模式）后：

- 其 Skype for Business 客户端将被禁用，因为所有聊天和通话都将在 Teams 中进行。 此客户端将继续用于以前安排的 Skype for Business 会议。 如果此桌面客户端已卸载，用户将被重定向到通过 Skype for Business Web 应用访问以前安排的 Skype for Business 会议。

- 升级之前安排的任何 Skype for Business 会议都将正常进行，但所有新会议都在 Teams 中安排。 如果用户尝试登录 Skype for Business，其客户端会发出已升级到 Teams 的通知。 用户需要手动卸载其移动设备上的 Skype for Business 客户端。



**我在用户的客户端上激活升级通知后，他们是否仍能够使用 Skype for Business？**<br>
是，升级通知只是向用户提醒 Skype for Business 将升级到 Teams，并邀请他们开始使用 Teams（如果他们还没有开始使用）。 我们建议除了此通知外，还进行宣传活动（电子邮件、常见问题解答、技术支持人员就绪、海报/标牌），以传达贵组织特定的进一步详细信息，例如，升级执行时间、面向用户的行动号召、培训事项等。 如需沟通模板，请下载我们的 [Upgrade Success Kit](https://aka.ms/UpgradeSuccessKit)。


**从许可方面来看，这意味着什么？客户将如何为 Teams 中的智能通信服务付费？**<br>
Teams 在 Microsoft 365 和 Office 365 套件中提供。 现在 Skype for Business Online 中作为优质工作负荷的功能将继续在 Teams 中作为优质工作负荷。 客户在现有许可上的投入将转到 Teams 中。 例如，如果客户单独购买了音频会议或购买了包含音频会议的 E5（附带 Skype for Business），则将在 Teams 中启用音频会议，因为它现在可用。


**Microsoft 是否安排计划的升级？**<br>
当前，我们没有安排要为企业用户计划升级。 Skype for Business Online 将于 2021 年 7 月 31 日停用，在此之前，客户可选择根据组织的需要迁移到 Teams。 我们将为管理员和用户提供工具和指导，帮助其他们迁移到 Teams。

为了支持可能没有专用 IT 资源的小型客户，Microsoft 通过从 Skype for Business Online 到 Teams 的自动化升级提供协助。 符合条件的客户会收到通过电子邮件和消息中心通知发出的升级通知。 可在沟通资料中找到更多详细信息。 有关详细信息，请参阅[从 Skype for Business Online 到 Microsoft Teams 的自动升级](upgrade-automated.md)。



## <a name="microsoft-teams-capabilities-and-roadmap"></a>Microsoft Teams 功能和路线图

**Teams 的后端基础结构的优势是什么？**<br>
Teams 专为高度可扩展的微服务架构中的云构建，它可减少带宽消耗，提供更强大的遥测功能，并可在尽量减少中断的情况下进行维护和升级。 因此，用户无需下载插件，即可享有更快的会议加入时间和更好的浏览器体验。利用此现代基础结构，可以轻松地利用 Microsoft 认知服务，其中包括转录、翻译、语音识别和机器学习功能，可使通信和协作更加轻松和高效。

**客户如何了解何时将在 Teams 中提供 Skype for Business 功能？**<br>
请参阅 [Microsoft 365 路线图](https://aka.ms/O365Roadmap)。

**将为 Teams 提供哪些 API 和 SDK？**<br>
有关可用 API 和 SDK 的信息，请访问 [Microsoft Teams 开发人员平台](https://docs.microsoft.com/microsoftteams/platform/)。


**你是否支持 Teams 中的第三方开发机会？**<br>
支持，应用集成是采用 Teams 的主要优势之一。 我们目前支持 Teams 中的第三方聊天机器人、连接器和扩展。 此外，我们在 Microsoft Teams 应用商店中提供一个大型外接程序生态系统。

**Microsoft 365 教育版中是否提供 Teams？**<br>
所有 Microsoft 365 教育版套件许可（Microsoft A1、A3 和 A5）中均提供 Teams。

**政府社区云 (GCC) 中是否提供了 Teams？**<br>
是的，美国政府社区云 (GCC) 中提供了 Teams。 若要了解详细信息，请参阅 [Microsoft 365 GCC 部署规划](https://docs.microsoft.com/microsoftteams/plan-for-government-gcc)。



## <a name="calling-capabiities"></a>通话功能

**Microsoft 的联机语音功能的计划是什么？**<br>
我们语音解决方案的核心是现已推出的电话系统。 客户还可以添加 Microsoft 通话套餐，它为呼叫提供全面支持，包括直接在 Microsoft 365 中进行号码获取和分配。 希望保留其电信电话干线的客户可以使用直接路由功能 – 它包含在电话系统中。 根据组织的需要将两者混合使用，以便拥有完整的语音解决方案。

**对于已在 Skype for Business Online 中的电话系统（云 PBX）上部署的客户，有什么指导？**<br>
Microsoft Teams 中的呼叫功能可满足你的所有通信需求。 我们鼓励所有 Microsoft 365 客户开始独立使用 Teams 或与 Skype for Business 并行使用 Teams。


**对于希望迁移至 Teams 并使用呼叫功能的企业语音客户，有什么指导？**<br>
希望将自己的电话服务加入 Teams 的客户现在可以通过通用版本的[直接路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359)来实现。 在 Microsoft Teams 中可以选择使用直接路由和通话套餐拨打电话。

## <a name="meeting-capabilities"></a>会议功能


**Teams 中的音频会议覆盖范围与 Skype for Business 是否不同？**<br>
由于音频会议在 Teams 中可用，因此音频会议的覆盖范围没有变化。 我们目前覆盖 90 多个国家/地区和 400 多个城市，此覆盖范围在两个产品中将继续有效。 有关当前列表，请参阅[音频会议和通话套餐的国家/地区可用性](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。



**Teams 是否支持第三方音频会议提供商 (ACP)？**<br>
没有计划在 Teams 中支持第三方音频会议提供商 (ACP)。 我们认为，对于使用 Teams 和 Skype for Business 的客户，最佳的音频会议体验就是使用音频会议服务。 需要在 Skype for Business 会议中利用 ACP 支持的客户可以继续使用 Skype for Business 客户端加入 Skype for Business 会议。 在 Teams 中安排的会议将需要使用 Microsoft 365 的音频会议服务。

针对将第三方音频会议提供商 (ACP) 集成到 Skype for Business Online 的支持服务已延长到 2021 年 7 月 31 日，并为剩余活动租户提供有限支持，以便延长过渡时间。 这是 2018 年 4 月宣布的 ACP 时间表的更新。



**对 Teams 会议的视频互操作性支持有什么计划？**<br>
[会议室设备](https://products.office.com/microsoft-teams/across-devices)对于我们对新式工作场所的愿景至关重要。 通过现有 VTC 系统支持 Teams 会议的[云视频互操作性服务](https://docs.microsoft.com/microsoftteams/cloud-video-interop)通过我们的合作伙伴 Pexip、Polycom 和 Blue Jeans 提供。

**最新一代的 Skype Room Systems v2 是否支持 Teams 中的会议？**<br>
我们已将 Skype Room Systems 重新命名为“Microsoft Teams 会议室”，它完全支持 Microsoft Teams 会议，并通过在设备上启用 Teams 提供从 Skype for Business 到 Teams 的轻松迁移路径。

用户不仅能够通过接近检测来识别附近的 Microsoft Teams 会议室，还可以通过单击加入 Teams 会议。提供双屏支持和 Microsoft Whiteboard，并且我们将继续提供具有智能捕获功能的内容相机等创新功能。


**是否将更新 Skype Room Systems v1 以支持 Teams 会议？**<br>
我们已于 2018 年 10 月 9 日停止对安装有 Skype Room System 版本 1 (SRS v1) 软件的 Lync Room System (LRS) 设备提供支持。 这意味着 Skype Room Systems v1 软件将不再获得任何产品更新或修补程序。 建议安装有 Skype Room System v1 软件的 Lync Room System 设备的用户将其设备升级到 Microsoft Teams 会议室。 若要了解详细信息，请参阅[将 Lync 会议室系统 (LRS) 设备迁移到 Microsoft Teams 会议室](https://docs.microsoft.com/microsoftteams/rooms/lrs-migration)。

**Skype 会议直播是否将与 Skype for Business Online 同时停用？**<br>
是。 [Teams 实时事件](https://docs.microsoft.com/microsoftteams/teams-live-events/what-are-teams-live-events)是 Skype 会议直播的后续解决方案。


## <a name="management-capabilities"></a>管理功能

**Teams 的管理体验是什么？**<br>
与 Skype for Business 管理控制台一样，Microsoft 365 管理中心内的 [Microsoft Teams 管理中心 ](https://admin.teams.microsoft.com/) 是管理全新 Teams 体验的唯一场所。 在此门户中，管理员可以创建自定义联机状态、聊天、应用、会议和语音策略，以及为 Teams 用户分配策略。

## <a name="device-compatibility"></a>设备兼容性

**是否可以在 Surface Hub 上使用 Teams？**<br>
现在可以在 Surface Hub 上举行 Teams 会议，用户将拥有通话和会议体验。 有关详细信息，请参阅[部署 Microsoft Teams for Surface Hub](https://docs.microsoft.com/microsoftteams/teams-surface-hub)。

**目前的第三方 IP (3PIP) 手机能否继续使用 Microsoft Teams？如果是这样，可以使用多长时间？**<br>
Skype for Business Online 将于 2021 年 7 月 31 日停用。在此之后，只有迁移到 Teams 的 3PIP 设备用户能够继续使用 3PIP 设备，但此时功能受限且有效期截止 2023 年 7 月 31 日。

**认证的 Skype for Business Online 电话是否可与 Teams 协作？**<br>
有关与电话兼容性相关的问题，请阅读[认证的 Skype for Business Online 电话及其对 Teams 的意义](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/bc-p/125309)。







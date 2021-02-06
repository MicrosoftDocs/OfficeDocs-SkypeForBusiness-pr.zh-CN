---
title: 医疗保健组织的 Teams 入门
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 了解 Microsoft Teams 远程医疗、EHR 集成、一线员工系统集成和患者应用等医疗保健功能。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125765"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>医疗保健组织的 Teams 入门

Microsoft Teams 提供许多对医院和其他医疗保健组织有用的远程医疗功能。 Teams 功能正在开发中，有助于：

- 虚拟访问和电子医疗保健记录 (EHR) 集成
- Teams 策略包
- 安全消息传送
- Teams 模板
- 关注协调与协作

此功能是 Microsoft 医疗保健云的一部分。 详细了解如何使用此解决方案，该解决方案将 Azure、Dynamics 365 和 Microsoft Cloud for Healthcare 中的 Microsoft 365 功能 [汇集在一起](https://docs.microsoft.com/industry/healthcare)。

观看以下视频，了解有关使用医疗保健集合在 Microsoft Teams 中增强健康团队协作的更多内容。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 本部分的内容假定已在组织中部署 Teams。 如果尚未推出 Teams，请首先阅读"如何推广[Microsoft Teams"。](../../How-to-roll-out-teams.md)

以下方案适用于医疗保健组织：

| 使用场景 | 说明 | 要求 |
| -------- | -------- | -------- |
| [使用电子医疗保健记录与 EHR (集成进行虚拟) 访问](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 安排、管理和与患者进行虚拟访问。 此方案将 Microsoft Teams 和长篇平台连接到支持虚拟访问。 | Microsoft Cloud for Healthcare 的活动订阅或 Microsoft Teams EHR Connector 独立套餐的订阅。 <br> 用户必须具有相应的 Microsoft 365 或 Office 365 许可证（包括 Microsoft Teams 会议*）。 <br> 组织必须具有 2018 年 11 月版或更高版本的"长篇故事"版本。 <br>[EHR 要求的详细信息](ehr-admin.md#before-you-begin) |
| [使用 Microsoft Bookings 和 Bookings 应用进行虚拟访问](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 安排、管理和与患者进行虚拟访问。 此方案依赖于 Microsoft Bookings 来支持虚拟访问。 | 必须为组织启用 Microsoft Bookings。 <br> Bookings 应用的所有用户以及参与会议的所有用户都必须拥有支持 Teams 会议安排的许可证*。 <br>[Bookings 要求的详细信息](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams 策略包](#teams-policy-packages)| 确保医疗工作者、信息工作者和患者室设备具有对 Teams 功能的适当访问权限。| 用户必须具有适当的许可证*。 |
| [安全消息传送](#secure-messaging) | 更快地关注紧急邮件，并置信邮件已接收和已读。 | 用户必须具有适当的许可证*。  |
| [Teams 模板](#teams-templates-for-healthcare-organizations) | 创建一个团队，其中包括预定义的设置模板、频道和预安装的应用，以在医院、Pod 或部门内部，或医院内的多个医生、Pod 和部门之间通信和协作。 | 用户必须具有适当的许可证*。  |
| [关注协调与协作](#care-coordination-and-collaboration) | 医生和职员可以在内部协作处理日程安排、文档、任务等。| 用户必须具有适当的许可证*。 |

*支持 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商业标准版、A3、A5、E3 和 E5。 有关常规 Teams 许可详细信息，请参阅"[管理用户对 Teams 的访问权限"。](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>虚拟访问和电子医疗保健记录 (EHR) 集成

使用 Microsoft Teams 中的完整会议平台安排、管理和与患者进行虚拟访问。

- 如果组织已使用电子运行状况记录或 EHR，可以集成 Microsoft Teams，获得更无缝的体验。 借助 Microsoft Teams 电子健康记录 (EHR) Connector，医生可以轻松直接从 EHR 系统在 Teams 中启动虚拟患者访问或咨询其他提供商。 若要了解有关详细信息，请参阅"使用[Teams 进行虚拟访问 - 集成到 EHR"。](ehr-admin.md)
- 如果不使用受支持的 EHR，可以使用 Teams 中的 Microsoft Bookings 和 Bookings 应用。 若要了解详情，请参阅 Microsoft Teams 中的 [Bookings 应用和虚拟访问](../../bookings-app-admin.md)。

![使用 Microsoft Teams 进行虚拟访问](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams 策略包

应用 Teams 策略包，以定义不同角色在 Teams 中可以执行哪些任务。 例如，指定用于：

- 医疗工作者（如注册的医生、医生、医生和社交工作者）可以完全访问聊天、呼叫、轮班管理和会议。
- 医疗保健组织的信息工作者（例如 IT 人员、信息人员、财务人员和合规官）可以完全访问聊天、呼叫和会议。
- 患者室，用于控制患者室设备的设置。

若要了解有关详细信息，请参阅 [用于医疗保健的 Teams 策略包](../../policy-packages-healthcare.md)。

## <a name="secure-messaging"></a>安全消息传送

安全消息传送支持运行状况团队内的协作，包括多项新功能：

- 邮件发件人可以设置其邮件的特殊优先级，以便收件人在阅读邮件之前反复收到通知。
- 邮件发件人可以请求已读回执，因此当邮件收件人阅读他们发送的邮件时，他们会收到通知。

通过这些功能，可以更快地关注紧急邮件，并置信收到和阅读邮件。 可以基于每个患者创建使用这些功能的新健康团队。 这些功能基于策略，可分配给个人或整个 Teams。

若要了解有关详细信息，请参阅 [医疗保健组织的安全消息传送策略入门](messaging-policies-hc.md)。

与安全消息传送相关的另一个功能是让医疗保健组织联合的其他租户，从而允许更丰富的租户间通信。  (Microsoft Teams) 管理联合身份验证 [ (外部](../../manage-external-access.md)) 。

## <a name="teams-templates-for-healthcare-organizations"></a>医疗保健组织的 Teams 模板

已开发用于创建 Teams 的新模板以应用于医院设置，预计很快会推出更多模板。 这样一来，可以更轻松地创建医疗保健工作者用于协调各个部门或医院中患者护理的团队。 若要了解有关详细信息，请参阅 [医疗保健组织的 Teams 模板入门](healthcare-templates.md)。 团队可以针对内部部门（如疾病学）或护理室启动，并且更多模板正在开发中。

## <a name="care-coordination-and-collaboration"></a>关注协调与协作

将健康团队汇集在一起，通过 Microsoft Teams 协调护理并协作。

![医疗保健：在 Teams 中与健康团队协作](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams 使医生、医生、医生和其他人员能够使用 Microsoft Teams 中包含的协作功能进行高效协作，例如：

- 为健康团队和信息工作者设置团队和频道。 将带选项卡的频道用作构建工作的方法，并借助选项卡中可固定信息源的其他帮助。
- 聊天、发布消息和沟通。 你的团队可以就需要关注的不同患者展开持久对话。
- 与运行状况团队成员通话和开会。 通过 Teams 音频、视频、屏幕共享、录制和听录功能设置单个会议，或使用频道会议管理每日会议。
- 存储和共享文件和文档。 健康团队是处理和协作处理 Office 文档的单个虚拟化团队的一部分。

此外，团队可以使用 Teams 中的应用来：

- 使用列表应用共享列表和跟踪信息
- 使用"任务"应用跟踪和监视任务
- 使用"审批"应用简化审批
- 使用 Shifts 应用创建、管理和共享计划

### <a name="share-lists-and-track-information-with-the-lists-app"></a>使用列表应用共享列表和跟踪信息

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams 中的 [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 借助列表，医疗保健组织的护理团队可以创建从轮次和内部团队会议到常规患者监视等场景的患者列表。

Teams 中的列表应用可帮助团队跟踪信息和整理工作。 该应用已针对所有 Teams 用户预安装，并可在每个团队和频道中作为选项卡提供。 可以从头开始创建列表、从预定义模板创建列表，或者将数据导入 Excel。

健康团队可以使用"患者"模板开始。 他们可以创建列表来跟踪患者的需求和状态。 可以输入 Excel 电子表格上的现有患者数据，在 Teams 中创建列表。 这些列表可用于轮次和患者监视等方案，以协调护理。

例如，收费员在包含所有健康团队成员的团队内创建患者列表。 在轮次期间，健康团队会使用其移动设备访问 Teams，并更新列表中的患者信息，团队中的每个人都可以查看这些信息来保持同步。在健康团队聚集在一起，讨论和评估关键健康性能指标以确保患者处于正确的释放路径的轮次会话中，他们可以使用 Teams 在大型显示屏幕上共享此信息。 不现场的运行状况团队成员可以远程加入。

下面是为患者舍入设置的示例列表。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者舍入示例列表的屏幕截图":::

若要了解有关详细信息，请参阅 ["在 Teams 中为组织管理列表"应用](../../manage-lists-app.md)。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>使用"任务"应用跟踪和监视任务

使用 [Teams](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 中的任务跟踪，为整个健康团队执行项目。 运行状况团队可以从运行 Teams 的任何设备随时创建、分配和计划任务、对任务进行分类以及更新状态。

若要了解更多信息，请参阅 ["在 Microsoft Teams 中为组织管理任务"应用](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>使用"审批"应用简化审批

使用 ["](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) 审批"简化团队的所有请求和流程。 直接从中心创建、管理和共享审批，以用于团队合作。 从发送聊天的同一位置、频道对话中或"审批"应用本身启动审批流程。 只需选择审批类型、添加详细信息、附加文件并选择审批者。 提交后，审批者会收到通知，并可以审阅并处理请求。

你可以为组织允许"审批"应用，并将其添加到团队。 若要了解有关管理应用的信息，请参阅"在 Microsoft Teams 管理中心[管理应用"。](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>使用 Shifts 应用和一线辅助角色集成创建、管理和共享计划

Microsoft Teams 与 Shifts 应用和一线员工集成，可用于协调班次人员配备功能等。 例如，在班次中，医生经理可以设置和协调其职员的日程安排，而医生可以检查日程安排和调班。 Teams 包括内置 Frontline Worker 应用设置策略，可将其分配给组织的一线辅助角色。 默认情况下，该策略包括活动、Shifts、聊天和呼叫应用。 此策略控制这些应用的行为，例如，将 Shifts 应用固定到应用栏，以便团队可以快速访问它。

若要了解有关详细信息，请参阅"在 Microsoft Teams 中管理组织的[Shifts 应用"。](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>帮助医疗和信息工作者使用 Teams

有许多资源可帮助组织中的所有用户熟悉 Teams 的使用：

- 访问 [Teams 采用](https://adoption.microsoft.com/microsoft-teams/) 中心，了解有关推出 Teams 的建议（如果你只是开始组织使用 Teams 之旅，或者将 Teams 扩展到组织的更多领域）。
- 请考虑为用户 [设置自定义](https://adoption.microsoft.com/microsoft-365-learning-pathways/) 学习途径，以便只涵盖他们需要执行的任务。
- 获取有关如何在 Microsoft Teams 中在 [Teams](https://support.microsoft.com/teams)支持网站上执行基本任务的帮助和培训，包括 [快速培训视频](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)。 该网站还提供 Teams 应用的帮助和培训[，包括列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)、任务、[](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)审批、[](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)[预订](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)[和班次](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)。

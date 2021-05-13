---
title: 适用于医疗保健组织的 Teams 入门
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
description: 了解 Microsoft Teams 括号、EHR 集成、第一线工作者系统集成和患者应用等医疗保健功能。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: f6048d2413ea92e377358af43c7348abbbe00be1
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760595"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>适用于医疗保健组织的 Teams 入门

Microsoft Teams 提供对医疗保健和其他医疗保健组织有用的许多电话服务功能。 Teams 功能正在开发中，有助于有助于：

- 虚拟访问和电子医疗保健记录 （EHR） 集成
- Teams 策略包
- 安全消息传递
- Teams 模板
- 护理协调与协作

此功能是 Microsoft 云用于医疗保健的一部分。 深入了解如何使用此解决方案，它汇集了 [Microsoft Cloud for Healthcare](/industry/healthcare)中 Azure、Dynamics 365 和 Microsoft 365 的功能。

观看以下视频，了解有关使用医疗保健集合在 Microsoft Teams 中增强运行状况团队协作有关详细信息。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 本节中的内容假定你已在组织中部署 Teams。 如果尚未推出 Teams，首先请阅读 [Microsoft Teams](../../deploy-overview.md)。

以下方案适用于医疗保健组织：

| 方案 | 说明 | 要求 |
| -------- | -------- | -------- |
| [通过电子医疗保健记录 （EHR） 集成实现虚拟访问](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 安排、管理和与患者进行虚拟访问。 此方案将 Microsoft Teams 和此时的此时所平台连接到支持虚拟访问。 | Microsoft Cloud 用于医疗保健活动订阅或订阅 Microsoft Teams EHR Connector 独立优惠。 <br> 用户必须具有包含 Microsoft Teams 会议的适当 Microsoft 365 或 Office 365 许可证。 <br> 组织必须具有 2018 年 11 月或更高版本的 Epic 版本。 <br>[EHR 要求的详细信息](ehr-admin.md#before-you-begin) |
| [使用 Microsoft Bookings 和 Bookings 应用进行虚拟访问](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 安排、管理和与患者进行虚拟访问。 此方案依靠 Microsoft Bookings 支持虚拟访问。 | 必须为组织启用 Microsoft Bookings。 <br> Bookings 应用的所有用户以及参与会议的教职员工必须具有支持 Teams 会议安排*的许可证。 <br>[Bookings 要求的详细信息](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams 策略包](#teams-policy-packages)| 确保患者、信息工作者和患者会议室设备可以适当访问 Teams 功能。| 用户必须具有适当的许可证*。 |
| [安全消息传递](#secure-messaging) | 更快地关注紧急邮件，并放心收到并阅读了该邮件。 | 用户必须具有适当的许可证*。  |
| [Teams 模板](#teams-templates-for-healthcare-organizations) | 创建包含设置、通道和预安装的应用的预定义模板，用于在医院、<3> <2> <3>或部门，或在医院内的多个帐户、频道和部门之间沟通和协作。 | 用户必须具有适当的许可证*。  |
| [护理协调与协作](#care-coordination-and-collaboration) | 医师和教职员工可以在排程、文档、任务等进行内部协作。| 用户必须具有适当的许可证*。 |

*支持 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商业版标准版、A3、A5、E3 和 E5。 有关常规 Teams 许可详细信息，请参阅"管理 [Teams](../../user-access.md)。

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>虚拟访问和电子医疗保健记录 （EHR） 集成

使用 Microsoft Teams 中完整的会议平台来安排、管理和与患者进行虚拟访问。

- 如果你的组织已使用电子健康记录（EHR）和 Microsoft Teams，你可以集成 Microsoft Teams 以更加无缝的体验。 借助 Microsoft Teams 电子健康记录 (EHR) 连接器，临床医生可轻松地直接从 EHR 系统直接向 Teams 中的其他提供商发起虚拟患者访视或咨询。 有关详细信息，请参阅 [Teams 的虚拟访问 - 集成到 EHR](ehr-admin.md)。
- 如果使用的不是受支持的 EHR，可以在 Teams 中使用 Microsoft Bookings 和 Bookings 应用。 有关详细信息，请参阅 [Bookings 应用和 Microsoft Teams](../../bookings-app-admin.md)。

![使用 Microsoft Teams 进行虚拟访问](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams 策略包

应用 Teams 策略包来定义可在 Teams 中执行的不同角色。例如，针对以下角色指定策略：

- 患者（如已注册的医师、主治医师、医师和社交工作者）可完全访问聊天、呼叫、轮班管理和会议。
- 医疗保健组织的信息工作者（例如 IT 人员、信息使、财务人员和合规部人员）可以完全访问聊天、呼叫和会议。
- 患者会议室，用于控制患者会议室设备的设置。

若要了解更多信息，请参阅 [医疗保健服务 （Healthcare） 的 Teams](../../policy-packages-healthcare.md)。

## <a name="secure-messaging"></a>安全消息传递

安全消息传递支持运行状况团队中的协作，包括以下几项新功能：

- 邮件发件人可以设置其邮件的特殊优先级，因此在收件人阅读该邮件之前，将重复收到通知。
- 邮件发件人可以请求已读回执，因此在邮件收件人阅读其发送的邮件时收到通知。

通过这些功能，可更快地关注紧急邮件，让邮件能够被接收和阅读。 可以在每患者的基础上创建使用这些功能的新健康团队。 这些功能基于策略，可分配到个人或整个团队。

若要了解更多信息，请参阅 [医疗保健组织安全邮件策略入门](messaging-policies-hc.md)。

与安全消息相关的是，允许由医疗保健组织联合的其他租户，从而允许更丰富的租户间通信。 （请参阅 [Microsoft Teams 网站中管理外部访问（联合](../../manage-external-access.md)））。

## <a name="teams-templates-for-healthcare-organizations"></a>适用于医疗保健组织的 Teams 模板

开发新的用于创建 Teams 的模板可应用于医院设置，并即将推出更多模板。 通过此操作，可更轻松地创建由医疗保健人员用于协调不同部门或部门中患者护理的团队。 有关详细信息，请参阅 [医疗保健组织或组织的 Teams 模板](./healthcare-templates-admin-console.md)。 可针对内部部门（如流程图）或护理中心启动团队，开发中更多模板。

## <a name="care-coordination-and-collaboration"></a>护理协调与协作

请您的健康团队聚在一起，以与 Microsoft Teams 协调护理并协作。

![医疗保健：在 Teams 中与运行状况团队协作](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams 提供 Microsoft Teams 中包含的协作功能，使医师、医师和其他人员能够高效协作，例如：

- 为运行状况团队和信息工作者设置团队和频道。 将带选项卡的频道用作组织工作结构的方法，从选项卡中可固定信息源的更多帮助。
- 聊天、发布消息和交流。你的团队可就需要关注的不同患者进行长时间的对话。
- 与医疗保健团队的成员通话和见面。通过 Teams 音频、视频、屏幕共享、录音和听录功能，安排单场会议或使用频道会议来管理日常会议。
- 存储和共享文件与文档。医疗保健团队是单个虚拟团队的一部分，该团队可处理 Office 文档并协作处理文档。

此外，团队可使用 Teams 中的应用：

- 使用"列表"应用共享列表和跟踪信息
- 使用"任务"应用跟踪和监视任务
- 通过审批应用简化审批
- 使用 Shifts 应用创建、管理和共享日程安排

### <a name="share-lists-and-track-information-with-the-lists-app"></a>使用"列表"应用共享列表和跟踪信息

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。

Teams 中的列表应用可帮助团队跟踪信息和组织工作。 该应用已可供所有 Teams 用户预安装，并可在每个团队和频道中用作选项卡。 可以从头开始、从预定义模板或将数据导入 Excel 创建列表。

医疗保健团队可使用患者模板开始操作。 他们可创建列表以跟踪患者的需求和状态。 可以参与 Excel 电子表格上的现有患者数据，在 Teams 中创建一个列表。 这些列表可用于圆形和患者监视等方案协调护理。

例如，护士长在包含所有医疗保健团队成员的团队中创建一个患者列表。在轮班期间，医疗保健团队会通过各自的移动设备访问 Teams 并更新列表中的患者信息，团队中的每个人都可以查看这些信息保持同步。在轮班会议中，医疗保健团队聚到一起讨论和评估关键的健康表现指标，确保患者病情正朝着出院的方向好转。在开会期间，他们可使用 Teams 在大显示屏上分享此信息。未到现场的医疗保健团队成员可远程参加。

下面是为患者舍入而设置的示例列表。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="用于患者四角的示例列表的屏幕截图":::

有关详细信息，请参阅 [Teams](../../manage-lists-app.md)中为组织管理列表。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>使用"任务"应用跟踪和监视任务

在 teams [使用](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 任务"来跟踪为整个健康团队执行项目。 你的健康团队可以从运行 Teams 的任何设备随时创建、分配和安排任务、对任务进行分类和更新状态。 IT 专业人员和管理员还可针对你的组织向特定团队发布任务。 例如，你可就要在全院采纳的新的安全协议或新的住院措施发布一组任务。

有关详细信息，请参阅 [Microsoft Teams 中为组织管理"任务"应用](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>通过审批应用简化审批

使用 [审批](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) ，通过团队简化所有请求和流程。 直接从中心创建、管理和共享批准，进行团队合作。 从发送聊天的同一位置、频道对话中，或者从审批应用本身开始审批流程。 只需选择审批类型、添加详细信息、附加文件，然后选择审批者。 提交后，审批者将收到通知，审阅者可以审阅并响应请求。

可针对组织允许审批应用，并将其添加到团队。 有关详细信息，请参阅 [Teams 审批应用的可用性](../../approval-admin.md)。

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>使用 Shifts 应用和第一线工作者集成，创建、管理和共享日程安排

Microsoft Teams 与 Shift 应用和第一线工作者集成，这可用于协调排班功能等。 例如，在排班中，分区经理可以设置并协调员工的日程安排，并且主管可检查日程安排和调班。 团队中包含内置的"第一线工作者"应用设置策略，可将其分配给组织中第一线工作者。 默认情况下，该策略包括“活动”、“班次”、“聊天”和“通话”应用。 此策略控制这些应用的行为，例如将 Shifts 应用固定到应用栏以便团队可快速访问它。

有关详细信息，请参阅 [Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)中为组织管理 Shifts。

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>帮助你的实验室和信息工作者使用 Teams

有许多资源可帮助你组织所有用户熟悉使用 Teams：

- 如果只是 [使用 Teams，或者将 Teams 扩展到组织的更多领域，请访问 ](https://adoption.microsoft.com/microsoft-teams/) 团队采用中心，了解有关推出 Teams 的建议。
- 请考虑设置自定义 [学习](https://adoption.microsoft.com/microsoft-365-learning-pathways/) ，以便你的用户只涵盖其需要执行的任务。
- 在 [Teams 支持网站](https://support.microsoft.com/teams)上获取有关如何在 Microsoft Teams 中执行基本任务的帮助和培训，包括 [快速培训](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)。 此网站还包括 Teams 应用的帮助和培训，包括 [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)、 [任务](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)、 [审批](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)、 [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)和 [Shift](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)。

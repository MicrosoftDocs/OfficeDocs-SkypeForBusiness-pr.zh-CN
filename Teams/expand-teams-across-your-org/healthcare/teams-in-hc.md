---
title: 适用于医疗保健组织的 Teams 入门
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 了解医疗保健的功能，包括护理协调、安全消息、虚拟访问、EHR 集成和一线 worker 系统集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03de58e9fef94dcf63649920cde5a3663a25889e
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433055"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>适用于医疗保健组织的 Teams 入门

Microsoft 团队提供了许多适用于医院和其他医疗保健组织的功能。 团队功能正在开发中，可帮助医院帮助医院：

- 护理协调和协作
- 安全消息
- 虚拟访问
- 电子医疗保健记录 (EHR) 集成
- 一线 Worker 系统集成

本部分内容基于团队的基础功能（如会议、呼叫和消息传递），并假设你已经在组织中部署了团队。 如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](../../How-to-roll-out-teams.md)。

## <a name="care-coordination---microsoft-teams-patients-app"></a>护理协调-Microsoft 团队患者应用

> [!IMPORTANT]
> **2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。 当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。
>
>" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。 使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。 若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。

Microsoft 团队现在具有特定于医疗保健组织的护理协调解决方案，可帮助他们提供最佳的患者护理。 Crux "护理协调解决方案" （Microsoft 团队患者应用）是一种第一方选项卡应用，它与电子运行状况记录集成 (EHR) 系统使用快速医疗保健互操作性资源 ([FHIR](https://www.hl7.org/fhir/)) 界面将宝贵的医学信息引入 Microsoft 团队以实现临床协作和通信。  

"护理协调" 解决方案可以与主要独立软件供应商进行交互， (Isv) ，可使用 HL7v2 和 FHIR 等现有健康数据标准将患者应用连接到 EHR 系统。 与以下行业领导人的 Microsoft 合作伙伴建立与团队的电子健康记录集成：

- Datica (通过其 [CMI](https://datica.com/compliant-managed-integration/) 服务) 
- Infor Cloverleaf ([INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) 
- Redox (通过 [R ^ FHIR 服务器](https://www.redoxengine.com/fhir/)) 
- Dapasoft (通过 [Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) 

尝试为医疗保健提供商组织实施 Microsoft 团队的 EHR 集成和互操作合作伙伴需要向患者应用提供与医疗保健提供商组织的 EHR 系统的安全且经过身份验证的连接。 这将启用单向 (只读) 将相关患者记录的流读入患者应用。 患者应用理解 FHIR 格式，因此合作伙伴还负责将聚合数据从各种其他格式（如 HL7v2 等）转换为 FHIR DSTU2 或 STU3。

患者应用集成了电子运行状况记录 (EHR) 系统，并支持护理提供商在团队的安全平台中实时交流患者护理。 患者应用是护理协调领域的第一大投资，旨在解决以下难题：

- 通过患者体验实现高效率和关键通信的低效率
- 带来管理负担的各自为政的信息
- 具有复杂且零散的协作工具的临床医生中的不满
- 非常低效的人员间护理协作，可能会产生太昂贵的临床时间

Microsoft 团队支持医生、临床医生、护士和其他员工通过以下方式高效协作：

- 成为可在 Office 文档上工作和协作的单个虚拟化团队的一部分
- 与需要关注的不同患者进行持续对话
- 将频道与选项卡配合使用来组织其工作，使用可固定信息源的选项卡中的其他帮助
- 将频道会议与团队的强大功能结合使用音频、视频、屏幕共享、录制和设备功能来管理日常会议
- 使用患者应用策展必须监控的高风险患者的列表，并从 EHR 系统中提取最新的详细信息。 患者应用本身将以下功能添加到 Microsoft 团队：
  - 可以在单个频道中创建多个患者列表。
  - 能够通过可配置的栏查看和排序患者显示的信息。
  - 通过团队模板自动预配应用的功能。
  - 适用于 iOS 和 Android 适用于 iOS 和 Android 的团队应用，适用于移动用户第一个医疗保健工作人员以及 Microsoft 团队 web 和桌面客户端。
  - 通过分析一致性语句支持 FHIR DSTU2 和 STU3 版本。
  - 针对其用户界面上的所有视图和搜索操作的审核日志，以保护每个 HIPAA 准则的 PHI。

患者应用在团队扩展性平台上构建，并利用选项卡框架在频道内显示丰富的患者内容。 若要了解有关其他团队应用和平台本身的详细信息，请参阅 [Microsoft 团队应用](/microsoftteams/platform/concepts/apps/apps-overview)。  

> [!NOTE]
> 患者应用在私人预览版中，FHIR 界面位于 beta 中。 发布的版本不应向后兼容。

![桌面和移动设备上患者应用的屏幕截图](../../media/ehr-2.png)

有关实现的详细信息，请参阅将 [电子医疗保健记录集成到 Microsoft 团队](patients-app.md) 中。

## <a name="teams-templates"></a>团队模板

创建团队的新模板已开发为适用于医院的设置，并且预计会更多。 这使您可以更轻松地创建医疗保健工作者在各种部门或 wards 中协调病人的护理。 请参阅 [面向医疗保健组织的团队模板入门](healthcare-templates.md)。 团队可以为内部部门（如心脏病科）或用于护理 wards 的团队开始，并且更多模板位于开发中。

## <a name="lists-app"></a>列表应用

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

团队中的 "列表" 应用可帮助团队跟踪信息和组织工作。 为所有团队用户预安装应用，并且该应用在每个团队和频道中均可用作选项卡。 可以从预定义的模板或将数据导入到 Excel 中从头开始创建列表。

护理团队可以使用患者模板开始使用。 他们可以创建列表来跟踪病人的需求和状况。 可将 Excel 电子表格中的现有患者数据引入到团队中以创建列表。 这些列表可用于诸如倒圆角和患者监视等方案来协调护理。

例如，收费护士在包含所有护理团队成员的团队中创建一个患者列表。 在舍入过程中，护理团队在其移动设备上访问团队并更新列表中的患者信息，团队中的每个人都可以查看它们以保持同步。在 glide 的舍入会话中，护理团队收集以讨论和评估关键运行状况性能指标以确保患者在合适的路径上，他们可以使用大型显示屏幕上的团队共享此信息。 不在网站上的护理团队成员可以远程加入。

下面是为患者舍入设置的示例列表。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者舍入示例列表的屏幕截图":::

若要了解详细信息，请参阅 [管理团队中组织的列表应用](../../manage-lists-app.md)。

## <a name="secure-messaging"></a>安全消息

安全邮件支持在护理团队内进行协作，包括以下几项新功能：

- 邮件发件人可以为其邮件设置特殊优先级，以便收件人在阅读邮件之前反复收到通知。
- 邮件发件人可以请求已读回执，这样当邮件收件人阅读邮件时，会收到通知。

结合这些功能，可以更快地注意紧急邮件，并确保邮件已接收和阅读。 使用这些功能的新的护理团队可以在每个患者的基础上创建。 这些功能是基于策略的，可分配给个人或整个团队。

有关 [医疗保健组织的安全邮件策略](messaging-policies-hc.md) 的详细信息，请参阅入门。

同时与安全消息相关的功能是拥有受医疗保健组织联盟的其他租户，从而实现了更丰富的租户间通信。  (请参阅 [管理 Microsoft 团队) 中的 "管理外部访问 (联合身份验证") ](../../manage-external-access.md) 。

## <a name="firstline-worker-integration"></a>一线工作人员集成

Microsoft 团队与一线工作人员集成，可用于协调倒班人员配备功能。 请参阅 [在 Microsoft 团队中管理你的组织的倒班应用](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。

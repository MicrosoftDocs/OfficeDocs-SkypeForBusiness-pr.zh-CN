---
title: 适用于医疗保健组织的 Teams 入门
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 适用于医疗保健组织的 Teams 入门
ms.openlocfilehash: 380d9c75bc2f7eeb66bc6d0d0f5598d2a243a9da
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767151"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>适用于医疗保健组织的 Teams 入门

Microsoft 团队提供了许多适用于医院和其他医疗保健组织的功能。 团队功能正在开发中，可帮助医院帮助医院：

- 护理协调和协作
- 安全消息
- Telehealth
- 电子医疗保健记录（EHR）集成 
- 一线 Worker 系统集成 

本节内容基于团队的基础功能（如会议、呼叫和消息传递），并假定你已部署在组织中部署的团队。 如果尚未推出团队，请先阅读[如何展示 Microsoft 团队](../../How-to-roll-out-teams.md)。

## <a name="care-coordination---microsoft-teams-patients-app"></a>护理协调-Microsoft 团队患者应用

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 团队现在具有特定于医疗保健组织的护理协调解决方案，可帮助他们提供最佳的患者护理。 护理协调解决方案的 crux （Microsoft 团队患者应用）是第一方选项卡应用，它与使用快速医疗保健互操作性资源（FHIR）接口的电子医疗记录（[](https://www.hl7.org/fhir/)）接口集成，以带来宝贵的将医疗信息插入到 Microsoft 团队的上下文中，以实现临床协作和通信。  

"护理协调" 解决方案可以与主要独立软件供应商（Isv）进行交互，这些供应商（Isv）可以使用现有的运行状况数据标准（如 HL7v2 和 FHIR）将患者应用连接到 EHR 系统。 与以下行业领导人的 Microsoft 合作伙伴建立与团队的电子健康记录集成：

- Datica （通过其[CMI](https://datica.com/compliant-managed-integration/)产品）
- Infor Cloverleaf （通过[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）
- Redox （通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/)）
- Dapasoft （通过[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)）

尝试为医疗保健提供商组织实施 Microsoft 团队的 EHR 集成和互操作合作伙伴需要向患者应用提供与医疗保健提供商组织的 EHR 系统的安全且经过身份验证的连接。 这将向患者应用启用相关患者记录的单向（只读）流。 患者应用理解 FHIR 格式，因此合作伙伴还负责将聚合数据从各种其他格式（如 HL7v2 等）转换为 FHIR DSTU2 或 STU3。

<br>

![插图突出显示护理协调和协作](../../media/ehr-1.png)

<br>

患者应用集成了电子运行状况记录（EHR）系统，使护理提供商可以实时地与团队的安全平台中的患者护理进行沟通。 患者应用是护理协调领域的第一大投资，旨在解决以下难题：

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

患者应用在团队扩展性平台上构建，并利用选项卡框架在频道内显示丰富的患者内容。 若要了解有关其他团队应用和平台本身的详细信息，请参阅[Microsoft 团队应用](/microsoftteams/platform/concepts/apps/apps-overview)。  

> [!NOTE]
> 患者应用在私人预览版中，FHIR 界面位于 beta 中。 发布的版本不应向后兼容。

![桌面和移动设备上患者应用的屏幕截图](../../media/ehr-2.png)

有关实现的详细信息，请参阅将[电子医疗保健记录集成到 Microsoft 团队](patients-app.md)中。

## <a name="templates"></a>Templates

创建团队的新模板已开发为适用于医院的设置，并且预计会更多。 这使您可以更轻松地创建医疗保健工作者在各种部门或 wards 中协调病人的护理。 请参阅[面向医疗保健组织的团队模板入门](healthcare-templates.md)。 团队可以为内部部门（如心脏病科）或用于护理 wards 的团队开始，并且更多模板位于开发中。

## <a name="secure-messaging"></a>安全消息

安全邮件支持在护理团队内进行协作，包括以下几项新功能：

- 邮件发件人可以为其邮件设置特殊优先级，以便收件人在阅读邮件之前反复收到通知。
- 邮件发件人可以请求已读回执，这样当邮件收件人阅读邮件时，会收到通知。


结合这些功能，可以更快地注意紧急邮件，并确保邮件已接收和阅读。 使用这些功能的新的护理团队可以在每个患者的基础上创建。 这些功能是基于策略的，可分配给个人或整个团队。

有关[医疗保健组织的安全邮件策略](messaging-policies-hc.md)的详细信息，请参阅入门。

同时与安全消息相关的功能是拥有受医疗保健组织联盟的其他租户，从而实现了更丰富的租户间通信。 （请参阅[管理 Microsoft 团队中的外部访问（联合）](../../manage-external-access.md)。

## <a name="firstline-worker-integration"></a>一线工作人员集成

Microsoft 团队与一线工作人员集成，可用于协调倒班人员配备功能。

 请参阅以下文章：

- [将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [在 Microsoft Teams 中为组织管理 Shifts 应用](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

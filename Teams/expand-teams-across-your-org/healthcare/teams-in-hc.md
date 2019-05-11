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
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 适用于医疗保健组织的 Teams 入门
ms.openlocfilehash: 40eccf379af8c0acd318cb3a8b1b647357f6cf7c
ms.sourcegitcommit: a46dad8dfc685534d81bb011f3c099c6f59ce2e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "33882890"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>适用于医疗保健组织的 Teams 入门

Microsoft 团队提供了大量医院和其他医疗保健机构有用的功能。 正在开发以帮助与医院是团队功能：

- 医护协调和协作
- 安全邮件
- Telehealth
- 电子医疗保健记录 (EHR) 集成 
- Firstline 工作者系统集成 

这是除了的 Microsoft 团队的基本功能，如会议/呼叫和消息。 

## <a name="care-coordination---microsoft-teams-patients-app"></a>医护协调-Microsoft 团队患者应用程序

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 团队现在具有特定于医疗保健组织，以帮助他们提供最佳医患护理协调解决方案。 医护协作解决方案，Microsoft 团队患者应用程序的关键是与电子健康记录使用的 Fast 医疗保健互操作性资源 ([FHIR](https://www.hl7.org/fhir/)) 接口以显示有价值的 (EHR) 系统集成的第一个方选项卡应用程序若要启用临床协作和通信的上下文中的 Microsoft 团队医疗信息。  

医护协调解决方案可以与领先的独立软件供应商 (Isv) 可以连接到使用现有的运行状况数据标准，如 HL7v2 和 FHIR 您 EHR 系统的患者应用程序的接口。 Microsoft 合作伙伴与以下的行业领导者，建立与团队电子健康记录集成：

- Datica （通过其[CMI](https://datica.com/compliant-managed-integration/)产品）
- 项 Cloverleaf （通过[项 FHIR 桥](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）
- Redox (通过[R ^ FHIR 服务器](https://www.redoxengine.com/fhir/))
- Dapasoft （通过[Corolar FHIR 上](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

EHR 集成和互操作性合作伙伴尝试为医疗保健提供程序组织实现的 Microsoft 团队需要提供与医护人员提供程序组织 EHR 系统的安全和身份验证连接的患者应用程序。 这样一个双向 （只读） 流到患者应用程序的相关患者记录。 患者应用程序可识别的 FHIR 格式，以便合作伙伴程序还负责将从各个其他格式，例如 HL7v2 等聚合的数据转换为 FHIR DSTU2 或 STU3。

<br>

![EHR 集成](../../media/ehr-1.png)

<br>

与电子健康记录 (EHR) 系统集成患者应用程序和启用医护提供程序进行通信医患中有关实时团队的安全平台中。 患者应用程序是旨在解决以下难题的医护协调区域中的第一个主要投资：

- 延期和关键通信患者体验通过低效率
- 创建管理负担的孤立的信息
- 不满之间临床和复杂和零碎协作工具
- 可以刻录太多昂贵的临床时间的低效的现场医护协调

Microsoft 团队使医生、 临床医生、 护理和其他人员通过有效地协作：

- 单个虚拟化团队的工作原理，以及对 Office 文档协作的一部分
- 需要注意的不同患者持久对话
- 通道使用选项卡作为一种方式结构他们的工作，他们可以向其 pin 信息源的选项卡的其他帮助
- 使用团队音频、 视频、 屏幕共享、 录制和转录功能的强大功能与通道会议管理每日会议
- 使用患者应用程序 curate 高风险患者必须监视和提取 EHR 系统从其最新的详细信息的列表。 患者应用程序本身的 Microsoft 团队中向以下功能：

    - 能够创建多个患者列表中的单个通道。
    - 能够查看和显示的有关通过可配置列患者的信息进行排序。
    - 自动设置通过团队模板应用程序的功能。
    - 适用于 iOS 团队相关应用程序和 Android 移动的第一个医疗保健工作者，以及 Microsoft 团队 web 和桌面客户端。
    - 通过解析一致性的 FHIR DSTU2 和 STU3 版本支持。
    - 对其用户界面来保护 PHI 每 HIPAA 准则的所有视图和搜索操作的审核日志。

患者应用程序团队扩展性平台上构建和利用选项卡框架，用来显示在频道内丰富患者的内容。 若要了解有关其他团队应用程序和平台本身的详细信息，请参阅[相关应用程序的 Microsoft 团队](/microsoftteams/platform/concepts/apps/apps-overview)。  

> [!NOTE]
> 患者应用程序处于专用预览以及 FHIR 接口是在 beta。 已发布的版本不会为向后兼容。

![患者应用程序屏幕截图](../../media/ehr-2.png)

实现详细信息，请参阅[到 Microsoft 团队集成电子医疗保健记录](patients-app.md)。

## <a name="templates"></a>模板

新模板，用于创建团队的开发要应用于某个医院设置，以及推出期望的详细信息。 这样，更轻松地创建医疗保健工作人员使用的各种部门或病房患者协调医护团队。 请参阅[Get started with 医疗保健机构的工作组模板](healthcare-templates.md)。 可以启动团队，如心脏病学内部部门或护理病房且更多模板中开发。

## <a name="secure-messaging"></a>安全邮件

医护团队，包括几种新功能中的安全邮件支持协作：

- 邮件发件人可以设置人的邮件的特殊优先级，以便他们阅读邮件之前，将重复通知收件人。
- 邮件发件人可以请求已读的回执，以便在邮件收件人已阅读它们发送邮件时通知它们。


在一起，这些功能允许更快地重视紧急邮件和可信度邮件已接收和阅读。 可以在每个患者基础上创建使用这些功能的新医护团队。 这些功能是基于策略的并可以分配给个人或整个团队。

有关详细信息，请参阅[入门 Secure Messaging 医疗保健组织的策略](messaging-policies-hc.md)。

此外相关的保护消息是具有其他租户的联盟医疗保健组织允许更丰富的租户间通信的功能。 （请参阅[管理外部访问 （联合身份验证） 中的 Microsoft 团队](../../manage-external-access.md)）。

## <a name="firstline-worker-integration"></a>Firstline 工作者集成

与 Firstline 工作者，可用于协调 shift 人员配备功能等集成的 Microsoft 团队。

 请参阅以下文章：

- [将 Microsoft StaffHub 团队移动到引进中的 Microsoft 团队](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [在 Microsoft Teams 中为组织管理 Shifts 应用](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

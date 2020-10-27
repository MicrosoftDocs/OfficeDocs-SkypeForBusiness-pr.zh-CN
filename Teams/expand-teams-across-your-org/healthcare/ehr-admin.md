---
title: 用于虚拟访问的团队
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
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
description: 使用 Microsoft 团队设置你的虚拟访问系统
ms.openlocfilehash: dcf852486d6a7fbace23bea5fb8610c62bdc7e4f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766715"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>与团队的虚拟访问-集成到 EHR

Microsoft 团队电子医疗记录 (EHR) 连接器使临床医生能够轻松地从 EHR 系统与团队中的另一个提供商发起虚拟患者访问或咨询。 Microsoft 团队基于 Microsoft 365 云构建，支持在支持 HIPAA、高科技认证等的单个集线器中使用聊天、视频、语音和医疗保健工具实现简单、安全的协作和通信。

团队的通信和协作平台使临床医生能够轻松地通过零散的系统进行混乱，以便他们可以花时间提供最佳护理。 Microsoft 团队电子医疗记录 (EHR) 连接器可以：

- 启动团队从提供商和患者门户进行虚拟访问。

- 在连接和断开连接事件上写回 EHR 元数据，以启用自动审核和记录保留。

- 集成到现有 clinician 和患者工作流，同时允许他们使用 Microsoft 团队。

## <a name="before-you-begin"></a>开始之前

在集成 EHR 连接器之前，你需要确保具有以下先决条件：

- 适用于 Microsoft Cloud for 医疗保健的活动订阅或 Microsoft 团队订阅的 Microsoft 团队 EHR 连接器独立优惠。

- 用户必须具有相应的 Microsoft 365 或 Office 365 许可证，其中包含 Microsoft 团队会议。

- 应在组织内部采纳和使用 Microsoft 团队。

- 组织必须使用长篇版本2018或更高版本。

- 您的系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

你还需要来自组织中以下人员的信息：

- Microsoft 365 管理员

- 长篇故事管理员

> [!Note]
> 请求长篇故事管理员提供 Epic-Microsoft 的团队 Telehealth 集成指南，该指南在长篇故事市场中可用。

## <a name="connector-setup"></a>连接线设置

连接器设置要求你：

- [启动 EHR 连接器配置门户](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [配置提供商组织信息](ehr-admin.md#configure-provider-organization-information)
- [验证和批准配置](ehr-admin.md#verify-and-approve-the-configuration)
- [查看和完成配置](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[启动 EHR 连接器配置门户](#launch-the-ehr-connector-configuration-portal)

通过启动 EHR 连接器配置门户，将你的医疗保健组织配置为启动与 Microsoft 团队的虚拟访问。 使用测试 URL 配置长篇测试环境的连接器。 准备好启用长篇制作环境时，请使用生产 URL。
  
- 测试环境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)
- 生产环境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

您的组织中的 Microsoft 365 管理员和长篇故事管理员必须完成配置门户中的信息和集成步骤。 对于长篇故事配置步骤，请联系分配给你的组织的长篇故事资源。

### <a name="configure-provider-organization-information"></a>[配置提供商组织信息](#configure-provider-organization-information)

此步骤将由 Microsoft 365 管理员完成。 Microsoft 365 管理员必须启动连接器配置门户并通过 Microsoft 凭据登录才能启动配置过程。

若要完成此步骤，Microsoft 365 管理员必须收到一个有效的快速运行状况互操作性资源 (FHIR 来自 Microsoft 365 管理员的) 基 URL，以及将审批配置的长篇管理员的用户名。 Microsoft 365 管理员必须启动连接器配置页面，并以 Microsoft 凭据登录才能启动配置过程。

- FHIR 基 URL 是对应于服务器 FHIR API 终结点的静态地址。 示例 URL 是 [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) 。

- 配置审批者名称是将负责审批配置的长篇故事系统管理员的名称。

  ![将从 EHR 连接器的列表中选择配置审核人的姓名。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[验证和批准配置](#verify-and-approve-the-configuration)

作为审批者添加的医疗保健组织的长篇故事管理员必须现在使用同一 EHR 连接器 URL，以便使用其 Microsoft 365 凭据进行登录。 成功验证后，将要求审批者使用其长篇凭据进行登录以验证长篇故事组织。

> [!Note]
> 组织中的 Microsoft 365 管理员和长篇故事管理员可以是同一个人。 在这种情况下，在第一步中添加您自己的用户名作为审批者。 您仍需登录长篇故事以验证您的访问权限。 长篇故事登录仅用于验证你的 FHIR 基本 URL。 Microsoft 不会使用此登录存储凭据或访问 EHR 数据。

  ![验证和批准凭据配置。](../../media/ehc-provider-2.png)

成功长篇故事登录后，长篇故事管理员 **必须** 批准该配置。 如果配置不正确，Microsoft 365 管理员将能够通过再次登录 Microsoft EHR 连接器门户来修改原始配置。

![确认已配置 EHR 连接器，并选择更改配置。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[查看和完成配置](#review-and-finish-the-configuration)

当长篇管理员批准配置信息时，您将看到患者和提供商启动的集成记录。 这些记录是完成长篇故事中的虚拟访问配置所必需的。 有关详细信息，请参阅 Epic-Microsoft 的团队 Telehealth 集成指南。

> [!Note]  
> Microsoft 365 或长篇故事管理员可以随时登录到配置门户以查看集成记录和修改组织配置（如有必要）。

![显示集成信息。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a>启动团队虚拟访问

完成 EHR 连接器步骤和长篇配置后，你的组织已准备好支持 Microsoft 团队的视频访问。

### <a name="virtual-visit-prerequisites"></a>虚拟就诊先决条件

- 您的系统必须满足所有 [软件和浏览器先决条件](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

- 医疗保健组织必须已完成长篇企业和 Microsoft 365 组织之间的设置。

### <a name="provider-experience"></a>提供程序体验

你的组织中的医疗保健提供商还可以通过其长篇提供商应用程序 (超空间、Haiku、Canto) 与 Microsoft 团队的虚拟访问进行联接。 " **开始虚拟访问** " 按钮嵌入在提供程序流中。

提供程序体验的关键功能：

- 提供程序可使用支持的浏览器或 Microsoft 团队应用程序加入虚拟访问。

- 当首次加入虚拟访问时，提供程序必须使用 Microsoft 365 帐户进行一次登录。

- 在一次性登录后，提供者将直接转到 Microsoft 团队中的虚拟约会。  (提供商必须登录到 Microsoft 团队) 。

- 提供商可以查看为给定约会连接和断开连接的参与者的实时更新。 当患者连接到虚拟访问时，提供商可以看到。

  ![提供商体验与患者的虚拟访问](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>患者体验

该连接器支持患者通过 MyChart web 和手机加入虚拟走访。 在约会时，病人可以使用 " **开始虚拟访问** " 按钮从 MyChart 开始虚拟访问。

患者体验的关键功能：

- 在没有应用安装的情况下，患者可以从桌面和移动设备上的新式 web 浏览器中加入虚拟访问。

- 患者只需单击一次即可加入虚拟访问，无需其他帐户或登录。

- 不需要患者创建 Microsoft 帐户或登录以启动虚拟访问。

- 患者将放在大厅，直到医疗保健提供商加入约会并将其准许到虚拟就诊。

- 在加入虚拟访问之前，可以在大厅中测试视频和麦克风。

  ![虚拟就诊的患者体验](../../media/ehc-virtual-visit-5.png)

> [!Note]
> 长篇故事、MyChart、Haiku 和 Canto 是长篇故事系统公司的商标。

### <a name="privacy-and-location-of-data"></a>数据的隐私和位置

团队集成到 EHR 系统可优化集成和虚拟访问流程期间正在使用和存储的数据量。 该解决方案遵循团队隐私中概述的整个团队隐私和数据管理原则和指南。

Microsoft 团队 EHR 连接器不会在 EHR 系统中存储和传输任何可识别的个人数据或患者或医疗保健提供商的任何健康记录。 EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在团队会议设置期间使用。 EHR 用户的唯一 ID 存储在 [存储 Microsoft 365 客户数据的位置](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 中所述的三个地理区域之一。 会议参与者向团队输入的所有聊天、录制和其他数据将根据现有的存储策略进行存储。 如果想要了解有关 Microsoft 团队中的数据位置的详细信息，请访问 [团队中的数据位置](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。

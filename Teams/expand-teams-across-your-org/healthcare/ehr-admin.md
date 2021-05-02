---
title: Teams 虚拟就诊
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
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
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 使用 Microsoft Teams 设置虚拟就诊系统
ms.openlocfilehash: 37b93533aeff6b519b1f5a65cf49211464b41388
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096276"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>通过 Teams 进行虚拟就诊 - 集成到 EHR

借助 Microsoft Teams 电子健康记录 (EHR) 连接器，临床医生可轻松地直接从 EHR 系统向 Teams 中的其他提供商发起虚拟患者访视或咨询。 Microsoft Teams 基于 Microsoft 365 云进行构建，可在支持 HIPAA、HITECH 认证等合规性要求的单个中心内通过聊天、视频、语音和医疗保健工具，实现简单、安全的协作和沟通。
利用 Teams 的沟通和协作平台，临床医生可轻松解决零碎的体制问题，从而腾出更多时间提供最好的医治。 Microsoft Teams 电子健康记录 (EHR) 连接器可以实现以下操作：

- 从提供商和患者门户发起 Teams 虚拟就诊。
- 在发生连接后断开事件时，重新写入 EHR 元数据以启用自动审核和记录保留。
- 集成到现有临床医生和患者工作流中，同时允许其使用 Microsoft Teams。

  请观看此视频，了解如何从 EHR 门户管理虚拟就诊。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>开始之前

在集成 EHR 连接器之前，需要确保满足以下先决条件：

- 可以访问并使用 [Epic 的 App Orchard 商城](https://apporchard.epic.com/Gallery?id=6153)中的 Microsoft Teams 应用。

- 有效的 Microsoft Cloud for Healthcare 订阅或 Microsoft Teams EHR 连接器独立产品订阅（仅在生产测试期间强制实施）。

- 用户必须具有包含 Microsoft Teams 会议的适当 Microsoft 365 或 Office 365 许可证。

- 组织内部应采用和使用 Microsoft Teams。

- 组织必须具有 2018 年 11 月或更高版本的 Epic 版本。

- 系统必须满足所有[软件和浏览器先决条件](../../hardware-requirements-for-the-teams-app.md)。

还需要组织中以下人员的信息：

- Microsoft 365 管理员

- Epic 客户分析员

> [!Note]
> 与你的 Epic 技术专家一起查看 [Epic-Microsoft Teams 远程医疗集成指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。 请确保完成所有先决条件。 

## <a name="connector-setup"></a>连接器设置

连接器设置要求你执行以下操作：

- [启动 EHR 连接器配置门户](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [配置信息](ehr-admin.md#configuration-information)
- [批准或查看配置](ehr-admin.md#approve-or-view-configuration)
- [查看和完成配置](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[启动 EHR 连接器配置门户](#launch-the-ehr-connector-configuration-portal)

启动 EHR 连接器配置门户后，即可开始将你的医疗保健组织配置为通过 Microsoft Teams 发起虚拟就诊。 可配置一个或多个组织来测试集成。 在配置门户中配置测试和生产 URL。 在投入生产之前，请从 Epic 的测试环境测试集成。
  
- EHR 连接器配置 URL：[https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

你组织的 Microsoft 365 管理员和 Epic 客户分析员必须完成配置门户中的信息和集成步骤。 有关 Epic 配置步骤，请联系指派给贵组织的 Epic 技术专家资源。

### <a name="configuration-information"></a>[配置信息](#configuration-information)

此步骤应由 **Microsoft 365 管理员** 完成。 Microsoft 365 管理员必须启动连接器配置门户并使用 Microsoft 凭据登录才能开始配置过程。

若要完成此步骤，Microsoft 365 管理员必须从 Epic 技术专员处获得有效的快速医疗保健互操作性资源 (FHIR) 基本 URL，并获得负责批准配置的 Epic 客户分析员的用户名。 Microsoft 365 管理员必须启动连接器配置页面并使用 Microsoft 凭据登录才能开始配置过程。

- FHIR 基本 URL 是与你的服务器 FHIR API 端点对应的静态地址。 示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

- 配置审批者姓名是下一步j将负责审批配置的 Epic 客户分析员的姓名。 Epic 客户分析员是指你的组织中对 Epic 具有登录访问权限的人员。

  ![将从 EHR 连接器中的列表中选择配置审批者的姓名。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[批准或查看配置](#approve-or-view-configuration)

如果你的医疗保健组织的 Epic 客户分析员已被添加为审批者，其现在必须使用与上一步相同的 EHR 连接器 URL 来利用 Microsoft 365 凭据登录。 验证成功后，审批者必须使用其 Epic 凭据登录以验证 Epic 组织。

> [!Note]
> 你组织的 Microsoft 365 管理员和 Epic 客户分析员可以是同一个人。 在这种情况下，请将你自己的用户名添加为审批者。 你仍需要登录到 Epic 验证你的访问权限。 Epic 登录仅用于验证 FHIR 基本 URL。 Microsoft 不会通过此登录来存储凭据或访问 EHR 数据。

  ![验证和审批凭据配置。](../../media/approve-view-configuration.png)

成功登录 Epic 后，Epic 客户分析员 **必须** 审批配置。 如果配置不正确，Microsoft 365 管理员能够再次登录到 Microsoft EHR 连接器门户来修改原始配置。 

![确认已配置 EHR 连接器以及更改配置的选项。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[查看和完成配置](#review-and-finish-the-configuration)

在配置信息获得 Epic 管理员批准后，系统将为你提供用于患者和提供商启动的集成记录。 这些记录是完成 Azure 中的虚拟就诊配置所必需的。 有关更多详细信息，请参阅《Epic-Microsoft Teams 远程医疗集成指南》。

> [!Note]  
> Microsoft 365 或 Epic 客户分析员可以随时登录配置门户来查看集成记录并根据需要修改组织配置。

![将显示集成信息。](../../media/finish-configuration.png)

> [!Note]
> Epic 客户分析员必须对 Microsoft 管理员之前配置的每个 FHIR URL 完成审批过程。

![配置信息已获得批准。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>启动 Teams 虚拟就诊

完成 EHR 连接器步骤和 Epic 配置后，你的组织已准备好支持通过 Microsoft Teams 进行视频就诊。

### <a name="virtual-visit-prerequisites"></a>虚拟就诊先决条件

- 系统必须满足所有[软件和浏览器先决条件](../../hardware-requirements-for-the-teams-app.md)。

- 医疗保健组织必须已完成 Epic 组织和 Microsoft 365 组织之间的设置。

### <a name="provider-experience"></a>提供商体验

你组织的医疗保健提供商还可以从其 Epic 提供商应用程序（Hyperspace、Haiku、Canto）通过 Microsoft Teams 加入虚拟就诊。 提供商流中嵌入了“**开始虚拟就诊**”按钮。

提供商体验的主要功能：

- 提供商可以使用支持的浏览器或 Microsoft Teams 应用程序加入虚拟就诊。

- 在首次加入虚拟就诊时，提供商必须使用其 Microsoft 365 帐户进行一次性登录。

- 一次登录后，提供商将直接进入 Microsoft Teams 中的虚拟约会。（提供上必须登录到 Microsoft Teams）。

- 提供商可以查看给定预约的参与者连接和断开连接实时更新。 提供商可以查看患者何时连接到虚拟就诊。

  ![有患者的虚拟就诊提供商体验](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>患者体验

连接器支持患者通过 MyChart 网页版和移动版加入虚拟就诊。 预约时，患者可以使用“**开始虚拟就诊**”按钮从 MyChart 开始虚拟就诊。

患者体验的主要功能：

- 患者无需安装应用，可通过台式机和移动设备上的新式 Web 浏览器加入虚拟就诊。

- 患者只需单击一下即可加入虚拟就诊，无需其他帐户或登录。

- 患者无需创建 Microsoft 帐户或登录即可启动虚拟就诊。

- 患者将被置于大厅中，直到医疗保健提供商加入预约并准许患者进行虚拟就诊。

- 加入虚拟就诊之前，可在大厅中测试视频和麦克风。

  ![虚拟就诊患者体验](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商标。

### <a name="privacy-and-location-of-data"></a>隐私和数据位置

Teams 与 EHR 系统集成可优化集成和虚拟就诊流期间正在使用和存储的数据量。 该解决方案遵循“Teams 隐私”中概述的总体 Teams 隐私和数据管理原则和准则。

Microsoft Teams EHR 连接器不会存储或传输来自 EHR 系统的任何可识别个人数据或者患者或医疗保健提供商的任何健康记录。 EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在 Teams 会议设置期间使用。 EHR 用户的唯一 ID 存储在“[Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)”中所述的三个地理区域之一。 会议参与者在 Teams 中输入的所有聊天、记录和其他数据都将根据现有的存储策略进行存储。 如需了解有关 Microsoft Teams 中的数据位置的更多信息，请访问 [Teams 中的数据位置](../../location-of-data-in-teams.md)。
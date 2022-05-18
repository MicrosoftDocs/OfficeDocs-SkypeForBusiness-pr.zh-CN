---
title: 使用 Teams 的虚拟约会 - 集成到 Epic EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: 了解如何集成 Teams EHR 连接器，使组织中的医疗保健提供商能够直接从 Epic EHR 系统Teams与患者或其他提供商进行虚拟预约。
ms.openlocfilehash: abe826b1e71c37e0932404233c234282ec90b7f9
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465433"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>使用 Teams 的虚拟约会 - 集成到 Epic EHR

Microsoft Teams电子健康记录 (EHR) 连接器使临床医生可以轻松地直接从 Epic EHR 系统Microsoft Teams中启动虚拟患者预约或咨询其他提供程序。 Teams构建在Microsoft 365云之上，在支持符合 HIPAA、HITECH 认证等的单个中心内，通过聊天、视频、语音和医疗保健工具实现简单、安全的协作和通信。

Teams的沟通和协作平台使临床医生能够轻松地解决碎片系统杂乱无章的问题，以便他们能够专注于提供尽可能最好的护理。 使用Teams EHR 连接器，可以：

- 使用集成的临床工作流从 Epic EHR 系统启动Teams虚拟约会。
- 使患者能够从患者门户中或通过短信加入Teams虚拟约会。
- 支持其他方案，包括多参与者、组访问和解释器服务。
- 将有关Teams虚拟约会的元数据写回到 EHR 系统，以便在与会者连接、断开连接并启用自动审核和记录保存时记录。
- 查看与 EHR 连接的约会的消耗数据报告和可自定义呼叫质量信息。

本文介绍如何设置和配置 Teams EHR 连接器以与医疗保健组织中的 Epic 平台集成。 它还概述了 Epic EHR 系统Teams虚拟约会体验。

## <a name="before-you-begin"></a>开始之前

在开始之前，需要执行一些操作来准备集成。

### <a name="get-familiar-with-the-integration-process"></a>熟悉集成过程

查看以下信息，了解整个集成过程。

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="概述整个集成过程中的步骤的图像。":::

||||||
|---------|---------|---------|---------|---------|
|**操作**：[请求访问Teams应用](#request-access-to-the-teams-app)。 <br> **结果**：我们授权你的组织进行测试。|**操作**：创建公钥和私钥证书并将其上传到 Epic。 <br> **结果**：Epic 同步公钥证书。|**操作**：在 EHR 连接器配置门户中完成配置步骤。 <br> **结果**：收到 Epic 配置的 FDI 记录。| **操作**：请与 Epic 技术专家合作，在 Epic 中配置 FDI 记录。<br> **结果**：配置已完成。 已准备好进行测试。|**操作**：在测试环境中完成测试。<br> **结果**：完全验证流并决定迁移到生产环境。|

### <a name="request-access-to-the-teams-app"></a>请求访问Teams应用

需要请求对Teams应用的访问权限。

1. 请求在 [Epic App Orchard 市场](https://apporchard.epic.com/Gallery?id=6153)中下载Teams应用。 这样做会触发从 Epic 到 Microsoft EHR 连接器团队的请求。
1. 发出请求后，使用组织名称、租户 ID 和 Epic 技术联系人的电子邮件地址向 [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 发送电子邮件。
1. Microsoft EHR 连接器团队将在确认启用后回复电子邮件。

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>查看Epic-Microsoft Teams远程医疗集成指南

与你的 Epic 技术专家一起查看 [Epic-Microsoft Teams 远程医疗集成指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。 确保满足所有先决条件。

## <a name="prerequisites"></a>先决条件

- 只有在生产 EHR 环境) 中进行测试时，才会强制实施 Microsoft Cloud for Healthcare 的活动订阅或Microsoft Teams EHR 连接器独立产品/服务的订阅 (。
- 史诗版本 2018 年 11 月或更高版本。
- 用户具有适当的Microsoft 365或Office 365许可证，其中包括Teams会议。
- Teams在医疗保健组织中采用和使用。
- 系统满足Teams的所有[软件和浏览器要求](../../hardware-requirements-for-the-teams-app.md)。

> [!IMPORTANT]
> 在继续集成之前，请确保完成预集成步骤并满足所有先决条件。

集成步骤由组织中的以下人员执行：

- **Microsoft 365全局管理员**：负责集成的主要人员。 管理员配置连接器，根据需要启用短信 () ，并添加将批准配置的 Epic 客户分析师。
- **Epic 客户分析师**：组织中具有 Epic 登录凭据的人员。 他们批准管理员输入的配置设置，并向 Epic 提供配置记录。

Microsoft 365管理员和 Epic 客户分析师可以是同一个人。

## <a name="set-up-the-teams-ehr-connector"></a>设置Teams EHR 连接器

连接器设置要求你执行以下操作：

- [启动 EHR 连接器配置门户](#launch-the-ehr-connector-configuration-portal)
- [输入配置信息](#enter-configuration-information)
- [启用短信通知 (可选) ](#enable-sms-notifications-optional)
- [批准或查看配置](#approve-or-view-the-configuration)
- [查看和完成配置](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>启动 EHR 连接器配置门户

若要开始，Microsoft 365管理员将启动 [EHR 连接器配置门户](https://ehrconnector.teams.microsoft.com)，并使用其Microsoft 365凭据登录。

Microsoft 365管理员可以配置单个组织或多个组织来测试集成。 在配置门户中配置测试和生产 URL。 在迁移到生产环境之前，请务必测试 Epic 测试环境中的集成。

> [!NOTE]
> Microsoft 365管理员和 Epic 客户分析师必须在配置门户中完成集成步骤。 有关 Epic 配置步骤，请联系分配给组织的 Epic 技术专家。

### <a name="enter-configuration-information"></a>输入配置信息

接下来，若要设置集成，Microsoft 365管理员执行以下操作：

1. 从 Epic 技术专家处添加快速运行状况互操作性资源 (FHIR) 基本 URL，并指定环境。 根据需要配置任意数量的 FHIR 基本 URL，具体取决于组织的需求和要测试的环境。

    - FHIR 基 URL 是与服务器 FHIR API 终结点相对应的静态地址。 示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

    - 可以为测试和生产环境设置集成。 对于初始设置，我们鼓励你在迁移到生产环境之前从测试环境中配置连接器。

1. 添加 Epic 客户分析师的用户名，他们将在后续步骤中批准配置。

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="“配置”页的屏幕截图，其中显示了正在添加的审批者。" lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>启用短信通知 (可选) 

> [!NOTE]
> 短信通知目前仅在美国中可用。 我们正在努力使此功能在将来版本的Teams的其他区域中可用，并在可用时更新本文。

如果组织希望 Microsoft 为患者管理短信通知，请完成此步骤。 启用短信通知时，患者将收到计划约会的确认和提醒消息。

若要启用短信通知，Microsoft 365管理员执行以下操作：

1. 在短信通知页上，选择两个同意复选框：

    - 允许 Microsoft 代表组织向患者发送短信通知。
    - 确认你将确保与会者已同意发送和接收短信消息。
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="“短信通知”页的屏幕截图，其中显示了同意复选框和生成电话号码的选项。" lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. 在 **电话号码** 下，选择 **“生成新电话号码** ”，为组织生成电话号码。 执行此操作将启动请求和生成新电话号码的过程。 此过程可能需要长达 2 分钟才能完成。

    生成电话号码后，它将显示在屏幕上。 此号码将用于向患者发送短信确认和提醒。 该数字已预配，但尚未链接到 FHIR 基 URL。 在下一步中执行此操作。

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="显示生成的电话号码示例的屏幕截图。" lightbox="media/ehr-connector-epic-phone-number.png":::

    选择 **“完成**”，然后选择 **“下一步**”。

1. 若要将电话号码链接到 FHIR 基 URL，请在短信 **配置** 部分的 **电话号码** 下选择该号码。 针对要为其启用短信通知的每个 FHIR 基 URL 执行此操作。

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="显示如何将电话号码链接到 FHIR 基 URL 的屏幕截图。" lightbox="media/ehr-connector-epic-link-phone-number.png":::

    如果这是你第一次配置连接器，你将看到在前面的步骤中输入的 FHIR 基 URL。 相同的电话号码可以链接到多个 FHIR 基本 URL，这意味着患者将收到来自不同组织和/或部门的相同电话号码的短信通知。

1. 选择每个 FHIR 基 URL 旁边 **的短信设置**，以设置要发送给患者的短信通知的类型。

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="显示短信设置的屏幕截图。" lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **确认短信**：在 EHR 系统中计划、更新或取消预约时，会向患者发送通知。
    - **提醒短信**：通知将根据指定的时间间隔和预约的计划时间发送给患者。

    选择" **保存**"。

1. 选择 **Upload证书** 上传公钥证书。 必须仅) 每个环境的 .cer 证书上传 Base64 编码 (公钥。

    接收发送短信通知的约会信息需要公钥证书。 需要证书来验证传入信息是否来自有效源。

    当连接器用于发送短信提醒时，当在 Epic 中创建约会时，Epic 会在 HL7v2 有效负载中发送患者的电话号码。 这些数字存储在组织的地理位置中的每个约会中，并保留到约会进行为止。 若要详细了解如何配置 HL7v2 消息，请[参阅 Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。

    选择 **“下一步**”。

> [!NOTE]
> 任何时候，Microsoft 365管理员都可以更新任何短信设置。 请记住，更改设置可能会导致短信服务停机。 有关如何查看短信报表的详细信息，请[参阅Teams EHR 连接器管理员报告](ehr-admin-reports.md)。

### <a name="approve-or-view-the-configuration"></a>批准或查看配置

被添加为审批者的组织中的 Epic 客户分析师将启动 [EHR 连接器配置门户](https://ehrconnector.teams.microsoft.com)，并使用其Microsoft 365凭据登录。 成功验证后，请求审批者使用其 Epic 凭据登录以验证 Epic 组织。

> [!Note]
> 如果Microsoft 365管理员和 Epic 客户分析师是同一个人，你仍需要登录到 Epic 来验证访问权限。 Epic 登录仅用于验证 FHIR 基 URL。 Microsoft 不会使用此登录存储凭据或访问 EHR 数据。

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="“批准”或“查看配置”页的屏幕截图，其中显示了“登录和批准”选项。" lightbox="media/ehr-connector-epic-login-approve.png":::

成功登录到 Epic 后，Epic 客户分析师 **必须** 批准配置。 如果配置不正确，则Microsoft 365管理员可以登录到配置门户并更改设置。

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="“批准”或“查看配置”页的屏幕截图，其中显示了“批准”选项。" lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>查看和完成配置

在配置信息获得 Epic 管理员批准后，系统将为你提供用于患者和提供商启动的集成记录。 集成记录包括：

- 患者和提供程序记录
- 直接短信记录
- 短信配置记录
- 设备测试配置记录

可以在患者集成记录中找到设备测试的上下文令牌。 Epic 客户分析师必须向 Epic 提供这些记录，才能在 Epic 中完成虚拟约会配置。 有关详细信息，请参阅 [Epic-Microsoft Teams Telehealth 集成指南](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)。

> [!Note]  
> 任何时候，Microsoft 365或 Epic 客户分析师都可以登录到配置门户，查看集成记录并根据需要更改组织配置。

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="“审阅和完成”页的屏幕截图，其中显示了集成信息。" lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> Epic 客户分析师必须完成由Microsoft 365管理员配置的每个 FHIR 基本 URL 的审批过程。

## <a name="launch-teams-virtual-appointments"></a>启动Teams虚拟约会

完成 EHR 连接器步骤和 Epic 配置后，组织可以使用Teams支持视频约会。

### <a name="virtual-appointments-prerequisites"></a>虚拟约会先决条件

- 系统必须满足Teams的所有[软件和浏览器要求](../../hardware-requirements-for-the-teams-app.md)。

- 你已完成 Epic 组织与Microsoft 365组织之间的集成设置。

### <a name="provider-experience"></a>提供商体验

组织中的医疗保健提供商可以使用其 Epic 提供程序应用 (Hyperspace、Haiku、Canto) 中的Teams加入约会。 提供商流中嵌入了“**开始虚拟就诊**”按钮。

  ![与患者进行虚拟约会的提供程序体验。](media/ehc-provider-experience-6.png)

提供商体验的主要功能：

- 提供程序可以使用受支持的浏览器或Teams应用加入约会。

- 首次加入约会时，提供商必须使用其Microsoft 365帐户进行一次性登录。

- 一次性登录后，提供程序将直接转到Teams中的虚拟约会。  (必须将提供程序登录到Teams) 。

- 提供程序可以看到针对给定约会连接和断开连接的参与者的实时更新。 提供程序可以查看患者何时连接到约会。

> [!NOTE]
> 应下载、复制和通知医疗记录连续性或保留目的所需的会议聊天中输入的任何信息。 聊天不构成合法医疗记录或指定的记录集。 聊天中的消息基于Microsoft Teams管理员创建的设置进行存储。

### <a name="patient-experience"></a>患者体验

连接器支持患者通过短信短信、MyChart Web 和移动设备中的链接加入约会。 预约时，患者可以使用 **“开始虚拟访问**”按钮或点击短信短信中的链接，从 MyChart 开始预约。

  ![虚拟约会的病人体验。](media/ehc-virtual-visit-5.png)

患者体验的主要功能：

- 患者可以在[桌面和移动设备上加入新式 Web 浏览器的约会，而无需安装Teams应用](../browser-join.md)。
- 患者可以在加入预约之前测试其设备硬件和连接。

    :::image type="content" source="media/ehr-admin-epic-device-test.png" alt-text="显示设备测试功能的移动设备的图像。" lightbox="media/ehr-admin-epic-device-test.png":::
  
    设备测试功能：

  - 患者可以测试其扬声器、麦克风、相机和连接。
  - 患者可以完成测试调用以完全验证其配置。
  - 设备测试的结果可以发送回 EHR 系统。

- 患者只需单击一次即可加入约会，无需其他帐户或登录。

- 患者无需创建 Microsoft 帐户或登录即可启动预约。

- 患者被安置在大厅中，直到提供程序加入并接受他们。

- 患者可以在加入预约之前在大厅中测试他们的视频和麦克风。

> [!Note]
> Epic、MyChart、Haiku 和 Canto 是 Epic Systems Corporation 的商标。

## <a name="get-insight-into-virtual-appointments-usage"></a>深入了解虚拟约会使用情况

Microsoft Teams管理中心的[“虚拟访问使用情况”报告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)为管理员提供了组织中Teams虚拟约会活动的概述。 该报告显示虚拟约会的详细分析，包括从 EHR 系统进行的Teams与 EHR 集成的会议。

可以查看关键指标，例如大厅等待时间和约会持续时间。 使用此信息可深入了解使用趋势，帮助优化虚拟约会以提供更好的业务成果。

### <a name="privacy-and-location-of-data"></a>隐私和数据位置

Teams集成到 EHR 系统会优化集成和虚拟约会流期间使用和存储的数据量。 该解决方案遵循“Teams 隐私”中概述的总体 Teams 隐私和数据管理原则和准则。

Teams EHR 连接器不会从 EHR 系统存储或传输患者或医疗保健提供者的任何可识别个人数据或任何健康记录。 EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在 Teams 会议设置期间使用。

EHR 用户的唯一 ID 存储在“[Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)”中所述的三个地理区域之一。 会议参与者在Teams中共享的所有聊天、录制和其他数据都根据现有存储策略进行存储。 若要详细了解数据在Teams中的位置，请参阅[Teams中的数据位置](../../location-of-data-in-teams.md)。

## <a name="related-articles"></a>相关文章

- [Teams虚拟访问使用情况报告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR 连接器管理员报告](ehr-admin-reports.md)
- [开始医疗保健组织的Teams](teams-in-hc.md)

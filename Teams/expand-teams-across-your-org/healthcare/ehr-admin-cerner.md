---
title: 使用 Teams 进行虚拟访问 - 集成到 Cerner EHR
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
description: 了解如何集成 Teams EHR 连接器，使组织中的医疗保健提供商能够直接从 Cerner EHR 系统Teams中与患者或其他提供商进行虚拟访问。
ms.openlocfilehash: b5a5a860036b3b561d5a6e18a13b71e072998aa4
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703688"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>使用 Teams 进行虚拟访问 - 集成到 Cerner EHR

Microsoft Teams电子健康记录 (EHR) 连接器使临床医生可以轻松地从 Cerner EHR 系统发起虚拟患者就诊或咨询Microsoft Teams中的其他提供商。 Teams构建在Microsoft 365云之上，在支持符合 HIPAA、HITECH 认证等的单个中心内，通过聊天、视频、语音和医疗保健工具实现简单、安全的协作和通信。

Teams的沟通和协作平台使临床医生能够轻松地解决碎片系统杂乱无章的问题，以便他们能够专注于提供尽可能最好的护理。 使用Teams EHR 连接器，可以：

- 使用集成的临床工作流从 Cerner EHR 系统进行Teams虚拟访问。
- 使患者能够通过电子邮件或短信通知加入Teams虚拟访问。
- 查看与 EHR 连接的访问的消耗数据报告和可自定义呼叫质量信息。

本文介绍如何设置和配置 Teams EHR 连接器以与 Cerner 平台集成。 它还概述了 Cerner EHR 系统提供的Teams虚拟访问体验。

## <a name="before-you-begin"></a>开始之前

> [!NOTE]
> 在启用集成之前，请确保与 Cerner 代表交谈并查看 Cerner 集成指南。

### <a name="prerequisites"></a>先决条件

在医疗保健组织中集成Teams EHR 连接器之前，必须具有以下功能：

- Microsoft Teams EHR 连接器独立产品/服务的有效订阅 (仅在生产 EHR 环境) 中测试时强制实施。
- 用户具有适当的Microsoft 365或Office 365许可证，其中包括Teams会议。
- Teams在医疗保健组织中采用和使用。
- 系统满足Teams的所有[软件和浏览器要求](../../hardware-requirements-for-the-teams-app.md)。
- Cerner 版本 2018 年 11 月或更高版本

## <a name="set-up-the-teams-ehr-connector"></a>设置Teams EHR 连接器

连接器设置要求你执行以下操作：

- [启动 EHR 连接器配置门户](#launch-the-ehr-connector-configuration-portal)
- [输入配置信息](#enter-configuration-information)
- [启用 SMS 通知 (可选) ](#enable-sms-notifications-optional)
- [查看和完成配置](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 这些步骤必须由组织中Microsoft 365全局管理员完成。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>启动 EHR 连接器配置门户

若要开始，Microsoft 365管理员将启动 [EHR 连接器配置门户](https://ehrconnector.teams.microsoft.com)并使用其 Microsoft 凭据登录。

Microsoft 365管理员可以配置单个部门或多个部门来测试集成。 在配置门户中配置测试和生产 URL。 在迁移到生产环境之前，请务必测试 Cerner 测试环境中的集成。

### <a name="enter-configuration-information"></a>输入配置信息

接下来，若要设置集成，Microsoft 365管理员从 Cerner 添加快速运行状况互操作性资源 (FHIR) 基 URL 并指定环境。 根据需要配置任意数量的 FHIR 基本 URL，具体取决于组织的需求和要测试的环境。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Teams EHR 连接器配置门户的“配置信息”页的屏幕截图。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 基 URL 是与服务器 FHIR API 终结点相对应的静态地址。 示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

- 可以为测试和生产环境设置集成。 对于初始设置，我们鼓励你在迁移到生产环境之前从测试环境中配置连接器。

验证 FHIR 基 URL 并选择环境后，选择 **“完成**”。 然后，根据需要为其他环境添加更多 FHIR 基本 URL。

选择 **“下** 一步”转到下一步。

### <a name="enable-sms-notifications-optional"></a>启用 SMS 通知 (可选) 

如果组织希望 Microsoft 管理患者短信通知，请完成此步骤。 启用短信通知时，患者将收到计划访问的确认和提醒消息。

若要启用短信通知，Microsoft 365管理员执行以下操作：

1. 在“短信通知”页上，选中以下两个同意复选框：

    - 允许 Microsoft 代表你的组织向患者发送短信通知。
    - 确认你将确保与会者已同意发送和接收短信。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="“短信通知”页的屏幕截图，其中显示了同意复选框和生成电话号码的选项。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. 在 **电话号码** 下，选择 **“生成新电话号码** ”，为组织生成电话号码。 执行此操作将启动请求和生成新电话号码的过程。 此过程可能需要长达 2 分钟才能完成。

    生成电话号码后，它将显示在屏幕上。 此号码将用于向患者发送短信确认和提醒。 该数字已预配，但尚未链接到 FHIR 基 URL。 在下一步中执行此操作。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="显示生成的电话号码示例的屏幕截图。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    选择 **“完成**”，然后选择 **“下一步**”。

1. 若要将电话号码链接到 FHIR 基 URL，请在 **SMS 配置** 部分的 **电话号** 下选择该号码。 针对要为其启用短信通知的每个 FHIR 基 URL 执行此操作。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="显示如何将电话号码链接到 FHIR 基 URL 的屏幕截图。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    如果这是你第一次配置连接器，你将看到在前面的步骤中输入的 FHIR 基 URL。 相同的电话号码可以链接到多个 FHIR 基本 URL，这意味着患者将收到来自不同组织和/或部门的相同电话号码的短信通知。

     选择 **“下一步**”。

### <a name="review-and-finish-the-configuration"></a>查看和完成配置

你将看到用于患者和提供程序启动的集成记录。 这些记录是完成 Cerner 中的虚拟访问配置所必需的。 有关详细信息，请参阅Cerner-Microsoft Teams远程医疗集成指南。

> [!NOTE]
> 任何时候，Microsoft 365管理员都可以登录到配置门户，查看集成记录并根据需要更改配置设置。

## <a name="launch-teams-virtual-visits"></a>启动Teams虚拟访问

完成 EHR 连接器步骤和 Cerner 配置步骤后，组织可以使用Teams支持视频访问。

### <a name="virtual-visits-prerequisites"></a>虚拟访问先决条件

- 系统必须满足Teams的所有[软件和浏览器要求](../../hardware-requirements-for-the-teams-app.md)。
- 你已完成 Cerner 组织与Microsoft 365组织之间的集成设置。

### <a name="provider-experience"></a>提供商体验

组织中的医疗保健提供商可以使用 PowerChart 门户中的Teams加入访问。 提供程序必须导航到提供Teams选项的患者板。

在此处，提供程序可以查看访问信息、加入访问和发送会议链接。 一次性登录后，提供程序将直接转到Teams中的虚拟约会。

提供商体验的主要功能：

- 提供程序可以使用受支持的浏览器或Teams应用加入访问。
- 提供程序可以使用所有受支持的Teams会议功能，包括屏幕共享、自定义背景和录制。
- 提供程序可以在 PowerChart 中查看连接到访问以进行给定约会的患者的实时更新。
- 在访问期间，患者看不到提供程序信息。

> [!NOTE]
> 应下载、复制和通知医疗记录连续性或保留目的所需的会议聊天中输入的任何信息。 聊天不构成合法医疗记录或指定的记录集。 聊天中的消息基于Microsoft Teams管理员创建的设置进行存储。

### <a name="patient-experience"></a>患者体验

连接器支持患者通过短信中的链接加入访问。 预约时，患者可以通过点击短信中的链接开始就诊。

患者体验的主要功能

- 患者可以在[桌面和移动设备上加入新式 Web 浏览器的访问，而无需安装Teams应用](../browser-join.md)。
- 患者只需单击一次即可加入访问，无需其他帐户或登录。
- 患者无需创建 Microsoft 帐户或登录即可发起访问。
- 患者被安置在大厅中，直到提供程序加入并接受他们。
- 在加入访问之前，患者可以在大厅中测试他们的视频和麦克风。

## <a name="get-insight-into-virtual-visits-usage"></a>深入了解虚拟访问使用情况

Microsoft Teams管理中心的[“虚拟访问”使用情况报告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)为管理员提供了组织中Teams虚拟访问活动的概述。 该报告显示虚拟约会的详细分析，包括从 EHR 系统进行的Teams与 EHR 集成的会议。

可以查看关键指标，例如大厅等待时间和访问持续时间。 使用此信息可深入了解使用趋势，帮助优化虚拟访问以提供更好的业务成果。

## <a name="privacy-and-location-of-data"></a>隐私和数据位置

Teams集成到 EHR 系统会优化集成和虚拟访问流期间使用和存储的数据量。 该解决方案遵循“Teams 隐私”中概述的总体 Teams 隐私和数据管理原则和准则。

Teams EHR 连接器不会从 EHR 系统存储或传输患者或医疗保健提供者的任何可识别个人数据或任何健康记录。 EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，该 ID 在Teams会议设置期间使用。

EHR 用户的唯一 ID 存储在“[Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)”中所述的三个地理区域之一。 会议参与者在Teams中共享的所有聊天、录音和其他数据都根据现有存储策略进行存储。 若要详细了解数据在Teams中的位置，请参阅[Teams中的数据位置](../../location-of-data-in-teams.md)。

## <a name="related-articles"></a>相关文章

- [Teams虚拟访问使用情况报告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR 连接器管理员报告](ehr-admin-reports.md)
- [开始医疗保健组织的Teams](teams-in-hc.md)

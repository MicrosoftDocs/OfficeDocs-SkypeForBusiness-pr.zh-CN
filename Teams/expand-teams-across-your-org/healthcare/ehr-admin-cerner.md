---
title: 使用证书进行虚拟Teams - 集成到 Cerner EHR
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
description: 了解如何集成 Teams EHR 连接器，使贵组织的医疗保健提供商能够直接从 Cerner EHR 系统与 Teams 中的患者或其他提供商进行虚拟访问。
ms.openlocfilehash: 7329bd0afacfe941746374cc836203f17a9b5e57
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960132"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>使用证书进行虚拟Teams - 集成到 Cerner EHR

借助 Microsoft Teams EHR (EHR) 连接器，医生可以轻松与患者发起虚拟访问，或者直接从 Cerner EHR 系统咨询 Microsoft Teams 中的其他提供商。 基于 Microsoft 365 云Teams，借助支持符合 HIPAA、HITECH 认证等要求的单一中心内聊天、视频、语音和医疗保健工具，Teams轻松、安全地进行协作和通信。

这种通信和协作平台Teams让医生能够轻松解决碎片化系统的混乱，以便他们专注于提供最佳护理。 使用 Teams EHR 连接器，可以：

- 使用Teams工作流从 Cerner EHR 系统执行虚拟访问。
- 允许患者通过电子邮件Teams短信通知加入虚拟访问。
- 查看与 EHR 连接的访问的消耗数据报告和可自定义的呼叫质量信息。

本文介绍如何设置和配置 EHR 连接器Teams Cerner 平台集成。 此外，还概述了 Cerner EHR Teams虚拟访问体验。

## <a name="before-you-begin"></a>开始之前

> [!NOTE]
> 在启用集成之前，请确保与 Cerner 代表联系并查看 Cerner 集成指南。

### <a name="prerequisites"></a>先决条件

在医疗保健组织中Teams EHR 连接器之前，必须具有以下项：

- 仅在生产 EHR Microsoft Teams环境中测试时，才 (EHR 连接器独立产品/服务的活动) 。
- 包含Microsoft 365会议Office 365或Teams许可证。
- Teams已在你的医疗保健组织中采用和使用。
- 系统满足[所有软件和浏览器要求，Teams。](../../hardware-requirements-for-the-teams-app.md)
- Cerner 版本 2018 年 11 月或更高版本

## <a name="set-up-the-teams-ehr-connector"></a>设置 Teams EHR 连接器

连接器设置要求你执行以下操作：

- [启动 EHR 连接器配置门户](#launch-the-ehr-connector-configuration-portal)
- [输入配置信息](#enter-configuration-information)
- [启用短信通知 (可选) ](#enable-sms-notifications-optional)
- [查看和完成配置](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 这些步骤必须由组织中全局管理员Microsoft 365完成。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>启动 EHR 连接器配置门户

若要开始，Microsoft 365启动[EHR](https://ehrconnector.teams.microsoft.com)连接器配置门户，然后使用其 Microsoft 凭据登录。

你的Microsoft 365管理员可以配置单个部门或多个部门来测试集成。 在配置门户中配置测试和生产 URL。 在迁移到生产环境之前，请确保从 Cerner 测试环境测试集成。

### <a name="enter-configuration-information"></a>输入配置信息

接下来，若要设置集成，Microsoft 365管理员从 Cerner 将快速运行状况互操作性资源 (FHIR) 基 URL 并指定环境。 根据需要配置多个 FHIR 基 URL，具体取决于组织的需求和要测试的环境。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="EHR 连接器配置门户中Teams信息页的屏幕截图。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 基 URL 是对应于服务器 FHIR API 终结点的静态地址。 示例 URL 为 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`。

- 可以设置测试和生产环境的集成。 对于初始设置，建议在迁移到生产环境之前从测试环境配置连接器。

验证 FHIR 基 URL 并选择环境后，选择"完成 **"。** 然后，根据需要为其他环境添加更多 FHIR 基 URL。

选择 **"下** 一步"转到下一步。

### <a name="enable-sms-notifications-optional"></a>启用短信通知 (可选) 

如果你的组织希望 Microsoft 管理患者短信通知，请完成此步骤。 启用短信通知时，患者将收到有关计划虚拟访问的确认和提醒消息。

若要启用短信通知，Microsoft 365管理员执行以下操作：

1. 在"短信通知"页面上，选中以下两个许可复选框：

    - 允许 Microsoft 代表组织向患者发送短信通知。
    - 确认你将确保与会者已同意发送和接收短信。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="短信通知页面的屏幕截图，显示同意复选框和生成电话号码的选项。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. 在 **"电话号码"** 下，选择"生成 **新** 电话号码"，为组织生成电话号码。 执行此操作会启动请求并生成新电话号码的过程。 此过程最多可能需要 2 分钟才能完成。

    生成电话号码后，它将显示在屏幕上。 此号码将用于向患者发送短信确认和提醒。 该号码已预配，但尚未链接到 FHIR 基 URL。 下一步中会执行该步骤。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="显示已生成的电话号码的示例的屏幕截图。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    选择 **"完成**"，然后选择"下 **一步"。**

1. 若要将电话号码链接到 FHIR 基 URL，请在 **电话"短信****配置"** 部分中选择该号码。 针对要启用短信通知的每个 FHIR 基 URL 执行此操作。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="显示如何将电话号码链接到 FHIR 基 URL 的屏幕截图。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    如果这是第一次配置连接器，则会看到在上一步中输入的 FHIR 基 URL。 同一电话号码可以链接到多个 FHIR 基 URL，这意味着患者将收到来自不同组织和/或部门相同电话号码的短信通知。

     选择"下 **一步"。**

### <a name="review-and-finish-the-configuration"></a>查看和完成配置

你将看到患者和提供者启动的集成记录。 这些记录是完成 Cerner 中的虚拟访问配置所必需的。 有关详细信息，请参阅远程Cerner-Microsoft Teams集成指南。

> [!NOTE]
> 管理员随时Microsoft 365登录配置门户，查看集成记录并根据需要更改配置设置。

## <a name="launch-teams-virtual-visits"></a>启动 Teams 虚拟就诊

完成 EHR 连接器步骤和 Cerner 配置步骤后，组织已准备好使用 Teams 支持视频访问。

### <a name="virtual-visits-prerequisites"></a>虚拟访问先决条件

- 系统必须满足所有[软件和浏览器要求，Teams。](../../hardware-requirements-for-the-teams-app.md)
- 已完成 Cerner 组织与组织之间的Microsoft 365设置。

### <a name="provider-experience"></a>提供商体验

您的组织中的医疗保健提供商可以使用 PowerChart 门户Teams虚拟访问。 提供商必须导航到提供"Teams"选项的"患者委员会"。

提供商可以从中查看虚拟访问信息、加入虚拟访问以及发送会议链接。 一次登录后，提供程序将直接进入 Teams 中的虚拟Teams。

提供商体验的主要功能：

- 提供程序可以使用支持的浏览器或应用加入虚拟Teams访问。
- 提供商可以使用所有受支持的Teams功能，包括屏幕共享、自定义背景和录制。
- 提供商可以在 PowerChart 中查看连接到虚拟访问的给定预约患者实时更新。
- 在虚拟访问期间，患者看不到提供商信息。

### <a name="patient-experience"></a>患者体验

连接器支持患者通过短信中的链接加入虚拟访问。 预约时，患者可以通过点击短信中的链接开始虚拟访问。

患者体验的主要功能

- 患者可以从桌面和移动设备上的现代 Web 浏览器加入虚拟访问，而无需安装 Teams[应用](../mobile-browser-join.md)。
- 患者只需单击一次即可加入虚拟访问，无需其他帐户或登录。
- 患者无需创建 Microsoft 帐户或登录即可启动虚拟就诊。
- 病人被安排在大厅中，直到提供商加入预约并准许他们进行虚拟访问。
- 在加入虚拟访问之前，患者可以在大厅中测试视频和麦克风。

## <a name="privacy-and-location-of-data"></a>隐私和数据位置

Teams EHR 系统集成可以优化集成和虚拟访问流期间使用和存储的数据量。 该解决方案遵循“Teams 隐私”中概述的总体 Teams 隐私和数据管理原则和准则。

EHR 连接器Teams EHR 系统不存储或传输任何可识别的个人数据或患者或医疗保健提供者的任何健康记录。 EHR 连接器存储的唯一数据是 EHR 用户的唯一 ID，Teams设置期间使用。

EHR 用户的唯一 ID 存储在“[Microsoft 365 客户数据的存储位置](/microsoft-365/enterprise/o365-data-locations)”中所述的三个地理区域之一。 会议参与者在会议Teams共享的所有聊天、录制和其他数据都根据现有存储策略进行存储。 若要了解有关数据在数据中的位置Teams，[请参阅数据在](../../location-of-data-in-teams.md)Teams 中的位置。

## <a name="related-articles"></a>相关文章

- [Teams EHR 连接器管理员报告](ehr-admin-reports.md)
- [医疗保健Teams入门](teams-in-hc.md)

---
title: 规划运营商连接会议
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解运营商连接会议，例如要求和部署规划。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257502"
---
# <a name="plan-for-operator-connect-conferencing"></a>规划运营商连接会议

Microsoft 音频会议提供使用公用电话交换网和 PSTN 电话拨入 (拨入) 呼叫的能力。  参与者Microsoft Teams仅音频会议网桥加入会议。

借助连接会议功能，组织可以使用来自第三方运营商的电话号码加入Microsoft Teams会议。 如果你的当前接线员是 Microsoft 接线员连接计划的一部分，你可以将你的接线员的电话号码添加到音频会议网桥，并使用它们加入会议。

如果没有连接会议功能，组织只能将 Microsoft 提供的电话号码用于其音频会议网桥。

>[!NOTE]
>本文中引用属于 Microsoft 接线员连接的电话号码提供商为"接线员"。
>
>若要了解操作员是否参与 Microsoft Operator 连接计划，请参阅 Microsoft 365 Operator[连接 目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

本文介绍运营商连接会议：

- [优势](#benefits)
- [许可要求和计费](#licensing-requirements-and-billing)
- [有关 Microsoft 音频会议的其他信息](#additional-information-on-microsoft-audio-conferencing)

有关为会议配置连接的信息，请参阅[配置连接会议"](operator-connect-conferencing-configure.md)。

如果你组织的一些用户需要向 PSTN 电话号码进行外部呼叫，你仍然需要呼叫计划。 若要了解如何使用第三方运营商进行外部 PSTN 连接，请参阅[规划操作员](operator-connect-plan.md)连接。

## <a name="benefits"></a>优点

运营商连接会议提供以下优势：

- **在运营商和 Microsoft 之间灵活分配电话号码。** 将来自 Microsoft 和您的运营商的电话号码 (仅与 Microsoft 音频会议标准版订阅一起使用) ，或者仅将接线员 (的电话号码与接线员 连接 会议许可证) 。

- **操作员管理的基础结构。**  操作员管理 SDC (边界控制器) 与 Microsoft 的互连，从而节省额外的硬件购买和管理费用。

- **更快、更轻松地部署。**  从管理中心快速连接到接线员并将电话号码分配给Teams网桥。

- **增强的支持和可靠性。**  操作员提供技术支持和共享服务级别协议来改善服务支持，由 Azure 提供支持的直接对等互连可创建一对一网络连接以提高可靠性。

当连接时，运营商电话会议可能是适合你的组织的解决方案：

- 您希望 **保留与现有** 电话号码提供商的合同

- 您希望扩展 **现有** Microsoft 音频会议网桥的全球覆盖范围

- 您希望从 **新的电话号码提供商获取** 音频会议的电话号码

- **Microsoft 音频会议在你的地理位置不可用**

- 您希望 **利用采用** 按分钟付费模式的音频会议服务的运营商，例如，使用免费号码和从 Teams 会议拨打出站呼叫到订阅中未包含的国家/地区的电话号码

## <a name="licensing-requirements-and-billing"></a>许可要求和计费

需要接线员连接号码才能加入他们组织的会议的用户必须分配有 Microsoft 音频会议标准订阅或 Microsoft 连接 会议许可证。

### <a name="audio-conferencing-standard-subscription"></a>音频会议标准订阅

Microsoft Audio Conferencing Standard 订阅可以购买为 Microsoft Teams 许可证的附加内容，并且也包含在 Microsoft 365 E5 和 Office 365 E5 订阅中。

音频会议标准版订阅允许订阅者使用 Microsoft 提供的电话号码，并扩展其音频会议网桥以及运营商提供的电话号码。 订阅者还可以决定从会议Teams通过 Microsoft 路由的出站呼叫，以及通过操作员路由的呼叫。

有关详细信息，请参阅 [**配置运营商连接会议。**](operator-connect-conferencing-configure.md)

### <a name="operator-connect-conferencing-license"></a>运营商连接会议许可证

可以将 Microsoft 连接会议许可证作为附加内容获取到 Microsoft Teams 许可证。

接线员连接会议许可证允许订阅者使用来自运营商的电话号码，但它不包括来自 Microsoft 的电话号码。 来自会议的所有Teams必须通过运营商路由。

有关详细信息，请参阅 [**配置运营商连接会议。**](operator-connect-conferencing-configure.md)

>[!Note]
>会议参与者不需要音频会议标准订阅许可证或接线员 连接 会议许可证来加入由具有"电话连接"功能的用户组织的会议。

使用接线连接会议，Microsoft 根据组织使用的音频会议许可证的类型、Microsoft 音频会议或运营商 连接 会议以及 Microsoft 提供的任何电话号码向组织进行帐单。

你的运营商向组织支付使用运营商连接他们提供的会议号码的费用。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>有关 Microsoft 音频会议的其他信息

Microsoft 音频会议允许参与者Microsoft Teams PSTN 电话号码拨入或拨打 PSTN 电话号码来加入会议。 有关组织可用的 Microsoft 音频会议功能的信息，请参阅音频[会议](audio-conferencing-in-office-365.md)Microsoft 365。

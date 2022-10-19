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
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解运营商连接会议，例如部署的要求和规划。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e1c363c66028a9e8611fa38179585e1e073c54b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583978"
---
# <a name="plan-for-operator-connect-conferencing"></a>规划运营商连接会议

Microsoft 音频会议提供使用公共交换电话网络 (PSTN) 电话号码拨入会议和从会议中拨出的功能。  参与者使用仅音频会议网桥加入 Microsoft Teams 会议。

使用运营商连接会议功能，组织可以使用第三方运营商的电话号码加入 Microsoft Teams 会议。 如果当前操作员是 Microsoft Operator Connect 计划的一部分，则可以将操作员的电话号码添加到音频会议网桥，并使用它们加入会议。

如果没有运营商连接会议功能，组织只能将 Microsoft 提供的电话号码用于其音频会议网桥。

>[!NOTE]
>本文将属于 Microsoft Operator Connect 计划的电话号码提供程序引用为“操作员”。
>
>若要查看操作员是否参与 Microsoft Operator Connect 计划，请参阅 [Microsoft 365 运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

本文介绍运营商连接会议：

- [优势](#benefits)
- [许可要求和计费](#licensing-requirements-and-billing)
- [有关 Microsoft 音频会议的其他信息](#additional-information-on-microsoft-audio-conferencing)

有关配置运营商连接会议的信息，请参阅[配置运营商连接会议](operator-connect-conferencing-configure.md)。

如果组织的某些用户需要对 PSTN 电话号码进行外部呼叫，则仍需要呼叫计划。 若要了解如何使用第三方运算符进行外部 PSTN 连接，请参阅 [Plan for Operator Connect](operator-connect-plan.md)。

## <a name="benefits"></a>优点

运营商连接会议提供以下优势：

- **在运营商和 Microsoft 之间灵活分配电话号码。** 将 Microsoft 和操作员 (的电话号码与仅) 的 Microsoft 音频会议标准版订阅一起使用，或者仅将运营商 (的电话号码与仅) 运营商连接会议许可证一起使用。

- **操作员管理的基础结构。** 操作员管理会话边框控制器 (SBC) 和与 Microsoft 的互连，从而使你免于额外的硬件购买和管理。

- **更快、更轻松的部署。** 快速连接到操作员，并将电话号码从 Teams 管理中心分配到音频会议网桥。

- **增强了支持和可靠性。** 操作员提供技术支持和共享服务级别协议来改进服务支持，而由 Azure 提供支持的直接对等互连会创建一对一网络连接，以提高可靠性。

运营商连接会议可能是组织在以下情况下的正确解决方案：

- 你希望保留与现有电话号码提供商 **的合同**

- 你希望扩大现有 Microsoft 音频会议网桥的 **全局覆盖范围**

- 您希望从新的电话号码提供程序 **获取音频会议的电话号码**

- **Microsoft 音频会议在地理位置不可用**

- 你想要 **利用具有按分钟付费模式的音频会议服务的运营商**，例如使用免费号码，以及从 Teams 会议到订阅中未包含的国家/地区的电话号码进行出站呼叫

## <a name="licensing-requirements-and-billing"></a>许可要求和计费

需要运营商连接会议号码才能加入其组织的会议的用户必须具有 Microsoft 音频会议标准订阅或 Microsoft 运营商连接会议 许可证。

### <a name="audio-conferencing-standard-subscription"></a>音频会议标准订阅

Microsoft Audio Conferencing Standard 订阅可以作为 Microsoft Teams 许可证的加载项购买，并且也包含在Microsoft 365 E5和Office 365 E5订阅中。

音频会议标准订阅允许订阅者使用来自 Microsoft 的电话号码，并使用操作员提供的数字扩展其音频会议网桥。 订阅者还可以决定要通过 Microsoft 路由哪些 Teams 会议的出站呼叫，以及通过运营商路由哪些呼叫。

有关详细信息，请参阅配置 [**运营商连接会议**](operator-connect-conferencing-configure.md)。

### <a name="operator-connect-conferencing-license"></a>运营商连接会议许可证

Microsoft 运营商连接会议许可证可以作为 Microsoft Teams 许可证的加载项获取。

运营商连接会议许可证允许订阅者使用运营商提供的电话号码，但不包括来自 Microsoft 的电话号码。 Teams 会议的所有出站呼叫都必须通过操作员路由。

有关详细信息，请参阅配置 [**运营商连接会议**](operator-connect-conferencing-configure.md)。

>[!Note]
>会议参与者不需要音频会议标准订阅许可证或运营商连接会议许可证才能加入由具有运营商连接会议功能的用户组织的会议。

使用运营商连接会议，Microsoft 会根据组织使用的音频会议许可证类型、Microsoft 音频会议或运营商连接会议以及 Microsoft 提供的任何电话号码的使用向组织收费。

操作员向组织索要使用他们提供的运营商连接会议号码。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>有关 Microsoft 音频会议的其他信息

Microsoft 音频会议允许参与者通过使用 PSTN 电话号码拨入或拨出 PSTN 电话号码加入 Microsoft Teams 会议。 有关组织可用的 Microsoft 音频会议功能的详细信息，请参阅 [Microsoft 365 中的音频会议](audio-conferencing-in-office-365.md)。

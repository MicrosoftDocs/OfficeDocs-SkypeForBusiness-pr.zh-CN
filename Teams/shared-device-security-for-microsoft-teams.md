---
title: Microsoft Teams 安全指南：在共享计算机上安全地使用 Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 在工作场所共享计算机上使用 Microsoft Teams 的安全指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc886b2783d1398a85e00927a224968d65a9539b
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646003"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>在共享计算机上安全使用 Microsoft Teams

对任何使用设备管理功能、设备运行状况检查、策略执行、设备级加密及其他安全功能的客户端设备，*建议* 企业尽可能采用零信任方案。

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="零信任图片蓝色圆圈中，分别显示的是显式验证、最少特权，还有假定泄露（即零信任的核心原则）。":::

管理员可通过 *始终* 验证、最少特权和假设泄露来创建严格的安全条件（执行这些标准可将用户和数据面临的风险降到最低）。

> [!TIP]
> 要深入了解零信任原则，请查看[这些视频](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)。

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>在共享计算机上安全使用 Microsoft Teams 的提示

尽管在某些场景中可能无法执行，但安全管理员在共享计算机或非托管设备上使用 Teams 时，仍应尽量严格按照指南进行操作。

应尽快根据指南制定计划。

1. 利用操作系统平台的安全功能。
    1. 确保操作系统已配置为自动安装来自操作系统提供商的更新（ Microsoft 系统可通过 [**Windows 更新**](https://support.microsoft.com/help/12373/windows-update-faq)进行设置）。 
    1. 确保启用任何设备加密功能，如 [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview)，并且用于访问设备的密钥受到保护。 请注意，大多数新式 [**Windows 10设备支持 bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。 
    1. 使用 [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 等提供的防病毒功能。
    1. 强烈建议每个用户用[单独的用户帐户](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)使用同一系统。
    1. *不要* 对非管理功能授予或使用管理员特权（例如浏览网页、启动 Teams 等）。

如果无法满足上述指导，我们建议使用其他浏览器安全最佳做法：

1. 应用浏览器安全功能。
    1. 启用隐私浏览模式，尽量减少保留在磁盘上的数据与历史记录。 例如，[在 Microsoft Edge 中以 inPrivate 模式进行浏览](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)， [在Google Chrome 中以无痕模式进行浏览](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)，或使用其他浏览器的隐私浏览功能。 
    1. 建议将系统行为设置为 *默认使用* 隐私浏览模式。 

2. 浏览到并使用 [Teams web 应用](https://teams.microsoft.com) （或称为 *web* 客户端），而不用可下载的 Teams 客户端。

3. 使用完共享系统后，您必须： 
    1. [注销 Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。
    1. 关闭所有浏览器选项卡和窗口。
    1. 注销此设备。

上述项目不是涵盖所有情况的最佳做法或安全控制措施的综合列表，并且可能在你的环境中执行额外的操作（例如，如果你 [Office 365 ATP 计划 1 或 2](/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)，安全管理员可以选择使用 Teams 的安全链接和安全附件）。但是，这些步骤是构建有关从共享设备使用 Teams 的指南的起点。

## <a name="more-information"></a>详细信息

[Configuration Manager 中的 Bitlocker](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Windows 10 in Intune 版 Bitlocker](/mem/intune/protect/encrypt-devices)

[Intune 端点安全性](/mem/intune/protect/endpoint-security)

在 Windows 安全中心[启用](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender 防病毒并[运行扫描](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Microsoft Defender 安全中心文章](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Teams web 客户端/teams web 应用](./get-clients.md#web-client)

[安全性与 Microsoft Teams](./teams-security-guide.md)

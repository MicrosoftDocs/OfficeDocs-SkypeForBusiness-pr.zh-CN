---
title: Microsoft Teams 安全指南
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
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868691"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>在共享计算机上安全使用 Microsoft Teams

对任何使用设备管理功能、设备运行状况检查、策略执行、设备级加密及其他安全功能的客户端设备，*建议*企业尽可能采用零信任方案。

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="零信任图片蓝色圆圈中，分别显示的是显式验证、最少特权，还有假定泄露（即零信任的核心原则）。":::

管理员可通过*始终*验证、最少特权和假设泄露来创建严格的安全条件（执行这些标准可将用户和数据面临的风险降到最低）。

> [!TIP]
> 要深入了解零信任原则，请查看[这些视频](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)。

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>在共享计算机上安全使用 Microsoft Teams 的提示

尽管在某些场景中可能无法执行，但安全管理员在共享计算机或非托管设备上使用 Teams 时，仍应尽量严格按照指南进行操作。

应尽快根据指南制定计划。

1. 利用操作系统平台的安全功能。
    1. 确保操作系统已配置为自动安装来自操作系统提供商的更新（ Microsoft 系统可通过 [**Windows 更新**](https://support.microsoft.com/help/12373/windows-update-faq)进行设置）。 
    2. 确保已启用设备加密功能，如 [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) 等，并确保访问设备的密匙也受到保护。  请注意，大多数新式[**Windows 10 设备支持 bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。 
    1. 使用 [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 等提供的防病毒功能。
    1. 强烈建议每个用户用[单独的用户帐户](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)使用同一系统。
    1. *不要*对非管理功能授予或使用管理员特权（例如浏览网页、启动 Teams 等）。

2. 利用浏览器的安全功能。
    1. 启用隐私浏览模式，尽量减少保留在磁盘上的数据与历史记录。 例如，[在 Microsoft Edge 中以 inPrivate 模式进行浏览](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)， [在Google Chrome 中以无痕模式进行浏览](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)，或使用其他浏览器的隐私浏览功能。 
    1. 建议将系统行为设置为*默认使用*隐私浏览模式。 

3. 浏览到并使用 [Teams web 应用](https://teams.microsoft.com) （或称为 *web* 客户端），而不用可下载的 Teams 客户端。

4. 使用完共享系统后，您必须： 
    1. [注销 Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。
    1. 关闭所有浏览器选项卡和窗口。
    1. 注销此设备。

上述建议不涵盖所有情况下的最佳实践或安全控制方案，不同环境中您也可能采取其他措施，（例如，如果您购买了 [Office 365 ATP 计划 1 或 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) ，安全管理员可能会选择使用 Teams 中的安全链接或安全附件）。 但这些步骤仍可帮助您开始创建在共享设备上使用 Teams 的安全指南。

## <a name="more-information"></a>详细信息

[Configuration Manager 中的 Bitlocker](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Windows 10 in Intune 版 Bitlocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[Intune 端点安全性](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

在 Windows 安全中心[启用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender 防病毒并[运行扫描](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Microsoft Defender 安全中心文章](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Teams web 客户端/teams web 应用](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[安全性与 Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide)

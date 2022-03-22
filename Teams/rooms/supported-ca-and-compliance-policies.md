---
title: 支持的条件访问和 Intune 设备符合性策略Microsoft Teams 会议室
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解受支持的推荐条件访问和 Intune 设备符合性策略，Microsoft Teams 会议室。
ms.openlocfilehash: f3b115430779324a260232ce45ba125859abdde8
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689061"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>支持的条件访问和 Intune 设备符合性策略Microsoft Teams 会议室

本文提供受支持的条件访问和 Intune 设备符合性策略，Microsoft Teams 会议室。 有关最佳做法和示例策略，请参阅条件[访问和 Intune 符合性最佳做法Microsoft Teams 会议室](conditional-access-and-compliance-for-devices.md)。

> [!NOTE]
> Teams 会议室必须已部署到要为其分配条件访问策略的设备上。 如果尚未部署Teams 会议室，请参阅为会议室和共享设备创建资源[](with-office-365.md)Teams和在 [Android](../devices/collab-bar-deploy.md) Microsoft Teams 会议室部署帐户了解详细信息。

## <a name="supported-conditional-access-policies"></a>支持的条件访问策略  

以下列表包括受支持的条件访问策略，Teams 会议室 Android Windows上：

| 分配 | Windows | Android |
|------------|---------|---------|
| 用户或工作负荷标识 |支持 | 支持 |
|云应用或操作 | 支持 <br><br> Teams 会议室模式时，需要访问以下三个云Teams：Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams | 支持 <br><br> Teams 会议室模式时，需要访问以下三个云Teams：Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams |
|**条件**| --- | --- |
| 用户风险 | 支持 | 支持 |
| 登录风险 | 支持 | 支持 |
| 设备平台 | 支持 | 支持 |
| Locations | 支持 | 支持 |
|客户端应用 |不支持| 不支持 |
|筛选设备 | 支持 | 支持 |
|**授予**| --- | --- |
| 阻止访问 | 支持 | 支持 |
| 授予访问权限 | 支持 | 支持 | 
| 要求多重身份验证 | 不支持 | 不支持 |
| 要求将设备标记为合规 | 支持 | 支持 |
|要求混合Azure AD设备 | 不支持 | 不支持 |
|需要批准的客户端应用 | 不支持 | 不支持 |
| 需要应用保护策略 | 不支持 |不支持 |
| 要求更改密码 | 不支持 | 不支持 |

> [!NOTE]
> Skype for Business Online 已停用且不受支持。 Skype for Business基于设备符合性的条件访问策略不支持联机云应用。

> [!NOTE]
> Microsoft Teams 会议室Windows必须满足以下要求，以支持设备符合性授予控制：
>
> - Microsoft Teams 会议室应用程序 4.8.19.0 或以上
> - Windows 10版本 20H2 及 (10.0.19042) 

## <a name="supported-device-compliance-policies"></a>支持的设备符合性策略 

Microsoft Teams 会议室 Android Windows Teams 会议室 支持不同的设备符合性策略。

#### <a name="teams-rooms-on-windows"></a>[Teams 会议室上Windows](#tab/mtr-w)

下面是设备符合性设置表，以及用于设备符合性设置Teams 会议室。  

|策略 | 可用性 | 注释|
|---------|-------------|-------|
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|需要 BitLocker| 支持 | 仅在首次在 Teams 会议室 上启用 BitLocker 时Teams 会议室。 |
|要求在设备上启用安全启动 |支持 |安全启动是安全启动Teams 会议室。 |
|需要代码完整性 |支持  | 代码完整性已是应用程序Teams 会议室。 |
| [**设备属性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|操作系统版本 (最小、最大)  |不支持 | Teams 会议室更新到较新版本的 Windows 并且在此处设置值可能会阻止 OS 更新后成功登录。|
|移动设备的 OS 版本 (最低、最大)  | 不支持。 | 不适用 |
| 有效的操作系统版本 | 不支持 | 不适用 |
| [**配置管理器符合性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| 要求配置管理器符合设备要求 | 支持 |  不适用 |
| [**系统安全性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| 所有密码策略 | 不支持 | 密码策略可以防止本地Skype帐户自动登录。 |
| 要求对设备上数据存储进行加密。 | 支持  | 仅在首次在云中启用数据存储加密时Teams 会议室。 |
| 防火墙 | 支持 | 防火墙已是应用程序Teams 会议室 |
| 受信任的平台模块 (TPM)  | 支持 | 受信任的平台模块 (TPM) 已是用户Teams 会议室。 |
| 防病毒 | 支持 | 防病毒 (Windows Defender) 已是应用程序Teams 会议室。 |
| 反spyware | 支持 | 反spyware (Windows Defender) 已是应用程序Teams 会议室。 |
| Microsoft Defender 反恶意软件 | 支持 | Microsoft Defender 反恶意软件已是进行安全Teams 会议室。 |
| Microsoft Defender 反恶意软件最低版本 | 不支持。 | Teams 会议室自动更新此组件，因此无需设置符合性策略。|
| Microsoft Defender 反恶意软件安全智能
最新 | 支持 | 验证 Microsoft Defender 反恶意软件已是用户Teams 会议室。 |
| 实时保护 | 支持 | 实时保护已是进行实时保护Teams 会议室。 |
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| 要求设备处于或处于计算机风险评分之下。 | 支持 |  不适用 |

#### <a name="teams-rooms-on-android"></a>[Teams 会议室 Android 上的应用](#tab/mtr-a)

下面是设备符合性设置表，以及用于设备符合性设置Teams 会议室。  

| 策略 | 可用性 | 注释 |
|---------|-------------|-------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| 要求设备处于或处于计算机风险评分之下 | 不支持 |  不适用 |
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| 使用设备管理员管理的设备 | 不支持。 | Teams Android 设备由设备管理
管理员。 |
| 根设备 | 支持 |  不适用 |
| 要求设备处于或处于设备威胁级别 | 不支持 |  不适用 |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services 已配置 | 不支持 | Android 设备上未Teams Google play。 |
| 最新安全提供程序 | 不支持 | Android 设备上未Teams Google play。 |
| 应用威胁扫描 | 不支持 | Android 设备上未Teams Google play。 |
| SafetyNet 设备证明 | 不支持 | Android 设备上未Teams Google play。|
| [**设备属性**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| 操作系统版本 (最小、最大)  | 支持 |  不适用 |
[**系统安全性**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| 要求对设备上数据存储进行加密。 |支持 |  不适用 |
[**设备安全性**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 阻止来自未知源的应用 | 不支持 | 仅Teams管理员安装应用或 OEM 工具 |
| 公司门户应用运行时完整性 | 支持 |  不适用|
| 受限制的应用 | 不支持 |  不适用 |
| 在设备上阻止 USB 调试 | 支持 |  不适用|
[**所有 Android 设备*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|需要密码前处于非活动状态的最大分钟数 | 不支持 |  不适用 |
| 需要密码才能解锁移动设备 | 不支持 | 不适用 |
| [**Android 10 及更高版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 及更早版本或 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|所需的密码类型 |不支持 | 不适用|

---

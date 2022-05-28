---
title: 支持的条件访问和Intune设备符合性策略Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解支持和推荐的条件访问和Intune设备符合性策略，以便Microsoft Teams 会议室。
ms.openlocfilehash: 8492f94106423498c7e301e48c8f4d046d569674
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761464"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms-and-teams-android-devices"></a>支持的条件访问和Intune设备符合性策略，适用于Microsoft Teams 会议室和Teams Android设备

本文为Microsoft Teams 会议室提供支持的条件访问和Intune设备符合性策略。 有关最佳做法和示例策略，请[参阅条件访问和Intune Microsoft Teams 会议室符合性最佳做法](conditional-access-and-compliance-for-devices.md)。

> [!NOTE]
> Teams 会议室必须已部署在要将条件访问策略分配到的设备上。 如果尚未部署Teams 会议室，请参阅[为会议室和共享Teams设备创建资源帐户](with-office-365.md)，并在[Android上部署Microsoft Teams 会议室](../devices/collab-bar-deploy.md)，了解详细信息。

## <a name="supported-conditional-access-policies"></a>支持的条件访问策略  

以下列表包括支持的条件访问策略，用于Windows和Android上的Teams 会议室，以及Teams面板、手机和显示器上的策略。

| 分配                               | Windows上的Teams 会议室                                                                                                                                                                              | Android和面板上的Teams 会议室                                                                                                                                                                              | Teams手机和显示器                                                                                                                                                    |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 用户或工作负荷标识              | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 云应用或操作                    | 支持 <br><br> Teams 会议室仅限Teams模式时，需要访问以下三个云应用：Office 365 Exchange Online、Office 365 SharePoint联机和Microsoft Teams | 支持 <br><br> Teams 会议室仅限Teams模式时，需要访问以下三个云应用：Office 365 Exchange Online、Office 365 SharePoint联机和Microsoft Teams | 支持<br><br>Teams Android设备需要访问以下三个云应用：Office 365 Exchange Online、Office 365 SharePoint联机和Microsoft Teams |
| **条件**                           | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| 用户风险                                | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 登录风险                             | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 设备平台                         | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| Locations                                | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 客户端应用                              | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                        |
| 设备筛选器                       | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| **授予**                                | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| 阻止访问                             | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 授予访问权限                             | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            |                                                                                                                                                                      |
| 需要多重身份验证      | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 支持                                                                                                                                                            |
| 要求将设备标记为合规 | 支持                                                                                                                                                                            | 支持                                                                                                                                                                            | 支持                                                                                                                                                            |
| 需要已加入混合 Azure AD 的设备    | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                        |
| 需要已批准的客户端应用              | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                        |
| 需要应用保护策略            | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                        |
| 要求更改密码                  | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                                        | 不支持                                                                                                                                                        |

> [!NOTE]
> Skype for Business联机已停用，不受支持。 Skype for Business基于设备符合性的条件访问策略不支持联机云应用。

> [!NOTE]
> Windows上的Microsoft Teams 会议室必须满足以下要求才能支持设备合规性授予控制：
>
> - Microsoft Teams 会议室应用程序 4.8.19.0 或更高版本
> - Windows 10版本 20H2 及更高版本 (10.0.19042) 

## <a name="supported-device-compliance-policies"></a>支持的设备符合性策略 

Android上Microsoft Teams 会议室Windows和Teams 会议室支持不同的设备符合性策略。

#### <a name="teams-rooms-on-windows"></a>[Windows上的Teams 会议室](#tab/mtr-w)

下表列出了设备符合性设置及其与Teams 会议室配合使用的建议。  

| 策略                                                                                                                      | 可用性   | 注释                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------------------------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-windows#device-health)                                     | --             | --                                                                                                                                          |
| 需要 BitLocker                                                                                                           | 支持      | 仅当首次在 Teams 会议室 上启用 BitLocker 时才使用。                                                                                |
| 要求在设备上启用安全启动                                                                             | 支持      | 安全启动是Teams 会议室的要求。                                                                                              |
| 要求代码完整性                                                                                                      | 支持      | 代码完整性已是Teams 会议室的要求。                                                                                    |
| [**设备属性**](/mem/intune/protect/compliance-policy-create-windows#device-properties)                             | --             | --                                                                                                                                          |
| 操作系统版本 (最小、最大)                                                                                  | 不支持  | Teams 会议室自动更新到较新版本的Windows，在此处设置值可能会阻止操作系统更新后成功登录。 |
| 移动设备的 OS 版本 (最小、最大)                                                                             | 不支持。 |                                                                                                                                             |
| 有效的操作系统生成                                                                                               | 不支持  |                                                                                                                                             |
| [**Configuration Manager符合性**](/mem/intune/protect/compliance-policy-create-windows#device-properties)              | --             | --                                                                                                                                          |
| 要求设备符合Configuration Manager                                                                        | 支持      |                                                                                                                                             |
| [**系统安全性**](/mem/intune/protect/compliance-policy-create-windows#system-security)                                 | --             | --                                                                                                                                          |
| 所有密码策略                                                                                                       | 不支持  | 密码策略可以阻止本地Skype帐户自动登录。                                                        |
| 需要对设备上的数据存储进行加密。                                                                               | 支持      | 仅当首次在Teams 会议室上启用了数据存储加密时才使用。                                                               |
| 防火墙                                                                                                                    | 支持      | 防火墙已是Teams 会议室的要求                                                                                           |
| 受信任的平台模块 (TPM)                                                                                                | 支持      | 受信任的平台模块 (TPM) 已是Teams 会议室的要求。                                                                     |
| 防病毒                                                                                                                   | 支持      | 防病毒 (Windows Defender) 已是Teams 会议室的要求。                                                                      |
| 反间谍软件                                                                                                                 | 支持      | 反软件 (Windows Defender) 已是Teams 会议室的要求。                                                                    |
| Microsoft Defender 反恶意软件                                                                                              | 支持      | Microsoft Defender 反恶意软件已是Teams 会议室的要求。                                                                    |
| Microsoft Defender 反恶意软件最低版本                                                                              | 不支持。 | Teams 会议室自动更新此组件，因此无需设置符合性策略。                                             |
| Microsoft Defender 反恶意软件安全智能最新                                                             | 支持      | 验证 Microsoft Defender 反恶意软件是否已是Teams 会议室的要求。                                                      |
| 实时保护                                                                                                        | 支持      | 实时保护已是Teams 会议室的要求。                                                                            |
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-windows#microsoft-defender-for-endpoint) | --             | --                                                                                                                                          |
| 要求设备处于或低于计算机风险分数。                                                                | 支持      |                                                                                                                                             |

#### <a name="teams-rooms-on-android"></a>[Android上的Teams 会议室](#tab/mtr-a)

下表列出了设备符合性设置及其与Teams 会议室配合使用的建议。  

| 策略                                                                                                                                  | 可用性  | 注释                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 要求设备处于或低于计算机风险分数                                                                             | 不支持 |                                                                               |
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 使用设备管理员管理的设备                                                                                                | 必需      | Teams Android设备管理需要启用设备管理员。 |
| 根设备                                                                                                                          | 支持     |                                                                               |
| 要求设备处于或低于设备威胁级别                                                                            | 不支持 |                                                                               |
| [**Google Play 保护**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| 配置了Google Play Services                                                                                                      | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 最新安全提供程序                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 对应用进行威胁扫描                                                                                                                     | 不支持 | Google play 未安装在Teams Android设备上。                         |
| SafetyNet 设备证明                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| [**设备属性**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 操作系统版本 (最小、最大)                                                                                              | 支持     |                                                                               |
| [**系统安全性**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 需要对设备上的数据存储进行加密。                                                                                           | 支持     |                                                                               |
| [**设备安全性**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 阻止来自未知源的应用                                                                                                         | 不支持 | 仅Teams管理员安装应用或 OEM 工具                                   |
| 公司门户应用运行时完整性                                                                                                    | 支持     |                                                                               |
| 受限应用                                                                                                                         | 不支持 |                                                                               |
| 阻止设备上的 USB 调试                                                                                                           | 支持     |                                                                               |
| [**所有Android设备*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 需要密码之前的最大非活动分钟数                                                                              | 不支持 |                                                                               |
| 需要密码才能解锁移动设备                                                                                             | 不支持 |                                                                               |
| [**Android 10 及更高版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 及更早版本或三星诺克斯**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必需密码类型                                                                                                                  | 不支持 |                                                                               |

#### <a name="teams-phones-and-displays"></a>[Teams手机和显示器](#tab/phones)

下面是设备符合性设置和建议表，用于Teams手机和显示器。  

| 策略                                                                                                                                  | 可用性  | 注释                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 要求设备处于或低于计算机风险分数                                                                             | 不支持 |                                                                               |
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 使用设备管理员管理的设备                                                                                                | 必需      | Teams Android设备管理需要启用设备管理员。 |
| 根设备                                                                                                                          | 支持     |                                                                               |
| 要求设备处于或低于设备威胁级别                                                                            | 不支持 |                                                                               |
| [**Google Play 保护**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| 配置了Google Play Services                                                                                                      | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 最新安全提供程序                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 对应用进行威胁扫描                                                                                                                     | 不支持 | Google play 未安装在Teams Android设备上。                         |
| SafetyNet 设备证明                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| [**设备属性**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 操作系统版本 (最小、最大)                                                                                              | 支持     |                                                                               |
| [**系统安全性**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 需要对设备上的数据存储进行加密。                                                                                           | 支持     | 制造商可能会以Intune无法识别的方式在其设备上配置加密属性。 如果发生这种情况，Intune将设备标记为不符合。<br><br>制造商配置这些加密属性的方式可能因设备模型而异。 有关特定模型的详细信息，请联系设备制造商。 |
| [**设备安全性**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 阻止来自未知源的应用                                                                                                         | 不支持 | 仅Teams管理员安装应用或 OEM 工具                                   |
| 公司门户应用运行时完整性                                                                                                    | 支持     |                                                                               |
| 受限应用                                                                                                                         | 不支持 |                                                                               |
| 阻止设备上的 USB 调试                                                                                                           | 支持     |                                                                               |
| [**所有Android设备*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 需要密码之前的最大非活动分钟数                                                                              | 不支持 |                                                                               |
| 需要密码才能解锁移动设备                                                                                             | 不支持 |                                                                               |
| [**Android 10 及更高版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 及更早版本或三星诺克斯**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必需密码类型                                                                                                                  | 不支持 |                                                                               |



#### <a name="teams-panels"></a>[Teams面板](#tab/panels)

下表列出了设备符合性设置及其在Teams面板中使用的建议。  

| 策略                                                                                                                                  | 可用性  | 注释                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 要求设备处于或低于计算机风险分数                                                                             | 不支持 |                                                                               |
| [**设备运行状况**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 使用设备管理员管理的设备                                                                                                | 必需      | Teams Android设备管理需要启用设备管理员。 |
| 根设备                                                                                                                          | 支持     |                                                                               |
| 要求设备处于或低于设备威胁级别                                                                            | 不支持 |                                                                               |
| [**Google Play 保护**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| 配置了Google Play Services                                                                                                      | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 最新安全提供程序                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| 对应用进行威胁扫描                                                                                                                     | 不支持 | Google play 未安装在Teams Android设备上。                         |
| SafetyNet 设备证明                                                                                                            | 不支持 | Google play 未安装在Teams Android设备上。                         |
| [**设备属性**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 操作系统版本 (最小、最大)                                                                                              | 支持     |                                                                               |
| [**系统安全性**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 需要对设备上的数据存储进行加密。                                                                                           | 支持     |                                                                               |
| [**设备安全性**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 阻止来自未知源的应用                                                                                                         | 不支持 | 仅Teams管理员安装应用或 OEM 工具                                   |
| 公司门户应用运行时完整性                                                                                                    | 支持     |                                                                               |
| 受限应用                                                                                                                         | 不支持 |                                                                               |
| 阻止设备上的 USB 调试                                                                                                           | 支持     |                                                                               |
| [**所有 Android 设备*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 需要密码之前的最大非活动分钟数                                                                              | 不支持 |                                                                               |
| 需要密码才能解锁移动设备                                                                                             | 不支持 |                                                                               |
| [**Android 10 及更高版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 及更早版本或 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必需密码类型                                                                                                                  | 不支持 |                                                                               |

---

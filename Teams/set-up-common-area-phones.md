---
title: 设置公共区域电话许可证
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '了解如何为大厅、接待区和会议室设置公共区域电话 '
ms.openlocfilehash: f3f3ee2c98e48a41bb12dcaa7fc461c623f49994
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045821"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>为Microsoft Teams部署常用区域电话

公用区域电话通常放置在大厅等区域或许多人可以拨打电话的另一个区域中：例如，接待区、大厅或会议电话。 公共区域电话使用绑定到公共区域电话许可证的帐户登录。

本文概述了如何将Teams手机部署和配置为共享空间的公共区域电话。 若要获得更完整的会议室体验（包括音频会议），请考虑使用会议室设备购买专用会议室许可证。

## <a name="overview"></a>概述

公共区域电话许可证支持：

|                                           | 公共区域电话                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams 电话**&sup1;                   | &#x2714;                                          |
| **音频会议**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium计划 1** | &#x2714;                                          |
| **Exchange Online计划 2**                | &#x2714;  &sup3;                                  |
| **全球可用性**                | &#x2714;                                          |
| **通道可用性**                  | EA、EAS、EES、云解决方案提供商、Web Direct、GCC、GCC-High、DoD |

&sup1;以前称为电话系统。

&sup2;公共区域电话可以通过会议组织者提供的拨入号码加入音频会议。  

&sup3;仅限基于云的语音邮件功能。

>[!NOTE]
> 无法将Skype for Business Server中创建的常见区域电话对象的帐户迁移到Microsoft Teams。 按照本文中的步骤为Teams重新创建这些帐户，并根据需要迁移 PTSN 连接。

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

首先，需要购买通用区域电话 (CAP) 许可证，并确保拥有经过认证的电话。 若要搜索和了解有关认证手机的详细信息，请转到[Microsoft Teams设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在Microsoft 365 管理中心中，转到 **计** > 费 **购买服务**。 

2. 如果“ **按类别查看** ”部分尚未显示，请 **转到“从 Microsoft 购买**”，然后选择 **“查看产品**”。 然后选择 **“协作和通信**”。  

3. 在产品列表中，查找 **公共区域电话** 并选择 **“详细信息**”。

4. 输入所需的许可证数，然后选择 **“购买**”。

>[!NOTE]
>如果在环境中使用Intune，并且有要求设备符合性的条件访问规则，则需要分配Azure Active Directory Premium计划 1，并将许可证Intune到通用区域电话的设备帐户。
>
>常见区域电话可能会受到条件访问规则和其他标识配置（如多重身份验证）的影响。 若要了解详细信息，请参阅[Teams Android设备的身份验证最佳做法](devices/authentication-best-practices-for-android-devices.md)。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步骤 2 - 创建新的用户帐户并分配许可证

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

如果一次部署多个通用区域电话，请了解如何 [使用 PowerShell](#using-powershell) 创建帐户和分配许可证。

如果要部署一台设备：

1. 在Microsoft 365 管理中心中，转到 **“用户** > **活动用户** > **添加用户**”。

2. 输入用户名（如“Main”）作为名字，为第二个名称输入“接收”。

3. 如果显示名称未自动生成“主接收”等显示名称，请输入该名称。

4. 输入用户名，如“MainReception”或“Mainlobby”。

5. 手动设置公共区域电话的密码以防止。 为此，取消选中 **自动创建密码** ， **并要求此用户在首次登录时更改其密码**。  

    >[!Important]
    > 强烈建议为公用区域电话手动设置密码，以防止最终用户出现登录问题。

6. 选择设备的使用位置，并将公共区域电话许可证分配给帐户。 如果需要任何其他许可证（如呼叫计划），请分配它们。

>[!NOTE]
> 无需添加电话系统许可证。 许可证包含在公共区域电话许可证中。
>
>如果不使用Microsoft 电话系统直接路由或运营商连接，则可能需要添加通话套餐许可证。 有关许可证的详细信息，请参阅[Microsoft Teams附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

想要同时为多个用户帐户创建和分配许可证时，请使用 PowerShell。 有关详细信息，请参阅[使用 PowerShell 创建Microsoft 365用户帐户](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)，并将[Microsoft 365许可证分配给使用 PowerShell 的用户帐户](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

## <a name="step-3---set-policies-for-common-area-phones"></a>步骤 3 - 为公用区域电话设置策略

使用策略控制公共区域电话上的用户可用的功能。

>[!NOTE]
>分配策略后，注销手机并重新登录。 策略分配可能需要长达一小时才能生效。

### <a name="ip-phone-policies"></a>IP 电话策略

使用已分配公共区域电话许可证的帐户登录的电话将显示公共区域用户体验。

如果要覆盖手机的默认接口，请考虑创建 [IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true)。 例如，如果公共区域中使用了公共区域电话，请设置 IP 电话策略以限制搜索组织的全局通讯簿并阻止热桌面。 有关详细信息，请参阅[“设置Teams Android设备用户界面](devices/Teams-Android-devices-user-interface.md)”。

### <a name="calling-policies"></a>通话策略

使用呼叫策略在公共区域电话上使用呼叫转接或同时拨打来启用专用呼叫。 请参阅[Teams中的呼叫和呼叫转发](teams-calling-policy.md)，了解详细信息。

默认情况下，公共区域电话未启用呼叫寄存。 你需要创建一个策略来启用它。 请参阅[呼叫寄存，并在Microsoft Teams中检索](call-park-and-retrieve.md)以了解详细信息。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步骤 4 - 获取和分配电话号码

请参阅 [组织管理电话号码](manage-phone-numbers-landing-page.md) ，了解如何根据 PSTN 连接选项获取和分配电话号码。

## <a name="step-5---sign-in"></a>步骤 5 - 登录

创建和配置用户帐户后，可以登录到手机。 根据要部署的手机数量，你有三个登录选项：

- [本地登录](#local-sign-in)
- [从另一台设备登录](#sign-in-from-another-device)
- [使用Teams管理中心登录](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>本地登录

若要使用用户名和密码在本地登录： 

1. 打开公共区域电话

2. 选择 **在此设备上登录**

3. 按照设备上的登录说明操作。 登录后，手机将显示通用区域电话用户体验。

> [!NOTE]
> 如果使用的是取消固定调用应用的自定义设置策略，则拨号盘不会显示在公共区域电话上。 有关Teams设置策略的详细信息，请参阅[Microsoft Teams中的“管理应用设置策略](/microsoftteams/teams-app-setup-policies)”。

### <a name="sign-in-from-another-device"></a>从另一台设备登录

还可以使用代码从另一台设备登录到公共区域电话。 以这种方式登录时，会在另一台设备上输入用户名和密码，而不是在手机本身上输入。

1. 首先，在公共区域电话上，查找登录屏幕上显示的代码。

2. 在另一台设备上，转到 https://www.microsoft.com/devicelogin。

3. 输入代码并按照说明完成登录。

### <a name="sign-in-using-the-teams-admin-center"></a>使用Teams管理中心登录

作为管理员，可以从Teams管理中心远程预配和登录公共区域电话。 这是一次部署大量手机时最有效的登录方法。 有关详细信息，请参阅[远程预配并登录Teams Android设备](devices/remote-provision-remote-login.md)。

## <a name="next-steps"></a>后续步骤

现在，你已为组织设置并登录了公共区域电话，可以在Teams管理中心管理它们。 请参阅[Microsoft Teams：管理设备](devices/device-management.md)以了解详细信息。

## <a name="related-topics"></a>相关主题

- [远程更新Microsoft Teams设备](devices/remote-update.md)
- [管理Microsoft Teams设备标记](devices/manage-device-tags.md)
- [Microsoft Teams设备运行状况监视](alerts/device-health-status.md)

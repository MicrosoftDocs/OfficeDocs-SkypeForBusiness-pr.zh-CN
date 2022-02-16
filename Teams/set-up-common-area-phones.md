---
title: 设置"公共区域"电话许可证
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
description: '了解如何为大厅、接收区和会议室设置公用区域电话 '
ms.openlocfilehash: 144e32e1bf56bc3e2d64d0c6a1a137fd501442b7
ms.sourcegitcommit: 5aae5eace62e491dac655882d24974824ce1aa07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "62856660"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>为用户部署常用Microsoft Teams

公用区域电话通常放置在大厅等区域，或者供许多人进行呼叫的另一区域;例如，前台区域、大厅或会议电话。 常用区域电话使用与公用区域服务许可证绑定电话登录。

本文概述了如何将手机部署和Teams共享空间的公用区域电话。 要获得更完整的会议室体验（包括音频会议），请考虑购买具有会议室设备的专用会议许可证。

## <a name="overview"></a>概述

公共区域电话支持： 


| &nbsp;  |  公共区域电话  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|电话系统 |    &#x2714; |
|音频会议 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|全球可用性 |       &#x2718; &sup2;  |
|频道可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;公用区域电话可以通过会议组织者提供的拨入号码加入音频会议

&sup2;在主权云中不可用  

>[!NOTE]
> 在 Skype for Business Server 中创建的常用区域电话对象的帐户无法迁移到Microsoft Teams。 按照本文中的步骤重新创建这些帐户Teams，并迁移 PTSN 连接（如果需要）。

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

首先，需要购买公共区域 电话 (CAP) 许可证，并确保拥有经过认证的电话。 若要搜索并了解有关认证电话的信息，请转到Microsoft Teams[设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在Microsoft 365 管理中心，转到 **"计费** > **""购买服务"**。 

2. 如果" **按类别** 查看"部分尚未显示，请转到"从 **Microsoft** 购买"，然后选择" **查看产品"**。 然后选择" **协作和通信"**。  

3. 在产品列表中，找到 **"常用区域"电话** 并选择"**详细信息"**。

4. 输入所需的许可证数，然后选择"购买 **"**。

>[!NOTE]
>如果在环境中使用 Intune，并且具有要求设备符合性的条件访问规则，则需要为公共区域电话的设备帐户分配 Azure Active Directory Premium 计划 1 和 Intune 许可证。
>
>常见区域电话可能会受到条件访问规则和其他标识配置（如多重身份验证）的影响。 有关详细信息[，请参阅 Teams Android 设备的](devices/authentication-best-practices-for-android-devices.md)身份验证最佳做法。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步骤 2 - 创建新的用户帐户并分配许可证

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

如果要一次部署多个公用区域电话，请了解如何使用 [PowerShell 创建帐户和分配许可证](#using-powershell)。

如果要部署一个设备：

1. 在Microsoft 365 管理中心，转到"**用户** > **""活动用户** > **""将用户"。**

2. 输入用户名，例如"Main"作为名字，输入"接收"作为第二个名称。

3. 如果没有自动生成显示名称如"主前台"，请输入一个密码。

4. 输入用户名，例如"MainReception"或"Mainlobby"。

5. 手动设置常用区域电话的密码以防止。 为此，请取消选中 **"自动创建** 密码"，并要求此用户在首次登录 **时更改其密码**。  

    >[!Important]
    > 强烈建议为常用区域电话手动设置密码，以防止最终用户出现登录问题。

6. 选择设备的使用位置，并将"公用区域"电话许可证分配给帐户。 如果需要任何其他许可证（如呼叫计划），请分配它们。

>[!NOTE]
> 无需添加许可证电话系统许可证。 许可证包含在公共区域电话许可证中。
>
>如果不使用系统直接Microsoft 电话或运营商连接，可能需要添加呼叫计划许可证。 有关许可证详细信息，请参阅Microsoft Teams[附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

若要同时为多个用户帐户创建和分配许可证，请使用 PowerShell。 有关详细信息[，Microsoft 365 PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) 创建用户帐户和Microsoft 365 [PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) 为用户帐户分配许可证。

## <a name="step-3---set-policies-for-common-area-phones"></a>步骤 3 - 设置常用区域电话的策略

使用策略来控制公用区域电话上哪些功能可供用户使用。

>[!NOTE]
>分配策略后，注销手机并重新登录。 策略分配最多可能需要一小时才生效。

### <a name="ip-phone-policies"></a>IP 电话策略

使用已分配"公共区域"电话登录的电话将显示公共区域用户体验。

如果要替代电话的默认接口，请考虑创建 [IP 电话策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)。 例如，如果在公共区域中使用公用区域电话，请设置 IP 电话策略以限制搜索组织的全局通讯簿并阻止热桌面。 有关详细信息[，Teams设置 Android](devices/Teams-Android-devices-user-interface.md) 设备用户界面。

### <a name="calling-policies"></a>通话策略

使用呼叫策略在公用区域电话上启用私人呼叫、使用呼叫转发或同时拨打。 有关详细信息[，请参阅](teams-calling-policy.md)在 Teams 呼叫和呼叫转发。

默认情况下，不为公用区域电话启用呼叫停放。 需要创建一个策略来启用它。 有关详细信息[，请参阅呼叫Microsoft Teams](call-park-and-retrieve.md)和检索。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步骤 4 - 获取和分配电话号码

请参阅 [管理组织的电话号码](manage-phone-numbers-landing-page.md) ，了解如何根据 PSTN 连接选项获取和分配电话号码。

## <a name="step-5---sign-in"></a>步骤 5 - 登录

创建和配置用户帐户后，可以登录到手机。 根据要部署的电话，有三个登录选项：

- [本地登录](#local-sign-in)
- [从另一台设备登录](#sign-in-from-another-device)
- [使用 Teams 管理中心登录](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>本地登录

若要使用用户名和密码在本地登录，请： 

1. 打开公用区电话

2. 选择 **"在此设备上登录"**

3. 按照设备的登录说明操作。 登录后，手机会显示常见的区域电话用户体验。

### <a name="sign-in-from-another-device"></a>从另一台设备登录

您也可以使用代码从另一台设备登录到公用区域电话。 这样登录时，你将在另一台设备上输入用户名和密码，而不是在手机本身上输入。

1. 首先，在常用区域电话上，查找登录屏幕上显示的代码。

2. 在另一台设备上，转到 https://www.microsoft.com/devicelogin。

3. 输入代码，然后按照说明完成登录。

### <a name="sign-in-using-the-teams-admin-center"></a>使用 Teams 管理中心登录

作为管理员，可以从管理中心远程预配和登录到Teams电话。 这是一次部署大量电话时最有效的登录方法。 有关详细信息[，请参阅远程预配Teams Android 设备的](devices/remote-provision-remote-login.md)登录。

## <a name="next-steps"></a>后续步骤

为组织设置并登录公用区域电话后，可以在管理中心内Teams电话。 有关详细信息[Microsoft Teams请参阅管理](devices/device-management.md)设备。

## <a name="related-topics"></a>相关主题

- [远程Microsoft Teams更新设备](devices/remote-update.md)
- [管理Microsoft Teams标记](devices/manage-device-tags.md)
- [Microsoft Teams设备运行状况监视](alerts/device-health-status.md)

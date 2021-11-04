---
title: 注销 Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: 了解如何注销 Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fb1048f0db6166dbbcd7f43c317db2603b57dd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750081"
---
# <a name="sign-out-of-microsoft-teams"></a>注销 Microsoft Teams

我们建议用户保持登录到 Microsoft Teams 应用，从而继续接收聊天、来电以及其他活动。 我们了解，用户有时可能出于以下几个原因想要注销 Teams 应用程序:

- 因为他们厌倦了一整天使用 Teams
- 他们希望使用不同的帐户
- 因为他们位于与他人共享的设备上

出于这些等其他原因，Teams 允许注销应用并结束会话。

## <a name="account-sharing-between-apps"></a>应用之间的帐户共享

新式操作系统允许在设备的不同应用之间共享帐户。 此单一登录(SSO) 设计允许用户在其设备上使用多个应用，而无需登录到每个应用。 Teams 不控制此行为，但确实利用了此设计为最终用户体验提供的便利。

SSO 对注销有重要影响。当用户注销 Teams 时，系统会从 Teams 应用中删除与其帐户关联的数据，但设备上的其他应用可以继续访问其帐户。 这也意味着，如果用户选择使用同一帐户重新登录 Teams，则系统可能不会提示其重新输入凭据。

## <a name="sign-out-of-teams-on-desktop"></a>在桌面上注销 Teams

要注销 Teams 桌面客户端或从浏览器中注销，请选择应用顶部的配置文件图片，然后选择 **注销**。

对于桌面应用，还可以右击任务栏中的应用图标，然后选择 **注销**。

如果添加了多个帐户，则需要注销每个单独的帐户。 注销 Teams 中的帐户后，可能需要在下次启动应用时再次输入凭据以访问帐户。

## <a name="sign-out-of-teams-on-mobile-devices"></a>在移动设备上注销 Teams

在移动设备上，要注销 Teams 可以转到菜单，选择 **更多** 菜单，然后选择 **注销**。注销后，下次启动应用时需要重新输入凭据。

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>适用于一线员工的全局登录和注销

现在，Teams Android 应用支持全局登录和注销，为一线员工提供简便的登录和注销体验。 员工可以从共享设备池中选取设备，并在轮班期间进行单一登录以“使其成为自己的设备”。 当轮班结束时，他们应能够执行注销以在设备上进行全局注销。 这将从设备中删除其所有个人和公司信息，以便其可以将设备返回设备池。 若要获取此功能，设备必须处于共享模式。 若要了解如何设置共享设备，请参阅[如何使用 Android中的共享设备模式](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。

## <a name="manual-cleanup"></a>手动清理

尽管很少见，但 Teams 在完全注销后可能无法进行清理。根据用户报告，常见原因包括文件被系统上运行的服务锁定，但可能还存在其他原因，这取决于个人设备配置或策略以及应用于设备的用户权限。

此问题的常见表现包括 Teams 将尝试自动选择现有帐户以使用户登录。 在此类情况下，用户可能想要手动清理 Teams 本地缓存。 有关详细信息，请参阅 [从 Teams 中登录或删除帐户](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)。

## <a name="related-topics"></a>相关主题

[从 Teams 中登录或删除帐户](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)
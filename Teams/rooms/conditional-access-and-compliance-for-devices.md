---
title: 适用于应用程序的条件访问和符合性Microsoft Teams 会议室
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解建议的条件访问和 Intune 设备符合性策略以及适用于Microsoft Teams 会议室。
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689063"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>应用程序的条件访问和 Intune 符合性Microsoft Teams 会议室

本文提供共享空间中使用的条件访问和 Intune Microsoft Teams 会议室策略的要求和最佳做法。

## <a name="requirements"></a>要求

Teams 会议室必须已部署到要为其分配条件访问策略的设备上。 如果尚未部署Teams 会议室，请参阅为会议室和共享设备创建资源[](with-office-365.md)Teams和在 [Android](../devices/collab-bar-deploy.md) Microsoft Teams 会议室部署帐户了解详细信息。

使用Azure Active Directory访问需要一个 P1 服务计划。 它包含在许可证Microsoft Teams 会议室中。

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams 会议室条件访问最佳实践

条件访问策略可以保护共享空间中且由多人使用的设备的登录过程。 有关服务中条件访问的Azure Active Directory (Azure AD) [，请参阅什么是条件访问Azure Active Directory？](/azure/active-directory/conditional-access/overview)。

使用条件访问保护Teams 会议室，请考虑以下最佳做法：

-   若要简化部署和管理，请Microsoft 365组包含与Teams 会议室关联的所有会议室资源帐户。

-   对于所有资源帐户，都有Teams 会议室标准。 例如，帐户名称"mtr-room1@contoso.com"和"mtr-room2@contoso.com"均以前缀"prefix""开头。
    当帐户名称标准化时，可以使用 Azure AD 动态组来自动将条件访问策略一次应用到所有这些帐户。 有关 [动态组的信息，](/azure/active-directory/enterprise-users/groups-dynamic-membership) 请参阅动态填充组成员身份规则。

有关受支持的条件访问分配列表Teams 会议室，请参阅[支持的条件访问策略](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)。

## <a name="example-conditional-access-policy"></a>示例条件访问策略

在下面的示例中，条件访问策略的工作方式如下：

1.  帐户登录必须是特定用户组（本示例中为"共享设备"组）的成员。

2.  帐户登录必须仅尝试访问 Exchange Online、Microsoft Teams 或 SharePoint Online。 尝试登录到任何其他客户端应用会被拒绝。

3.  资源帐户必须登录 Windows平台。

4.  资源帐户还必须从已知的受信任位置登录。

如果成功满足这些条件，并且用户输入了正确的用户名和密码，则资源帐户将登录到 Teams。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>条件访问Microsoft Intune符合性Teams 会议室

符合性要求是设备必须满足的、标记为合规的已定义规则，例如最低操作系统版本。 必须先将设备视为合规，然后才能用于登录到资源帐户。

有关受支持的 Intune 符合性策略列表Teams 会议室，请参阅[支持的设备符合性策略](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)。

有关使用 Android 设备Teams Intune 的信息，请参阅配置 [Intune 以Teams基于 Android 的设备](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>仅 (Windows示例) ：具有 Intune 设备符合性的条件性访问

此示例中，Teams 会议室 on Windows

1. 要求防火墙在 Teams 会议室 上运行Windows。

2. 要求 Microsoft Defender 在 Teams 会议室。

3. 如果Teams聊天室不符合上述任一要求，则它将不会标记为合规，并且设备不会登录。

此符合性策略适用于所有用户，而不只是Teams帐户。

---
title: Microsoft Teams 会议室的条件访问和符合性最佳做法
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 了解建议的条件访问和Intune设备符合性策略以及Microsoft Teams 会议室的最佳做法。
ms.openlocfilehash: a1d86b002a4960e58541650643574428a2c3ede5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271027"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>条件访问和Intune符合Microsoft Teams 会议室

本文为共享空间中使用的Microsoft Teams 会议室提供条件访问和Intune设备符合性策略的要求和最佳做法。

## <a name="requirements"></a>要求

Teams 会议室必须已部署在要将条件访问策略分配到的设备上。 如果尚未部署Teams 会议室，请参阅[为会议室和共享 Teams 设备创建资源帐户](with-office-365.md)，并在 [Android 上部署Microsoft Teams 会议室](../devices/collab-bar-deploy.md)，了解详细信息。

使用条件访问需要 Azure Active Directory P1 服务计划。 它包含在Microsoft Teams 会议室许可证中。

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams 会议室条件访问最佳做法

条件访问策略可以在共享空间中且由多人使用的设备上保护登录过程。 有关 Azure Active Directory (Azure AD) 中的条件访问概述，[请参阅 Azure Active Directory 中的条件访问是什么？](/azure/active-directory/conditional-access/overview)

使用条件访问保护Teams 会议室时，请考虑以下最佳做法：

-   若要简化部署和管理，请将与Teams 会议室关联的所有 Microsoft 365 会议室资源帐户包含在一个用户组中。

-   为所有Teams 会议室资源帐户制定命名标准。 例如，帐户名称“mtr-room1@contoso.com”和“mtr-room2@contoso.com”都以前缀“mtr-”开头。
    当帐户名称标准化时，可以使用 Azure AD 中的动态组一次性自动将条件访问策略应用到所有这些帐户。 有关动态组的详细信息，请参阅 [动态填充组成员身份的规则](/azure/active-directory/enterprise-users/groups-dynamic-membership) 。

有关Teams 会议室支持的条件访问分配的列表，请参阅[支持的条件访问策略](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)。

## <a name="example-conditional-access-policy"></a>示例条件访问策略

在下面的示例中，条件访问策略的工作原理如下：

1.  登录帐户必须是特定用户组的成员，在此示例中为“共享设备”组。

2.  登录帐户必须仅尝试访问Exchange Online、Microsoft Teams 或 SharePoint Online。 将拒绝登录任何其他客户端应用的尝试。

3.  资源帐户必须在 Windows 设备平台上登录。

4.  资源帐户还必须从已知的受信任位置登录。

如果成功满足这些条件，并且用户输入了正确的用户名和密码，则资源帐户将登录到 Teams。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>具有Microsoft Intune符合性的条件访问Teams 会议室

符合性要求是定义的规则，设备必须满足这些规则才能标记为符合，例如最低操作系统版本。 设备必须被视为符合要求，然后才能使用它们登录到资源帐户。

有关Teams 会议室支持的Intune符合性策略的列表，请参阅[受支持的设备符合性策略](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)。

有关使用 Teams Android 设备设置Intune的详细信息，请参阅[配置Intune以注册基于 Teams Android 的设备](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>仅) windows (示例：具有设备符合性Intune条件访问

在此示例中，在 Windows 上Teams 会议室

1. 要求在 Windows 上的Teams 会议室上运行防火墙。

2. 要求 Microsoft Defender 在Teams 会议室上运行。

3. 如果 Teams 会议室不符合上述任一要求，则不会将其标记为合规，并且设备不会登录。

此符合性策略适用于所有用户，而不仅仅是 Teams 资源帐户。

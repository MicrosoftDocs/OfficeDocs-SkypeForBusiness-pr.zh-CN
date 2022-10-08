---
title: 为会议室和共享 Teams 设备创建资源帐户
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 请阅读本文，了解如何为会议室和共享设备创建资源帐户，包括 Microsoft Teams 会议室、Surface Hub 上的Teams 会议室和 Teams 上的热桌面显示。
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475494"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>为会议室和共享 Teams 设备创建和配置资源帐户

本文提供为共享空间和设备创建资源帐户的步骤，其中包括为 Windows 上的Microsoft Teams 会议室、Android 上的Teams 会议室、Surface Hub 上的Teams 会议室和 Teams 显示器上的热桌面配置资源帐户的步骤。

Microsoft 365 资源帐户是专用于特定资源（例如会议室或投影机）的邮箱和 Teams 帐户。 这些资源帐户可以使用创建时定义的规则自动响应会议邀请。 例如，如果你有一个常见的资源（例如会议室），则可以为该会议室设置一个资源帐户，该帐户将根据会议室的日历可用性自动接受或拒绝会议邀请。 

每个资源帐户对于单个Microsoft Teams 会议室安装或 Teams 显示热桌面实现都是独一无二的。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> 如果使用 Microsoft Teams 面板，则Teams 会议室资源帐户将登录到Teams 会议室和关联的 Teams 面板。

> [!NOTE]
> **Skype for Business** <br><br>
> 如果需要使资源帐户能够使用Skype for Business，请参阅[使用Skype for Business Server部署Microsoft Teams 会议室](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>开始之前

### <a name="requirements"></a>要求

根据你的环境，你需要一个或多个角色来创建资源帐户。

|**环境**|**必需角色**|
|-----|-----|
|Azure Active Directory  <br/> |全局管理员或用户管理员  <br/> |
|Active Directory  <br/> |Active Directory Enterprise 管理员、域管理员或具有创建用户的委派权限。 Azure Active Directory Connect 同步权限。  <br/> |
|Exchange Online  <br/> |全局管理员或 Exchange 管理员   <br/> |
|Exchange Server  <br/> |Exchange 组织管理或收件人管理   <br/> |

如果要为Teams 会议室创建资源帐户，UPN 必须与资源帐户的 SMTP 地址匹配。 在部署Teams 会议室之前，请参阅Microsoft Teams 会议室[要求](requirements.md)。

### <a name="what-license-do-you-need"></a>需要什么许可证？

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>创建资源帐户

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>配置邮箱属性

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>关闭密码过期

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>分配会议室许可证

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>后续步骤

### <a name="meeting-policies"></a>会议策略

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>通话

没有使用资源帐户启用调用的唯一要求。 启用资源帐户以与启用常规用户相同的方式进行调用。

> [!NOTE]
> 建议通过向设备资源帐户分配呼叫策略来关闭共享设备的语音邮件。 有关详细信息，请参阅 [Teams 中的呼叫和呼叫转发](../teams-calling-policy.md) 。

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>相关文章

[为Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)

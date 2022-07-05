---
title: 在 Teams 中管理资源帐户
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 本文介绍如何在 Microsoft Teams 中创建、编辑和管理资源帐户。
ms.openlocfilehash: 0b8c77f7d6371ba1bfefa9837488415405e48f67
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615798"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>后续步骤

完成资源帐户设置并根据需要分配服务号码后，即可将资源帐户与自动助理或呼叫队列配合使用。

有关详细信息，请参阅以下引用：

- [云自动助理](create-a-phone-system-auto-attendant.md)
- [云呼叫队列](create-a-phone-system-call-queue.md)

可以使用“**编辑**”选项编辑资源帐户 **显示名称** 和 **资源帐户** 类型。 完成后单击 **“保存** ”。

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>更改现有资源帐户以使用 Teams 电话资源帐户许可证

如果决定将现有资源帐户上的许可证从 **Teams 电话标准版** 许可证切换到 **Microsoft Teams 电话资源帐户** 许可证，则需要获取免费 **的 Teams 电话资源帐户** 许可证，然后按照Microsoft 365 管理中心 [中的步骤操作将用户移动到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除完整的Teams 电话标准版许可证，并在同一许可证活动中分配 **Microsoft Teams 电话资源帐户** 许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。 如果发生这种情况，建议为 **Microsoft Teams 电话资源帐户** 许可证创建新的资源帐户，并删除损坏的资源帐户。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

有关 Skype For Business Server 2019 上可与云呼叫队列和云自动助理配合使用的资源帐户，请参阅 [计划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。 直接路由) 上托管的混合实现 (数字使用本地Skype for Business Server 2019 服务器上的 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet 进行配置。

创建应用程序实例时需要使用的应用程序 ID 包括：

- **自动助理：** ce933385-9390-45d1-9512-c8d228074e07
- **呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果希望 Skype For Business Server 2019 用户可以搜索呼叫队列或自动助理，则应在 Skype For Business Server 2019 上创建资源帐户，因为联机资源帐户不会同步到 Active Directory。 当 sipfederationtls 的 DNS SRV 记录解析为 Skype for Business Server 2019 时，**必须** 使用 SfB Management shell 在 Skype For Business Server 2019 上创建资源帐户并同步到 Azure AD。

对于与Skype for Business Server混合的实现：

   [规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [规划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)

   [配置本地资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>删除资源帐户

删除之前，请确保将电话号码与资源帐户分离，以免服务号码卡在挂起模式下。

执行此操作后，可以在“用户”选项卡下的Microsoft 365 管理中心中删除资源帐户。

若要与资源帐户取消直接路由电话号码的关联，请使用以下 cmdlet：

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

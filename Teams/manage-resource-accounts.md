---
title: 在 Teams 中管理资源帐户
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 在本文中，你将了解如何在 Microsoft 团队中创建、编辑和管理资源帐户。
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993497"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

资源帐户是 Azure AD 中已禁用的用户对象，可用于表示常规资源。 例如，可以在 Exchange 中使用资源帐户表示会议室，并允许他们拥有电话号码和日历。 资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。

在 Microsoft 团队中，每个自动助理或呼叫队列需要资源帐户。 也可以为资源帐户分配服务电话号码。 这是将电话号码分配给自动助理和呼叫队列的方式，允许来自外部团队的呼叫者到达自动助理或呼叫队列。

本文介绍如何创建资源帐户并准备好使用自动助理和呼叫队列。

在开始本文中的过程之前，请确保已完成以下操作：

- [获取虚拟用户许可证](#obtain-virtual-user-licenses)
- [获取服务号码](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>获取虚拟用户许可证

每个资源帐户都需要许可证，才能使用自动助理和呼叫队列。 您可以使用免费的 *Microsoft 365 Phone 系统虚拟用户* 许可证。 若要获取这些许可证，请参阅 [虚拟用户许可证](teams-add-on-licensing/virtual-user.md)。

我们将在本文的后面部分介绍如何将许可证分配给资源帐户。

若要获取虚拟用户许可证，请在 Microsoft 365 管理中心中，转到 " **支付**  >  **购买服务**  >  **附加订阅** "，滚动到 "结束"，您将看到 " *电话系统-虚拟用户* 许可证"。 选择 " **立即购买** "。 成本不为零，但仍需按照这些步骤获取许可证。

### <a name="obtain-service-numbers"></a>获取服务号码

服务号码对于自动助理和呼叫队列是可选的，但是您至少需要一个服务编号才能让呼叫者到达您的自动助理和呼叫队列配置。 对于您希望通过服务号码直接访问的任何自动助理或呼叫队列，您必须有一个具有相关服务号码的资源帐户。

资源帐户可以使用收费或免费服务号码。 您可以申请新号码或从其他运营商的现有号码中移植。

若要获取新的服务号码，请参阅 [获取服务电话号码](getting-service-phone-numbers.md)。

若要从另一个运营商那里移植号码，请参阅 [将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

## <a name="create-a-resource-account"></a>创建资源帐户

可以在 "团队管理中心" 中创建资源帐户。

![添加资源帐户用户界面的屏幕截图](media/resource-account-add.png)

1. 在 "团队管理中心" 中，展开 " **组织范围的设置** "，然后单击 " **资源帐户** "。

2. 单击“添加”。

3. 在 " **添加资源帐户** " 窗格中，填写 " **显示名称** "、" **用户名** " 和 " **资源帐户类型** "。 资源帐户类型可以是 **自动助理** 或 **呼叫队列** ，具体取决于你打算使用此资源帐户的方式。

4. 单击“ **保存** ”。

![资源帐户列表的屏幕截图](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>分配许可证

对于每个资源帐户，您必须分配一个 *Microsoft 365 电话系统-虚拟用户* 许可证或 *电话系统* 许可证。

![Microsoft 365 管理中心中分配许可证用户界面的屏幕截图](media/resource-account-assign-virtual-user-license.png)

1. 在 "Microsoft 365 管理中心" 中，单击要为其分配许可证的资源帐户。

2. 在 " **许可证和应用** " 选项卡上的 " **许可证** " 下，选择 " **Microsoft 365 Phone System-虚拟用户** "。

3. 单击 " **保存更改** "。

## <a name="assign-a-service-number"></a>分配服务号码

如果你打算将资源帐户与需要服务号码的自动助理或呼叫队列结合使用，请为资源帐户分配一个号码。

!["分配服务号码" 用户界面的屏幕截图](media/resource-account-assign-phone-number.png)

1. 在 "团队" 管理中心的 " **资源帐户** " 页面上，选择要为其分配服务编号的资源帐户，然后单击 " **分配/取消分配** "。

2. 在 " **电话号码类型** " 下拉列表中，选择要使用的号码类型。

3. 在 " **分配的电话号码** " 框中，搜索要使用的号码，然后单击 " **添加** "。

4. 单击“ **保存** ”。


若要为资源帐户分配直接路由或混合号码，您需要使用 PowerShell：

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>后续步骤

完成资源帐户设置并根据需要分配服务号码后，您就可以将资源帐户与自动助理或呼叫队列配合使用。

请参阅以下参考资料：

 - [云自动助理](create-a-phone-system-auto-attendant.md)

 - [云呼叫队列](create-a-phone-system-call-queue.md)

可以使用 " **编辑** " 选项编辑资源帐户的 " **显示名称** " 和 " **资源帐户** " 类型。 完成后单击 " **保存** "。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>更改现有资源帐户以使用虚拟用户许可证

如果你决定将现有资源帐户上的许可证从 **电话系统** 许可证切换到虚拟用户许可证，你将需要获取免费的虚拟用户许可证，然后按照 Microsoft 365 管理中心中的步骤 [将用户移动到其他订阅](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除完整的电话系统许可证，并在同一许可证活动中分配虚拟用户许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。 如果发生这种情况，我们建议你为虚拟用户许可证创建新的资源帐户，并删除断开的资源帐户。

## <a name="skype-for-business-server-2019"></a>Skype For Business 服务器2019

对于驻留在可与云呼叫队列和云自动助理一起使用的 Skype For business Server 2019 上的资源帐户，请参阅 [计划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。 在直接路由) 上 (号码的混合实现使用本地 Skype for business Server 2019 服务器上的 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet 进行配置。

创建应用程序实例时需要使用的应用程序 Id 如下：

- **自动助理：** ce933385-9390-45d1-9512-c8d228074e07
- **呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果您希望呼叫队列或自动助理可由 Skype For Business Server 2019 用户搜索，则应在 Skype For business Server 2019 上创建资源帐户，因为联机资源帐户未同步到 Active Directory。 当 sipfederationtls 的 DNS SRV 记录解析到 Skype for business Server 2019 时， **必须** 使用 SfB Management shell 并同步到 Azure AD，在 Skype For business server 2019 上创建资源帐户。

对于与 Skype for business 服务器混合的实现：

   [规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [规划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [配置本地资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>删除资源帐户

请确保在删除之前将电话号码与资源帐户取消关联，以避免让你的服务号码滞留在挂起模式下。

执行此操作后，您可以在 Microsoft 365 管理中心的 "用户" 选项卡下删除该资源帐户。

若要解除直接路由电话号码与资源帐户的关联，请使用以下 cmdlet：

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

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
description: 本文将了解如何在 Microsoft Teams 中创建、编辑和管理资源帐户。
ms.openlocfilehash: 8b58aae22afdff749e82ca67ff8b4a457f72b9de
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726641"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

资源帐户是 Azure AD 中已禁用的用户对象，通常可用于表示资源。 例如，资源帐户可用于Exchange会议室，并允许它们具有电话号码和日历。 可以使用 2019 年 Microsoft 365 将资源帐户Skype for Business Server本地。

在Microsoft Teams，每个自动助理或呼叫队列都需要一个资源帐户。 还可以为资源帐户分配服务电话号码。 这是将电话号码分配给自动助理和呼叫队列，允许来自外部呼叫者Teams自动助理或呼叫队列。

本文介绍如何创建资源帐户并准备好它们以用于自动助理和呼叫队列。

在开始本文中的过程之前，请确保已完成以下操作：

- [获取虚拟用户许可证](#obtain-virtual-user-licenses)
- [获取服务编号](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>获取虚拟用户许可证

每个资源帐户都需要许可证才能使用自动助理和呼叫队列。 可以使用免费的虚拟Microsoft 365 电话系统 *- 虚拟用户* 许可证。 若要获取这些许可证，请参阅 [虚拟用户许可证](teams-add-on-licensing/virtual-user.md)。

本文稍后将介绍如何将许可证分配给资源帐户。

若要获取虚拟用户许可证，Microsoft 365 管理中心，转到"计费购买服务加载项订阅"并滚动到末尾 - 会看到"电话系统  >    >  *- 虚拟用户* 许可证"。 选择"**立即购买"。** 成本为零，但仍需要按照以下步骤获取许可证。

### <a name="obtain-service-numbers"></a>获取服务编号

对于自动助理和呼叫队列，服务号码是可选的，但是，你至少需要一个服务号码，以便呼叫者能够联系你的自动助理和呼叫队列配置。 对于希望由服务号码直接访问的任何自动助理或呼叫队列，必须具有具有关联服务号码的资源帐户。

资源帐户可以使用收费或免费服务号码。 您可以请求其他运营商的新号码或移植现有号码。

若要获取新的服务号码，请参阅 [获取服务电话号码](getting-service-phone-numbers.md)。

若要转转其他运营商的号码，请参阅[将电话号码转移到Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="create-a-resource-account"></a>创建资源帐户

可以在管理中心内创建Teams帐户。

![添加资源帐户用户界面的屏幕截图。](media/resource-account-add.png)

1. 在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**

2. 单击“**添加**”。

3. 在"**添加资源帐户"** 窗格中，填写"**显示名称**、**用户名**"和"**资源帐户类型"。** 资源帐户类型可以是"自动 **助理"** 或"呼叫队列"，具体取决于你计划如何使用此资源帐户。

4. 单击“**保存**”。

![资源帐户列表的屏幕截图。](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>分配许可证

对于每个资源帐户，必须分配一个Microsoft 365 电话系统 *- 虚拟用户* 许可证或 *电话系统* 许可证。

!["许可证分配"用户界面的屏幕截图Microsoft 365 管理中心。](media/resource-account-assign-virtual-user-license.png)

1. 在Microsoft 365 管理中心，单击要为其分配许可证的资源帐户。

2. 在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**

3. 单击 **保存更改**。

## <a name="assign-a-service-number"></a>分配服务编号

如果计划将资源帐户与需要服务号码的自动助理或呼叫队列一同使用，请为资源帐户分配一个号码。

![分配服务编号用户界面的屏幕截图。](media/resource-account-assign-phone-number.png)

1. 在Teams管理中心的"资源帐户"页上，选择要为其分配服务编号的资源帐户，然后单击"**分配/取消分配"。**

2. 在 **电话类型**"下拉列表中，选择想要使用的编号类型。

3. 在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。**

4. 单击“**保存**”。


若要将直接路由或混合号码分配给资源帐户，需使用 PowerShell：

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>后续步骤

完成资源帐户设置并根据需要分配服务号码后，即可将资源帐户与自动助理或呼叫队列一同使用。

请参阅以下参考：

 - [云自动助理](create-a-phone-system-auto-attendant.md)

 - [云呼叫队列](create-a-phone-system-call-queue.md)

可以使用"编辑"选项编辑资源帐户显示 **名称和** 资源 **帐户** 类型。 完成后 **，** 单击"保存"。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>将现有资源帐户更改为使用虚拟用户许可证

如果决定将现有资源帐户上的许可证从 **电话系统** 许可证切换到虚拟用户许可证，则需要获取免费的虚拟用户许可证，然后按照 Microsoft 365 管理中心 中的步骤将用户移到其他 [订阅。](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> 始终删除完整的电话系统许可证，并在同一许可证活动中分配虚拟用户许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再正常运行。 如果发生这种情况，建议为虚拟用户许可证创建新的资源帐户，并删除损坏的资源帐户。

## <a name="skype-for-business-server-2019"></a>SkypeFor Business Server 2019

对于托管在 Skype For Business Server 2019 上且可用于云呼叫队列和云自动助理的资源帐户，请参阅计划云呼叫[队列](/SkypeforBusiness/hybrid/plan-call-queue)或[计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。 本地 (2019 服务器上使用[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet 配置了位于直接路由) 上的混合实现Skype for Business Server数字。

创建应用程序实例时需要使用的应用程序 ID 为：

- 自动助理：ce933385-9390-45d1-9512-c8d228074e07
- **呼叫队列** ：11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果希望呼叫队列或自动助理由 Skype For Business Server 2019 用户搜索，应在 Skype For Business Server 2019 上创建资源帐户，因为联机资源帐户不会同步到 Active Directory。 当 sipfederationtls 的 DNS SRV 记录解析为 Skype for Business Server 2019时，必须使用 SfB 命令行管理程序在 Skype For Business Server 2019 上创建资源帐户并同步到 Azure AD。

对于与应用混合Skype for Business Server：

   [规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [规划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [配置本地资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>删除资源帐户

在删除电话号码之前，请确保从资源帐户取消关联电话号码，以避免服务号码停滞在挂起模式。

执行该操作后，可以在"用户"选项卡下Microsoft 365 管理中心资源帐户。

若要取消关联资源帐户的直接路由电话号码，请使用以下 cmdlet：

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
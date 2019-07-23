---
title: 在 Teams 中管理资源帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: 了解有关在 Microsoft 团队中管理资源帐户的信息
ms.openlocfilehash: 1dd3fd8c7a9300b9c887cbc0c3cd3611b378d0c9
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821059"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

资源帐户在 Azure Active Directory 中也称为*已禁用的用户对象*, 并且可用于表示常规资源。 例如, 在 Exchange 中, 它可能用于表示会议室, 并允许他们拥有电话号码。 资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。

在 Microsoft 团队或 Skype for business Online 中, 每个电话系统呼叫队列或自动助理都必须具有关联的资源帐户。 资源帐户是否需要分配的电话号码取决于关联呼叫队列或自动助理的预期用途。 在将电话号码分配给资源帐户之前, 请参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。 对于驻留在 Skype for business Server 2019 上的资源帐户, 请参阅[配置资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)。


## <a name="overview"></a>概述

假设您的组织至少使用一个电话系统许可证, 若要为电话号码分配电话号码, 您需要按以下顺序解决各种相关性:

1. 获取服务号码。
2. 获取用于资源帐户的电话系统[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或普通电话系统许可证。
3. 创建资源帐户。 需要使用自动助理或呼叫队列才能拥有关联的资源帐户。
4. 将电话系统或电话系统虚拟用户许可证分配给资源帐户。
5. 将服务电话号码分配给您刚向其分配许可证的资源帐户。
6. 创建电话系统服务 (呼叫队列或自动助理)。
7. 将资源帐户与服务链接。

如果自动助理或呼叫队列嵌套在顶级自动助理下方, 并且如果你希望将多个点输入到自动助理的结构中并调用队列, 则关联的资源帐户仅需要电话号码。

若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> 为了避免资源帐户出现问题, 请按照此顺序执行这些步骤。

如果你要创建的电话系统服务将嵌套, 并且不需要电话号码, 则过程如下:

1. 创建资源帐户  
2. 创建电话系统服务
3. 将资源帐户与电话系统服务相关联

### <a name="create-a-resource-account-with-a-phone-number"></a>使用电话号码创建资源帐户

创建使用电话号码的资源帐户需要按以下顺序执行以下任务:

1. 或获取收费或免费服务号码。 该号码不能分配给任何其他语音服务或资源帐户。

   将电话号码分配给资源帐户之前, 您需要购买或移植您现有的收费或免费服务号码。 获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。 若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。

   如果您要为资源帐户分配电话号码, 您现在可以使用免费的电话系统虚拟用户许可证。 这将为组织级别的电话号码提供电话系统功能, 并允许你创建自动助理和呼叫队列功能。

2. 获取电话系统虚拟用户许可证或普通的电话系统许可证。 

   若要获取虚拟许可证, 请从 Microsoft 365 管理中心转到**帐单** > **购买服务** > **附加订阅**并滚动到 "结束", 你将看到 "电话系统-虚拟用户" 许可证。 选择 "**立即购买**"。 成本不为零, 但仍需按照这些步骤获取许可证。
3. 创建新的资源帐户。 请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)
4. 将[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或电话系统许可证分配给资源帐户。 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。
5. 将服务号码分配给资源帐户。 请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。
6. 设置下列内容之一:
   - [云自动助理](create-a-phone-system-auto-attendant.md)
   - [云呼叫队列](create-a-phone-system-call-queue.md)
7. 将资源帐户链接到自动助理或呼叫队列。 请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)

### <a name="create-a-resource-account-without-a-phone-number"></a>创建不带电话号码的资源帐户

创建不需要电话号码的资源帐户需要按以下顺序执行以下任务:

1. 创建新的资源帐户。 请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)
2. 设置下列内容之一:
   - [云自动助理](create-a-phone-system-auto-attendant.md)
   - [云呼叫队列](create-a-phone-system-call-queue.md)
3. 将资源帐户分配给服务。 请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中创建资源帐户

购买电话系统许可证后, 使用 Microsoft 团队管理中心导航到**组织范围的设置** > **资源帐户**。

!["资源帐户" 页面的屏幕截图](media/r-a-master.png)

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

若要创建新的资源帐户, 请单击 " **+ 新建帐户**"。 在弹出窗口中, 填写资源帐户的 "显示名称" 和 "用户名" (域名应自动填充), 然后单击 "**保存**"。

![新资源帐户选项的屏幕截图](media/res-acct.png)

接下来, 在 O365 管理中心中对资源帐户应用许可证, 如在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述。

### <a name="edit-resource-account-name"></a>编辑资源帐户名称

![数字2的图标, 引用上一个屏幕截图](media/sfbcallout2.png)中的标注, 您可以使用 "**编辑**" 选项编辑资源帐户的显示名称。  完成后单击 "**保存**"。
!["编辑资源帐户" 选项的屏幕截图](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>分配/取消分配电话号码和服务

![数字3的图标, 在以前的屏幕截图](media/sfbcallout3.png)中引用标注一旦创建了资源帐户并分配了许可证, 您可以单击 "**分配/取消**分配" 以将服务编号分配给资源帐户, 或分配资源帐户到已存在的自动助理或呼叫队列。 分配直接路由号码只能使用 Cmdlet 完成。 如果您的通话队列或自动助理仍需创建, 则可以在创建资源帐户时将其链接在一起。 完成后单击 "**保存**"。

若要将直接路由或混合号码分配给资源帐户, 您需要使用 PowerShell, 请参阅以下部分。

> [!IMPORTANT]
> 如果你的资源帐户没有虚拟用户或电话系统许可证, 则当你尝试将电话号码分配给资源帐户时, 内部检查将导致失败。 您无法分配该号码或将资源帐户与服务相关联。

!["分配/取消分配" 选项的屏幕截图](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>更改现有资源帐户以使用虚拟用户许可证

如果你决定将现有资源帐户上的许可证从电话系统许可证切换到虚拟用户许可证, 你需要 aquire "免费虚拟用户" 许可证, 然后按照 Microsoft 365 管理中心中的链接步骤[将用户移动到不同的订阅](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)。 

> [!WARNING]
> 始终删除完整的电话系统许可证, 并在同一许可证活动中分配虚拟用户许可证。 如果删除旧许可证, 请保存帐户更改, 添加新许可证, 然后再次保存帐户设置, 资源帐户可能不再按预期运行。 如果发生这种情况, 我们建议你为虚拟用户许可证创建新的资源帐户, 并删除断开的资源帐户。 

## <a name="create-a-resource-account-in-powershell"></a>在 Powershell 中创建资源帐户

你需要通过管理员权限连接到相应的 Powershell 提示, 具体取决于你的资源帐户是否位于联机或本地。

- 以下 Powershell cmdlet 示例假定资源帐户使用[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)进行联机托管, 以创建联机的资源帐户。

- 对于驻留在 Skype For business Server 2019 (可与云呼叫队列和云自动助理配合使用) 的本地资源帐户, 请参阅[配置云呼叫队列](/skypeforbusiness/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)。 混合实现 (直接路由上的号码) 将使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。

创建应用程序实例时需要使用的应用程序 ID 如下:

- **自动助理:** ce933385-9390-45d1-9512-c8d228074e07
- **呼叫队列:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果您希望呼叫队列或自动助理可由本地用户搜索, 您应该在本地创建资源帐户, 因为联机资源帐户没有同步到 Active Directory。

1. 若要创建联机的资源帐户以与自动助理配合使用, 请使用以下命令。  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. 你将无法使用资源帐户, 直到你向其应用许可证。 有关如何将许可证应用到 O365 管理中心中的帐户, 请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。

3. 可选将正确的许可证应用到资源帐户后, 您可以将电话号码设置为资源帐户, 如下所示。 并非所有资源帐户都需要电话号码。 如果未对资源帐户应用许可证, 则电话号码分配将失败。

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

有关此命令的详细信息, 请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。

> [!NOTE]
> 最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码, 如上文所述。

若要将直接路由或混合号码分配给资源帐户, 请使用以下 cmdlet:

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理资源帐户设置

若要在 Microsoft 团队管理中心中管理资源帐户设置, 请导航到 "**组织范围的设置**  > "**资源帐户**, 选择要更改其设置所需的资源帐户, 然后单击 "**编辑**" 按钮。 在 "**编辑资源帐户**" 屏幕中, 你将能够更改这些设置:

- 帐户的**显示名称**
- 呼叫队列或使用该帐户的自动助理
- 分配给帐户的电话号码

完成后, 单击 "**保存**"。

## <a name="delete-a-resource-account"></a>删除资源帐户

请确保在删除之前将电话号码与资源帐户取消关联, 以避免让你的服务号码滞留在挂起模式下。 你可以使用以下 commandlet 执行此操作:

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

执行此操作后, 您可以从 O365 管理门户删除资源帐户, 在 "用户" 选项卡下。

## <a name="troubleshooting"></a>疑难解答

如果您没有看到分配给团队管理中心中的资源帐户的电话号码, 并且您无法分配该号码, 请检查以下事项:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

如果 "部门" 属性显示 Skype for Business 应用程序终结点, 请运行以下 cmdlet:

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> 在运行 cmldet 后刷新团队管理中心网页, 您应该能够正确分配号码。

## <a name="related-information"></a>相关信息

对于与 Skype for business 服务器混合的实现:

   [规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [规划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [配置本地资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)


对于团队或 Skype for Business Online 中的实施:

   [什么是云自动助理？](what-are-phone-system-auto-attendants.md)

   [设置云自动助理](/microsoftteams/create-a-phone-system-auto-attendant)

   [小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)

   [创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)

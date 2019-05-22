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
ms.openlocfilehash: f2c7b03f79a29b89c94266359f21571b1994e82a
ms.sourcegitcommit: 4b8350e5bb2ef138dcc0204d764bdf85bae539ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "34334924"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

资源帐户在 Azure Active Directory 中也称为已禁用的用户对象, 并且可用于表示常规资源。 例如, 在 Exchange 中, 它可能用于表示会议室, 并允许他们拥有电话号码。 资源帐户可以托管在 Microsoft 365 中, 也可以在本地使用 Skype for Business 服务器托管, 这些帐户使用 Powershell 命令创建。

在 Microsoft 团队或 Skype for business Online 中, 每个呼叫队列或自动助理都必须具有关联的资源帐户。 资源帐户是否需要分配的电话号码取决于关联呼叫队列或自动助理的预期用途。 在将电话号码分配给资源帐户之前, 请参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。 对于驻留在 Skype for business Server 2019 上的资源帐户, 请参阅[配置云自动助理](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)。

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>将电话号码分配给资源帐户的先决条件

若要开始使用, 请务必记住以下几点:
  
- 需要使用自动助理或呼叫队列才能拥有关联的资源帐户。 
- 如果资源帐户将分配给顶层自动助理或呼叫队列, 则该帐户将需要已分配的电话号码。 
- 如果自动助理或呼叫队列嵌套在顶级自动助理下方, 并且如果你希望将多个点输入到自动助理的结构中并调用队列, 则关联的资源帐户仅需要电话号码。
- 您只需向分配了电话号码的资源帐户授予许可证。 在嵌套的自动助理或呼叫队列中, 如果自动助理或呼叫队列没有与之关联的电话号码, 则无需向其授予许可证。
- 如果您分配的电话号码与直接路由一起使用, 并且您有企业版 E1 或 E3 许可证, 则必须购买并向您分配电话系统许可证, 您就是要使用的资源帐户。 如果您有企业版 E5 许可证, 则电话系统已包含, 因此无需购买一个。 
- 如果你改为分配 Microsoft 服务号码, 你需要使用手机系统加载项和呼叫计划\(\)获取并将以下许可证分配给你的资源帐户 Office 365 企业版 E1、E3 或 E5。
- 您可以为您的资源帐户分配直接路由混合号码。  有关详细信息, 请参阅[规划直接路由](direct-routing-plan.md)。
- 对于 Microsoft 通话计划, 您只能将您在**Microsoft 团队管理中心**或从其他服务提供商移植到资源帐户的收费电话号码和免费服务电话号码分配给您。 若要获取并使用免费电话号码，则需要设置通信点数。

> [!NOTE]
> 仅为 Microsoft 团队用户和代理支持分配给自动助理和呼叫队列的资源帐户的直接路由服务号码。
>
> Microsoft 正在为应用程序 (如云自动助理和呼叫队列) 处理合适的许可模型, 现在你需要使用用户许可模型。
>
> 若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
>
> 用户 (订阅者) 电话号码不能分配给资源帐户。 仅可使用收费电话或免费电话号码。
>
> 如果您在美国以外, 则不能使用 Microsoft 团队管理中心获取服务号码。 转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。

### <a name="phone-numbers"></a>电话号码

创建使用电话号码的资源帐户需要按以下顺序执行以下任务:

1. 转接或获取收费或免费服务号码。 该号码不能分配给任何其他语音服务或资源帐户。

   将电话号码分配给资源帐户之前, 您需要购买或移植您现有的收费或免费服务号码。 获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。 若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。

2. 购买电话系统许可证和通话计划。 参阅  
   - [Office 365 企业版（E1 和 E3）](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 企业版 E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Office 365 企业版 E5 Business 软件](https://products.office.com/business/office-365-enterprise-e5-business-software)- [通话计划 (适用于 office 365](calling-plans-for-office-365.md) )

3. 创建新的资源帐户。 请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)
4. 将电话系统许可证和呼叫计划分配给资源帐户。 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。
5. 将服务号码分配给资源帐户。 请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。

不需要电话号码的资源帐户可以忽略步骤1、2和5。

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中创建资源帐户

购买电话系统许可证和呼叫计划之后, 使用 Microsoft 团队管理中心, 导航到**组织范围的设置** > **资源帐户**。 

![.asd](media/r-a-master.png)

![数字1](media/sfbcallout1.png)

若要创建新的资源帐户, 请单击 " **+ 新建帐户**"。 在弹出窗口中, 填写资源帐户的 "显示名称" 和 "用户名" (域名应自动填充), 然后单击 "**保存**"。

![资源帐户](media/res-acct.png)

接下来, 在 O365 管理中心中对资源帐户应用许可证, 如在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述。

### <a name="assignunassign-phone-numbers-and-services"></a>分配/取消分配电话号码和服务

![编号 3](media/sfbcallout3.png)创建资源帐户并分配许可证后, 您可以单击 "**分配/取消**分配" 将呼叫计划服务编号分配给资源帐户, 或者将资源帐户分配给指定的自动助理或呼叫队列已存在。 分配直接路由号码只能使用 Cmdlet 完成。 如果您的通话队列或自动助理仍需创建, 则可以在创建资源帐户时将其链接在一起。 完成后单击 "**保存**"。

使用以下 cmdlet 分配直接路由号码: 
``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

> [!IMPORTANT]
> 如果你的租户尚未购买电话系统许可证和呼叫计划, 则当你尝试将电话号码分配给资源帐户时, 内部检查将导致失败。 您无法分配该号码或将资源帐户与服务相关联。

![资源帐户分配](media/r-a-assign.png)

![数字 2](media/sfbcallout2.png)您可以使用 "**编辑**" 选项编辑资源帐户的显示名称。  完成后单击 "**保存**"。
![编辑资源帐户](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>在 Powershell 中创建资源帐户

对于 Microsoft 通话计划, 您只能将您在**Microsoft 团队管理中心**或从其他服务提供商移植到资源帐户的收费电话号码和免费服务电话号码分配给您。 若要获取并使用免费电话号码，则需要设置通信点数。

你需要通过管理员权限连接到相应的 Powershell 提示, 具体取决于你的资源帐户是否位于联机或本地。 
- 以下 Powershell cmdlet 示例假定资源帐户使用[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)进行联机托管, 以创建联机的资源帐户。

- 对于驻留在 Skype For business Server 2019 (可与云呼叫队列和云自动助理配合使用) 的本地资源帐户, 请参阅[配置云呼叫队列](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)。 混合实现 (直接路由上的号码) 将使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。

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
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

有关此命令的详细信息, 请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。

> [!NOTE]
> 最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码, 如上文所述。

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

## <a name="related-information"></a>相关信息

对于与 Skype for business 服务器混合的实现:

[规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[配置云自动助理](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

对于团队或 Skype for Business Online 中的实施:

[什么是云自动助理？](what-are-phone-system-auto-attendants.md)

[设置云自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)

[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

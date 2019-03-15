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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: 管理资源中的 Microsoft 团队的帐户
ms.openlocfilehash: dad2ea10f2dbdeb387a74d01fd48ca6de9805a5a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633247"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

资源帐户也称为 Azure Active Directory 中的已禁用的用户对象，可以用于通常表示资源。 在 Exchange 它可能用于表示会议室，例如，并允许有一个电话号码。 在 Microsoft 365 或本地的企业服务器，使用 Skype 可托管资源帐户并使用 Powershell 命令创建这些帐户。

在 Microsoft 团队或 Skype 业务联机，每个呼叫队列或自动助理需要具有关联的资源帐户。 资源帐户是否需要分配的电话号码将取决于打算使用的关联的呼叫队列或自动助理。 引用上调用队列的文章和自动助理电话号码分配给资源帐户之前底部这篇文章的链接。

> [!NOTE]
> 本文同时适用于 Microsoft 团队和 Skype 业务 online。

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>若要将电话号码分配给资源帐户的先决条件

若要开始非常重要记住几件事：
  
- 企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。 已分配的**电话系统**用户许可证数影响服务号码可用于资源帐户分配给队列或自动助理呼叫的号码。 取决于您的组织中分配的**电话系统**和**音频会议**的许可证数量的资源帐户，您可以数。 若要了解有关授权的详细信息，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    > [!NOTE]
    > 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。 请参阅[分配的 Microsoft 团队许可证](assign-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 调用计划的详细信息，请参阅[Office 365 调用计划](calling-plans-for-office-365.md)。
- 您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或从另一个服务提供商转接到的资源帐户。 若要获取并使用免费电话号码，则需要设置通信点数。

> [!NOTE]
> 用户 （订阅服务器） 的电话号码不能分配给资源帐户。 可以使用只有服务收费电话或免费电话号码。

若要将电话号码分配给资源帐户，您需要用于获取或转移您现有的收费电话或免费电话服务号码。 获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话****号码类型**列出将。 若要获取服务号码，请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)或如果您想要传输的现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。 转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。

## <a name="create-a-resource-account-in-powershell"></a>在 Powershell 中创建资源帐户

 您可以通过根据 （对于一个或多个资源帐户），需要运行相应 Powershell cmdlet 创建资源帐户，并为每个命名，依此类推。 当前没有在 Microsoft 团队管理中心中创建资源帐户的选项，但您可以编辑电话号码和更改的呼叫队列或自动助理分配资源帐户。

根据您的电话号码是否位于联机或本地，您需要连接到相应的 Powershell 提示符处，具有管理员权限。

- 混合实现 （号码号码驻留在直接路由、 OPCH 和 CCE） 将使用[新建 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)创建驻留在本地资源帐户。  
- 联机仅实现将使用[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)具有联机驻留的资源帐户。

以下是创建资源帐户的 online 环境示例：

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

在此命令的详细信息，请参阅[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) 。

> [!NOTE]
> 是最容易设置电话号码使用的 Microsoft 团队管理中心下, 一节中所述。 您还可以使用`Set-CsOnlineApplicationInstance`命令分配到的资源帐户电话号码其首次创建后所示：

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

在此命令的详细信息，请参阅[设置 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) 。

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>管理资源的 Microsoft 团队管理中心中的帐户设置

若要管理资源帐户设置的 Microsoft 团队管理中心中，导航到**组织范围的设置**  > **资源帐户**和选择资源帐户所需更改设置，然后单击**编辑**按钮。 在**编辑资源帐户**屏幕中，您都将能够更改:

- 该帐户的**显示名称**
- 呼叫队列或自动助理使用的帐户
- 分配给该帐户的电话号码

完成后，单击在**保存**。

## <a name="related-information"></a>相关的信息

为实现的混合与 Skype 的业务服务器：

[规划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[配置云自动助理](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

对于业务 online 团队或 Skype 中实现：

[什么是电话系统自动助理？](what-are-phone-system-auto-attendants.md)

[设置电话系统自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[小型企业示例 - 设置自动助理](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[创建电话系统呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

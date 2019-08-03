---
title: 在 Skype for Business Server 2019 中配置资源帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 为 Skype for business Server 2019 设置资源帐户。
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160468"
---
# <a name="configure-resource-accounts"></a>配置资源帐户

Skype for Business Server 2019 混合实施仅使用电话系统提供的用于统一消息的云服务, 不与 Exchange Online 集成。 在 Skype for Business Server 2019 中, 你现在可以使用[Office 365 中的电话系统获取](/MicrosoftTeams/here-s-what-you-get-with-phone-system)的云呼叫队列和自动助理。

若要将这些电话系统服务与 Skype for Business Server 2019 一起使用, 您需要创建充当应用程序终结点且可分配电话号码的资源帐户, 然后使用联机团队管理中心配置呼叫队列或自动助理。 此资源帐户可以联机 (请参阅[在 Microsoft 团队中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)以创建驻留在联机状态的资源帐户) 或本地, 如本文中所述。 通常会有多个电话系统服务节点, 每个节点都映射到可联机或在 Skype for Business Server 2019 中的资源帐户。

如果你有一个现有的 Exchange UM 自动助理和呼叫队列系统, 则在切换到 Exchange Server 2019 或 Exchange online 之前, 你需要手动记录详细信息, 然后使用团队管理中心实施全新的系统.

## <a name="overview"></a>概述

如果您的电话系统服务需要服务号码, 则可以按以下顺序满足各种依存关系:

1. 获取服务号码
2. 购买电话系统许可证
3. 创建资源帐户。 自动助理或呼叫队列必须具有关联的资源帐户。
4. 在联机和本地之间等待 active directory 同步
5. 将电话系统许可证分配给资源帐户。
6. 向资源帐户分配服务号码。
7. 创建电话系统服务 (呼叫队列或自动助理)
8. 将资源帐户与服务关联: (CsApplicationInstanceAssociation)

如果自动助理或呼叫队列嵌套在顶级自动助理下, 则关联的资源帐户只需要一个电话号码, 如果您希望将多个点输入到自动助理和呼叫队列的结构中。

若要将呼叫重定向到组织中已联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话套餐。 请参阅[分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)。 若要为企业语音启用它们, 可以使用 Windows PowerShell。 例如, 运行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果要创建的电话系统服务将嵌套, 并且不需要电话号码, 则该过程为:

1. 创建资源帐户  
2. 在联机和本地之间等待 active directory 同步
3. 创建电话系统服务
4. 将资源帐户与电话系统服务关联

## <a name="create-a-resource-account-with-a-phone-number"></a>创建具有电话号码的资源帐户

若要创建使用电话号码的资源帐户, 需要按以下顺序执行以下任务:

1. 端口或获取收费或免费服务号码。 该号码不能分配给任何其他语音服务或资源帐户。

   在向资源帐户分配电话号码之前, 需要获取或移植现有收费或免费服务号码。 获取收费或免费服务电话号码后, 它们将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将列为 "**服务-免费**"。 若要获取服务号码, 请参阅[获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers); 如果要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365)。

   如果你在美国之外, 则无法使用 Microsoft 团队管理中心获取服务号码。 转到 "[管理你的组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)", 以了解如何从美国以外的地区执行此操作。

2. 购买电话系统许可证。 请参阅：  
   - [Office 365 企业版 E1 和 E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企业版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企业版 E5 商业版软件](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 通过对每个电话系统服务运行`New-CsHybridApplicationEndpoint` cmdlet 来创建本地资源帐户, 并为每个帐户分配一个名称、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关此命令的更多详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

4. Optional创建资源帐户后, 您可以等待 AD 在联机和本地之间同步, 或者强制进行同步并继续进行电话系统服务的联机配置。 若要强制进行同步, 请在运行 AAD 连接的计算机上运行以下命令 (如果尚未执行此操作, 则需要加载`import-module adsync`才能运行该命令):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关此命令的更多详细信息, 请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

5. 将电话系统许可证分配给资源帐户。 请参阅[分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。

    如果要将电话号码分配给资源帐户, 现在可以使用免费电话系统虚拟用户许可证。 这样可以在组织级别为电话号码提供电话系统功能, 并允许您创建自动助理和呼叫队列功能。


6. 向资源帐户分配服务号码。 使用`Set-CsHybridApplicationEndpoint`命令将电话号码 (带有-LineURI 选项) 分配给资源帐户。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    有关此命令的详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。

    若要向资源帐户分配直接路由或混合号码, 请使用以下 cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

如果资源帐户将分配给顶级自动助理或呼叫队列, 则该帐户将需要已分配的电话号码。 无法将用户 (订阅者) 电话号码分配给资源帐户, 只能使用服务收费或免费电话号码。

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. 创建电话系统服务。 请查看下列内容之一：

   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 将资源帐户与以前选择的电话系统服务相关联。

小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。

## <a name="create-a-resource-account-without-a-phone-number"></a>创建不带电话号码的资源帐户

本节讨论如何创建驻留在本地的资源帐户。 在[Microsoft 团队中的 "管理资源帐户" 中](/MicrosoftTeams/manage-resource-accounts)讨论了如何创建驻留在联机状态的资源帐户。

无论您是创建全新的电话系统服务系统, 还是在 Exchange UM 中最初创建的结构重建, 都必须执行这些步骤。

登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet:

1. 通过对每个电话系统服务运行`New-CsHybridApplicationEndpoint` cmdlet 来创建本地资源帐户, 并为每个帐户分配一个名称、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关此命令的更多详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

2. Optional创建资源帐户后, 您可以等待 AD 在联机和本地之间同步, 或者强制进行同步并继续进行电话系统服务的联机配置。 若要强制进行同步, 请在运行 AAD 连接的计算机上运行以下命令 (如果尚未执行此操作, 则需要加载`import-module adsync`才能运行该命令):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关此命令的更多详细信息, 请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

3. 创建电话系统服务。 请查看下列内容之一：
   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 关联以前选择的资源帐户和电话系统服务。

小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。

## <a name="test-the-implementation"></a>测试实现

测试实现的最佳方式是调用为电话系统服务配置的号码, 并连接到其中一个代理或菜单。 您还可以通过使用管理中心操作窗格中的 "**测试" 按钮**来快速发出测试呼叫。 如果要对电话系统服务进行更改, 请选择它, 然后在操作窗格中单击 "**编辑**"。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>将 Exchange UM 自动助理或呼叫队列移动到电话系统

从 Exchange UM 迁移到电话系统将需要重新创建呼叫队列和自动助理结构, 而不支持直接从一个迁移到另一个。 若要重新实现一组呼叫队列和自动助理, 请执行以下操作:

1. 在以管理员身份登录时, 通过在 Exchange 2013 或2016系统上运行以下命令来获取所有 Exchange UM 自动助理和呼叫队列的列表:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 对于每个列出的 Exchange UM 呼叫队列或自动助理, 请注意其在结构中的位置、设置, 以及获取关联的声音或文本到语音转换文件的副本 (输出中的 guid 将是存储文件的文件夹的名称)。 可以通过运行以下命令获取这些详细信息:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    有关此命令的详细信息, 请参阅[get-umautoattendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。 您可能需要捕获的选项的完整列表是在[get-umautoattendant 成员](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)处, 但要注意的最重要的选项是:

    - 营业时间
    - 非工作时间
    - Language
    - 假日日程安排

3. 按照前面所述, 创建新的本地终结点。
   为顶级自动助理分配一个用于测试目的的临时编号。

4. 配置使用前面所述的终结点的电话系统服务。

   您可能会发现, 在教程中使用标题为 "小型企业版" 的练习,[设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml), 以创建旧 Exchange UM 系统中的层次结构的逻辑地图。
5. 测试电话系统服务。
6. 将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统服务。  

   在这种情况下, 如果您已经迁移了 UM 语音邮件, 则应在迁移到 Exchange Server 2019 的位置。

## <a name="see-also"></a>另请参阅

[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什么是云自动助理？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[规划云自动助理](plan-cloud-auto-attendant.md)

[规划云呼叫队列](plan-call-queue.md)

[为本地用户规划云语音邮件服务](plan-cloud-voicemail.md)

[新 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[在 Microsoft 团队](/MicrosoftTeams/manage-resource-accounts) - \(中管理资源帐户以创建托管联机的资源帐户\)

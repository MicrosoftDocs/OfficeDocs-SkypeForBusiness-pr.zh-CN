---
title: 在 Skype for Business Server 2019 中配置资源帐户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 为 Skype for Business Server 2019 设置资源帐户。
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919008"
---
# <a name="configure-resource-accounts"></a>配置资源帐户

Skype for Business Server 2019 混合实现仅将电话系统提供的云服务用于统一消息，不与 Exchange Online 集成。 在 Skype for Business Server 2019 中，你现在可以使用 Microsoft [365 或 Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)中的电话系统功能中所述的云呼叫队列和自动助理。

若要将电话系统自动助理或呼叫队列与 Skype for Business Server 2019 一同使用，你需要创建充当应用程序终结点的资源帐户，并可以分配电话号码，然后使用联机 Teams 管理中心配置呼叫队列或自动助理。 此资源帐户可以联机 ([在 Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) 中管理资源帐户，以创建联机或本地) 资源帐户，如本文所述。 通常，你将具有多个电话系统自动助理或呼叫队列节点，每个节点都映射到可联机或位于 Skype for Business Server 2019 中的资源帐户。

如果您有现有的 Exchange UM 自动助理和呼叫队列系统，在切换到 Exchange Server 2019 或 Exchange Online 之前，您需要手动记录详细信息，如下所述，然后使用 Teams 管理中心实现全新的系统。

## <a name="overview"></a>概述

如果电话系统自动助理或呼叫队列需要服务号码，可以按以下顺序满足各种依赖关系：

1. 获取服务号码。
2. 获取免费电话系统 - [虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 或付费电话系统许可证，以用于资源帐户。
3. 创建资源帐户。 自动助理或呼叫队列需要具有关联的资源帐户。
4. 等待联机和本地之间的 Active Directory 同步。
5. 将电话系统许可证分配给资源帐户。
6. 为资源帐户分配服务号码。
7. 创建电话系统呼叫队列或自动助理。
8. 将资源帐户与自动助理或呼叫队列关联： (New-CsApplicationInstanceAssociation) 。

如果自动助理或呼叫队列嵌套在顶级自动助理下，则如果你希望自动助理和呼叫队列的结构中有多个入口点，则关联的资源帐户只需要一个电话号码。

若要将呼叫重定向到组织中在线用户，他们必须拥有电话系统许可证，并且必须启用企业语音 或具有 Microsoft 365 或 Office 365 通话套餐。 请参阅 [分配 Microsoft Teams 许可证](/MicrosoftTeams/assign-teams-licenses)。 若要为用户启用企业语音，可以使用Windows PowerShell。 例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果要创建的电话系统自动助理或呼叫队列将嵌套，并且不需要电话号码，则过程为：

1. 创建资源帐户  
2. 等待联机和本地之间的 Active Directory 同步
3. 创建电话系统自动助理或呼叫队列
4. 将资源帐户与电话系统自动助理或呼叫队列关联

## <a name="create-a-resource-account-with-a-phone-number"></a>创建具有电话号码的资源帐户

创建使用电话号码的资源帐户需要按以下顺序执行以下任务：

1. 移植或获取收费或免费服务号码。 无法将号码分配给任何其他语音服务或资源帐户。

   在将电话号码分配给资源帐户之前，你需要获取或移植现有的收费或免费服务号码。 获取收费或免费服务电话号码后，它们会显示在 **Microsoft Teams** 管理中心语音电话号码中，列出的号码类型将列为"服务  >    >  **- 免费"。**  若要获取服务号码，请参阅["获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers)"，或者如果你想要转移现有服务号码，请参阅"将电话号码转移到[Teams"。](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   如果你在美国之外，则你无法使用 Microsoft Teams 管理中心获取服务号码。 转到 ["管理组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) "，以查看如何从美国以外的国家/地区进行管理。

2. 购买电话系统许可证。 请参阅：  
   - [电话系统–虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 企业版（E1 和 E3）](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企业版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企业版 E5 商业版软件](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 通过为每个电话系统自动助理或呼叫队列运行 cmdlet 创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4.  (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，也可以强制同步并继续电话系统自动助理或呼叫队列的联机配置。 若要强制同步，需要在运行 AAD Connect (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行此命令 `import-module adsync`) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    请注意，此时，帐户可能已同步，但设置可能不完整。  检查 [Get-CsOnlineApplicationEndpoint 的输出](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)。  如果同步的终结点尚未完成预配，则它将不会在此处显示。  可以在"Teams 设置状态"下检查 M365 门户中的预配 [请求的状态](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。  此预配阶段最多可能需要 24 小时。

5. 将电话系统 - 虚拟用户或电话系统许可证分配给资源帐户。 请参阅["分配 Microsoft Teams 附加许可证"和](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)["向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   如果要将电话号码分配给资源帐户，现在可以使用免费电话系统 - 虚拟用户许可证。 这将为组织级别的电话号码提供电话系统功能，并允许创建自动助理和呼叫队列功能。


6. 将服务号码分配给资源帐户。 使用 `Set-CsHybridApplicationEndpoint` 此命令为资源帐户分配 (-LineURI 选项) 分配电话号码。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    有关[此命令的更多详细信息，请参阅 Set-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    若要将直接路由或混合号码分配给资源帐户，请使用以下 cmdlet：

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   如果将资源帐户分配给顶级自动助理或呼叫队列，则该帐户将需要分配的电话号码。 用户 (订阅者) 电话号码无法分配给资源帐户，只能使用收费或免费服务电话号码。

     你可以将直接路由或混合号码分配给你的资源帐户。 有关详细信息，请参阅["规划直接路由"和](/MicrosoftTeams/direct-routing-plan)["规划云自动助理"。](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > 分配给自动助理和呼叫队列的资源帐户的直接路由服务号码仅受 Microsoft Teams 用户和代理支持。

7. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：

   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 将资源帐户与之前选择的电话系统自动助理或呼叫队列关联。

## <a name="create-a-resource-account-without-a-phone-number"></a>创建没有电话号码的资源帐户

本节讨论创建本地资源帐户。 在 Microsoft Teams 中管理资源帐户时，将讨论创建联机管理 [的资源帐户](/MicrosoftTeams/manage-resource-accounts)。

无论是创建全新的电话系统自动助理或呼叫队列结构，还是重建最初在 Exchange UM 中创建的结构，这些步骤都是必需的。

登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet：

1. 通过为每个电话系统自动助理或呼叫队列运行 cmdlet 创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2.  (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，也可以强制同步并继续电话系统自动助理或呼叫队列的联机配置。 若要强制同步，需要在运行 AAD Connect (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行 `import-module adsync`) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：
   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 将资源帐户与之前选择的电话系统自动助理或呼叫队列关联。

## <a name="test-the-implementation"></a>测试实现

测试实现的最佳方法就是呼叫为电话系统自动助理或呼叫队列配置的号码，并连接到其中一个代理或菜单。 您还可以使用管理中心操作窗格中的"测试"按钮快速进行测试呼叫。 如果要对电话系统自动助理或呼叫队列进行更改，请选择它，然后在操作窗格中单击"编辑 **"。** 

> [!TIP]
> 如果你的资源帐户在被分配到呼叫队列或自动助理时有困难，请参阅[Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)的已知问题和 Microsoft Teams[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)博客中的"如何修复我的混合应用程序实例"部分。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>将 Exchange UM 自动助理或呼叫队列移动到电话系统

从 Exchange UM 迁移到电话系统需要重新创建呼叫队列和自动助理结构，不支持从一个直接迁移到另一个。 重新实现一组呼叫队列和自动助理：

1. 以管理员身份登录时，在 Exchange 2013 或 2016 系统上运行以下命令，获取所有 Exchange UM 自动助理和呼叫队列的列表：

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 对于每个列出的 Exchange UM 呼叫队列或自动助理，记下其在结构、设置中的位置，并获取关联声音或文本到语音到语音文件的副本 (输出中的 guid 将为存储文件的文件夹的名称) 。 可以通过运行以下命令获取这些详细信息：

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    有关[此命令的更多详细信息，请参阅 Get-UMAutoAttendant。](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 可能需要捕获的选项的完整列表位于 [UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 成员中，但需要记下的最重要的选项是：

    - 营业时间
    - 非营业时间
    - 语言
    - 假日日程安排

3. 如前文所述创建新的本地终结点。
   为顶级自动助理分配一个临时号码以进行测试。

4. 配置使用终结点的电话系统自动助理或呼叫队列，如前面所述。

5. 测试电话系统自动助理或呼叫队列。

6. 将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统自动助理或呼叫队列。  

   此时，如果已迁移 UM 语音邮件，则应该可以迁移到 Exchange Server 2019。

## <a name="see-also"></a>另请参阅

[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什么是云自动助理？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[规划云自动助理](plan-cloud-auto-attendant.md)

[规划云呼叫队列](plan-call-queue.md)

[为本地用户规划云语音邮件服务](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[在 Microsoft Teams 中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)  -  \(创建联机管理的资源帐户\)

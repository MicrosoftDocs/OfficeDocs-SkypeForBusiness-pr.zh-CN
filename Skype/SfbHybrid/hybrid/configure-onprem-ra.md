---
title: 在 2019 Skype for Business Server配置资源帐户
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
ms.localizationpriority: medium
ms.collection: ''
description: 为 Skype for Business Server 2019 设置资源帐户。
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615608"
---
# <a name="configure-resource-accounts"></a>配置资源帐户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server 2019 混合实现仅使用电话系统提供的云服务进行统一消息传送，且不与Exchange Online集成。 在 2019 Skype for Business Server，你现在能够使用 [Microsoft 365 或 Office 365中的电话系统所述的](/MicrosoftTeams/here-s-what-you-get-with-phone-system)云呼叫队列和自动助理。

若要将电话系统自动助理或呼叫队列与 Skype for Business Server 2019 配合使用，需要创建充当应用程序终结点且可以分配电话号码的资源帐户，然后使用联机 Teams 管理中心来配置呼叫队列或自动助理。 此资源帐户可以联机托管， (请参阅 [Microsoft Teams 中的管理资源帐户](/MicrosoftTeams/manage-resource-accounts) ，以创建联机) 或本地托管的资源帐户，如本文所述。 通常，你将拥有多个电话系统自动助理或呼叫队列节点，其中每个节点都映射到资源帐户，这些帐户可以联机或在 2019 Skype for Business Server进行托管。

如果你有现有的 Exchange UM 自动助理和呼叫队列系统，则在切换到 Exchange Server 2019 或 Exchange online 之前，需要手动记录如下所述的详细信息，然后使用 Teams 管理中心实现全新的系统。

## <a name="overview"></a>概述

如果电话系统自动助理或呼叫队列需要服务号码，可按以下顺序满足各种依赖项：

1. 获取服务编号。
2. 获取用于[资源帐户的免费Microsoft Teams 电话资源帐户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付费电话系统许可证。
3. 创建资源帐户。 需要自动助理或调用队列才能拥有关联的资源帐户。
4. 等待联机和本地之间的 Active Directory 同步。
5. 将电话系统许可证分配给资源帐户。
6. 将服务编号分配给资源帐户。
7. 创建电话系统呼叫队列或自动助理。
8. 将资源帐户与自动助理或呼叫队列相关联： (New-CsApplicationInstanceAssociation) 。

如果自动助理或呼叫队列嵌套在顶级自动助理下，关联的资源帐户仅需要一个电话号码（如果需要多个入口点进入自动助理和呼叫队列的结构）。

若要将呼叫重定向到组织中处于联机状态的人员，他们必须拥有 **电话系统** 许可证并启用企业语音或拥有 Microsoft 365 或Office 365通话套餐。 请参阅 [分配 Microsoft Teams 许可证](/MicrosoftTeams/assign-teams-licenses)。 若要为其启用企业语音，可以使用Windows PowerShell。 例如，运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果要创建的电话系统自动助理或呼叫队列将被嵌套，并且不需要电话号码，则过程为：

1. 创建资源帐户  
2. 等待联机和本地之间的 Active Directory 同步
3. 创建电话系统自动助理或呼叫队列
4. 将资源帐户与电话系统自动助理或呼叫队列相关联

## <a name="create-a-resource-account-with-a-phone-number"></a>使用电话号码创建资源帐户

创建使用电话号码的资源帐户需要按以下顺序执行以下任务：

1. 移植或获取收费或免费服务号码。 无法将该数字分配给任何其他语音服务或资源帐户。

   在将电话号码分配到资源帐户之前，需要获取或移植现有的收费或免费服务号码。 获取收费或免费服务电话号码后，它们将显示在 **Microsoft Teams 管理中心** > **语音** > **电话号码** 中，列出 **的号码类型** 将列为 **服务 - 免费**。 若要获取服务号码，请参阅 [获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers) ，或者如果要传输现有服务号码，请参阅 [将电话号码传输到 Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。

   如果不在美国，则无法使用 Microsoft Teams 管理中心获取服务号码。 请改为转到[“管理组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)”，了解如何从美国外部执行此操作。

2. 购买电话系统许可证。 请参阅：  
   - [Microsoft Teams 电话资源帐户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 企业版（E1 和 E3）](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企业版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企业版 E5 商业软件](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 通过运行`New-CsHybridApplicationEndpoint`每个电话系统自动助理或呼叫队列的 cmdlet，并为每个用户提供名称、sip 地址等，创建本地资源帐户。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关此命令的更多详细信息，请参阅 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

4.  (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，或者强制同步并继续联机配置电话系统自动助理或呼叫队列。 若要强制同步，需要在运行 AAD Connect 的计算机上运行以下命令 (如果尚未执行此操作，则需要加载 `import-module adsync` 以运行命令) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关此命令的更多详细信息，请参阅 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

    请注意，此时帐户可能已同步，但预配可能无法完成。  检查 [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint) 的输出。  如果同步的终结点尚未完成预配，则不会显示在此处。  可以在 M365 门户中的 [Teams 安装状态](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)下检查预配请求的状态。  此预配阶段最多可能需要 24 小时。

5. 将 **Microsoft Teams 电话资源帐户** 许可证或 **Teams 电话标准版** 许可证分配给资源帐户。 请参阅 [分配 Microsoft Teams 加载项许可证](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 并向 [用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

   如果要将电话号码分配给资源帐户，现在可以使用免费 **Microsoft Teams 电话资源帐户** 许可证。 这为组织级别的电话号码提供电话系统功能，并允许你创建自动助理和呼叫队列功能。

6. 将服务编号分配给资源帐户。 使用命令 `Set-CsHybridApplicationEndpoint` 将电话号码 (与 -LineURI 选项) 分配给资源帐户。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    有关此命令的更多详细信息，请参阅 [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。

    若要将直接路由或混合号码分配到资源帐户，请使用以下 cmdlet：

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   如果将资源帐户分配给顶级自动助理或呼叫队列，则需要分配电话号码。 用户 (订阅者) 电话号码不能分配给资源帐户，只能使用服务收费或免费电话号码。

     可以将直接路由或混合号码分配给资源帐户。 有关详细信息，请参阅 [计划直接路由](/MicrosoftTeams/direct-routing-plan) 和 [计划云自动助理](plan-cloud-auto-attendant.md)。

     > [!NOTE]
     > 仅 Microsoft Teams 用户和代理支持分配给资源帐户自动助理和呼叫队列的直接路由服务号码。

7. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：

   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 将资源帐户与之前选择的电话系统自动助理或呼叫队列相关联。

## <a name="create-a-resource-account-without-a-phone-number"></a>创建没有电话号码的资源帐户

本部分讨论如何创建本地托管的资源帐户。 在 [Microsoft Teams 中的“管理资源帐户](/MicrosoftTeams/manage-resource-accounts)”中讨论如何创建联机托管的资源帐户。

无论是创建全新的电话系统自动助理还是呼叫队列结构，还是重新生成最初在 Exchange UM 中创建的结构，这些步骤都是必需的。

登录到Skype for Business前端服务器并运行以下 PowerShell cmdlet：

1. 通过运行`New-CsHybridApplicationEndpoint`每个电话系统自动助理或呼叫队列的 cmdlet，并为每个用户提供名称、sip 地址等，创建本地资源帐户。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关此命令的更多详细信息，请参阅 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

2.  (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，或者强制同步并继续联机配置电话系统自动助理或呼叫队列。 若要强制同步，需要在运行 AAD Connect 的计算机上运行以下命令 (如果尚未执行此操作，则需要加载 `import-module adsync` 以运行命令) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关此命令的更多详细信息，请参阅 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

3. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：
   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 关联之前选择的资源帐户和电话系统自动助理或呼叫队列。

## <a name="test-the-implementation"></a>测试实现

测试实现的最佳方式是调用为电话系统自动助理或呼叫队列配置的号码，并连接到其中一个代理或菜单。 还可以使用管理中心“操作”窗格中的 **“测试”按钮** 快速进行测试调用。 如果要更改电话系统自动助理或呼叫队列，请选择它，然后在“操作”窗格中单击 **“编辑**”。 

> [!TIP]
> 如果资源帐户在分配给呼叫队列或自动助理时遇到困难，请参阅 [Microsoft Teams 的已知问题](/MicrosoftTeams/Known-issues#phone-system)和 Microsoft Teams 博客中的[“如何修复我的混合应用程序实例”](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)部分。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>将 Exchange UM 自动助理或呼叫队列移动到电话系统

从 Exchange UM 迁移到电话系统需要重新创建呼叫队列和自动助理结构，不支持直接从一个迁移到另一个。 若要重新实现一组呼叫队列和自动助理：

1. 在 Exchange 2013 或 2016 系统上运行以下命令，同时以管理员身份登录，获取所有 Exchange UM 自动助理和呼叫队列的列表：

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 对于每个列出的 Exchange UM 呼叫队列或自动助理，请记下其在结构、设置中的位置，并获取关联的声音或文本转语音文件的副本 (输出中的 guid 将是文件存储) 的文件夹的名称。 可以通过运行命令获取以下详细信息：

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    有关此命令的更多详细信息，请参阅 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。 可能需要捕获的选项的完整列表位于 [UMAutoAttendant 成员](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) 处，但要记下的最重要选项包括：

    - 营业时间
    - 非工作时间
    - Language
    - 假日计划

3. 如前所述创建新的本地终结点。
   为顶层自动助理分配一个临时编号，以便进行测试。

4. 配置使用终结点的电话系统自动助理或呼叫队列，如前所述。

5. 测试电话系统自动助理或呼叫队列。

6. 将链接到 Exchange UM 呼叫队列的电话号码或自动助理重新分配给相应的电话系统自动助理或呼叫队列。  

   此时，如果已迁移 UM Voicemail，则应能够迁移到 2019 Exchange Server。

## <a name="see-also"></a>另请参阅

[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什么是云自动助理？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[规划云自动助理](plan-cloud-auto-attendant.md)

[规划云呼叫队列](plan-call-queue.md)

[为本地用户规划云语音邮件服务](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[在 Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( 中管理资源帐户创建联机托管的资源帐户\)
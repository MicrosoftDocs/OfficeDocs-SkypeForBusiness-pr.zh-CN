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
localization_priority: Normal
ms.collection: ''
description: 为 2019 Skype for Business Server资源帐户。
ms.openlocfilehash: 87db9779a6f90730d6aa53e3084a2014a71bad5aba91844d2e545f7d78ae37cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304694"
---
# <a name="configure-resource-accounts"></a>配置资源帐户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server 2019 混合实现仅将 电话系统 提供的云服务用于统一消息，不与 Exchange Online 集成。 在 Skype for Business Server 2019 中，你现在可以使用云呼叫队列和自动助理，如下面介绍的通过 电话系统 或 Microsoft 365 Office 365 获取[Office 365。](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

若要将 电话系统 自动助理或呼叫队列与 Skype for Business Server 2019 一同使用，需要创建充当应用程序终结点的资源帐户，并可以分配电话号码，然后使用联机 Teams 管理中心配置呼叫队列或自动助理。 此资源帐户可以联机 (请参阅管理[Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)中的资源帐户以创建联机或本地) 资源帐户，如本文所述。 通常，你将有多个电话系统自动助理或呼叫队列节点，每个节点都映射到一个资源帐户，这些帐户可以联机或 Skype for Business Server 2019。

如果您具有现有的 Exchange UM 自动助理和呼叫队列系统，在联机切换到 Exchange Server 2019 或 Exchange 之前，您需要手动记录详细信息，如下所述，然后使用 Teams 管理中心实现全新的系统。

## <a name="overview"></a>概述

如果你电话系统自动助理或呼叫队列需要服务号码，可以按以下顺序满足各种依赖关系：

1. 获取服务号码。
2. 获取免费电话系统 - 虚拟[用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付费电话系统许可证以用于资源帐户。
3. 创建资源帐户。 自动助理或呼叫队列需要具有关联的资源帐户。
4. 等待联机和本地之间的 Active Directory 同步。
5. 将电话系统许可证分配给资源帐户。
6. 为资源帐户分配服务号码。
7. 创建一电话系统呼叫队列或自动助理。
8. 将资源帐户与自动助理或呼叫队列关联： (New-CsApplicationInstanceAssociation) 。

如果自动助理或呼叫队列嵌套在顶级自动助理下，则如果您想要将多个入口点进入自动助理和呼叫队列的结构，则关联的资源帐户只需要一个电话号码。

若要将呼叫重定向到组织中在线用户，他们必须拥有 **电话系统** 许可证并启用 企业语音，或者Microsoft 365或Office 365通话套餐。 请参阅[分配Microsoft Teams许可证](/MicrosoftTeams/assign-teams-licenses)。 若要为用户启用企业语音，可以使用Windows PowerShell。 例如，运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果你电话系统自动助理或呼叫队列将嵌套，并且不需要电话号码，则过程为：

1. 创建资源帐户  
2. 等待联机和本地之间的 Active Directory 同步
3. 创建电话系统自动助理或呼叫队列
4. 将资源帐户与自动助理电话系统呼叫队列关联

## <a name="create-a-resource-account-with-a-phone-number"></a>创建具有电话号码的资源帐户

创建使用电话号码的资源帐户需要按以下顺序执行以下任务：

1. 移植或获取收费或免费服务号码。 无法将号码分配给任何其他语音服务或资源帐户。

   在将电话号码分配给资源帐户之前，你需要获取或移植现有的收费或免费服务号码。 获取收费或免费服务电话号码后，这些号码会显示在 **Microsoft Teams** 管理中心语音 电话 号码中，列出的号码类型将列为服务  >    >  -  **免费**。 若要获取服务号码，[请参阅获取服务](/MicrosoftTeams/getting-service-phone-numbers)电话号码，或者如果你想要转移现有服务号码，请参阅将电话号码转移到[Teams。](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   如果你在美国以外，则你无法通过Microsoft Teams中心获取服务号码。 转到 [管理你的组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) ，以查看如何从美国以外的地方执行。

2. 购买电话系统许可证。 请参阅：  
   - [电话系统–虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 企业版（E1 和 E3）](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企业版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企业版E5 商业软件](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 通过为每个自动助理或呼叫队列运行 cmdlet 电话系统创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4.  (可选) 创建资源帐户后，可以等待 AD 联机和本地同步，也可以强制同步并继续联机配置 电话系统 自动助理或呼叫队列。 若要强制同步，将在运行 AAD 连接 (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行命令 `import-module adsync`) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    注意-此时，帐户可能已同步，但设置可能无法完成。  检查 [Get-CsOnlineApplicationEndpoint 的输出](/powershell/module/skype/get-csonlineapplicationendpoint)。  如果同步的终结点尚未完成预配，则它将不会在此处显示。  可以在"设置状态"下的 M365 门户中检查[Teams请求的状态](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。  此预配阶段最多可能需要 24 小时。

5. 将电话系统 - 虚拟用户电话系统许可证分配给资源帐户。 请参阅[Microsoft Teams加载项许可证和](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

   如果要将电话号码分配给资源帐户，则现在可以使用免费 电话系统 - 虚拟用户许可证。 这电话系统组织级别的电话号码提供自动助理和呼叫队列功能。


6. 将服务号码分配给资源帐户。 使用 `Set-CsHybridApplicationEndpoint` 命令为资源帐户分配 (-LineURI 选项) 分配电话号码。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    有关[此命令的更多详细信息，请参阅 Set-CsHybridApplicationEndpoint。](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    若要将直接路由或混合号码分配给资源帐户，请使用以下 cmdlet：

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   如果将资源帐户分配给顶级自动助理或呼叫队列，则该帐户将需要分配的电话号码。 用户 (订阅者) 电话号码无法分配给资源帐户，只能使用收费或免费服务电话号码。

     你可以将直接路由或混合号码分配给你的资源帐户。 有关详细信息，请参阅规划[直接路由和](/MicrosoftTeams/direct-routing-plan)[规划云自动助理](plan-cloud-auto-attendant.md)。

     > [!NOTE]
     > 分配给自动助理和呼叫队列的资源帐户的直接路由服务号码仅受Microsoft Teams和代理的支持。

7. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：

   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 将资源帐户与电话系统自动助理或呼叫队列关联。

## <a name="create-a-resource-account-without-a-phone-number"></a>创建没有电话号码的资源帐户

本节讨论创建本地资源帐户。 在管理联机资源帐户中，将讨论创建在线[Microsoft Teams。](/MicrosoftTeams/manage-resource-accounts)

无论是创建全新的自动助理或呼叫队列电话系统，还是重建最初在 UM 中创建的结构，这些步骤Exchange是必需的。

登录到前端Skype for Business并运行以下 PowerShell cmdlet：

1. 通过为每个自动助理或呼叫队列运行 cmdlet 电话系统创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2.  (可选) 创建资源帐户后，可以等待 AD 联机和本地同步，也可以强制同步并继续联机配置 电话系统 自动助理或呼叫队列。 若要强制同步，将在运行 AAD 连接 (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行命令 `import-module adsync`) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. 创建电话系统自动助理或呼叫队列。 请查看下列内容之一：
   - [设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 将资源帐户与之前电话系统自动助理或呼叫队列关联。

## <a name="test-the-implementation"></a>测试实现

测试实现的最佳方法就是呼叫为自动助理或电话系统队列配置的号码，并连接到其中一个代理或菜单。 您还可以使用管理中心"操作"窗格中的 **"测试** "按钮快速进行测试呼叫。 如果要对自动助理或呼叫电话系统进行更改，请选择它，然后在"操作"窗格中单击"编辑 **"。** 

> [!TIP]
> 如果你的资源帐户在分配给呼叫队列或自动助理时有困难，请参阅[Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)的已知问题和 Microsoft Teams 博客中的如何修复我的[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)混合应用程序实例部分。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>将 Exchange UM 自动助理或呼叫队列移动到 电话系统

从 UM Exchange UM 电话系统需要重新创建呼叫队列和自动助理结构，不支持从一个直接迁移到另一个。 重新实现一组呼叫队列和自动助理：

1. 在以管理员身份登录的 Exchange 2013 或 2016 系统中运行以下命令，获取所有 Exchange UM 自动助理和呼叫队列的列表：

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 对于每个列出的 Exchange UM 呼叫队列或自动助理，请注意其在结构、设置中的位置，并获取关联声音或文本到语音文件的副本 (输出中的 guid 将是存储文件的文件夹的名称) 。 可以通过运行命令获取这些详细信息：

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    有关[此命令的更多详细信息，请参阅 Get-UMAutoAttendant。](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 可能需要捕获的选项的完整列表位于 [UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) 成员，但需要记下的最重要的选项是：

    - 营业时间
    - 非营业时间
    - 语言
    - 假日日程安排

3. 如前文所述创建新的本地终结点。
   为顶级自动助理分配一个临时号码以进行测试。

4. 按电话系统所述配置使用终结点的自动助理或呼叫队列。

5. 测试电话系统自动助理或呼叫队列。

6. 将链接到 UM 呼叫队列Exchange自动助理的电话号码重新分配给相应的电话系统自动助理或呼叫队列。  

   此时，如果您已经迁移了 UM 语音邮件，您应该可以迁移到 Exchange Server 2019。

## <a name="see-also"></a>另请参阅

[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什么是云自动助理？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[设置云自动助理](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[规划云自动助理](plan-cloud-auto-attendant.md)

[规划云呼叫队列](plan-call-queue.md)

[规划云语音邮件本地用户的部署服务](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[管理资源管理Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \(创建联机存储的资源帐户\)
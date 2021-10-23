---
title: EDU Microsoft Parents 应用的管理员设置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 一文介绍家长应用的先决条件和 PowerShell 设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b79319da9f901fc4546c25d5165f4d2361521a7
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537003"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在 Microsoft Teams 中部署父Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在 Microsoft Teams 中启用家长应用是管理员的一个简单过程，为教师提供一种安全的方法，以便与仍保留在租户中的学生及其联系人进行通信，这将在教师组织中进行扩展。

## <a name="requirements"></a>要求

### <a name="school-data-sync"></a>学校数据同步

- 你需要学校数据同步 (SDS) 来填充每个 **学生的相关联系信息**。
  - [部署 SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- 如果在设置 SDS 和在租户中启用父联系人方面需要帮助，请通过以下电话联系 EDU 客户成功团队：
  - 在 上完成 RFA [FastTrack。](https://www.microsoft.com/fasttrack?rtc=1)
  - 在支持 处打开 [票证](https://aka.ms/sdssupport)。

### <a name="teams-admins-center---policies"></a>Teams管理中心 - 策略

- 课堂所有者必须已启用聊天
- 类所有者必须具有外部访问Teams **组织未管理的帐户**。 
  - 可以在租户级别的组织范围的设置>外部访问"中找到此设置，或者，如果要为一组用户启用此设置，请参阅下面的 PowerShell。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>基于每个用户启用联合聊天

1. 安装最新的 powerShell Microsoft Teams预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 使用具有管理员权限的凭据，在命令窗口中运行以下命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

默认情况下，控制租户的使用者Teams访问的租户级别设置 (AllowTeamsConsumer) 禁用。 但是，在用户级别启用 Teams 使用者外部访问的策略设置默认为 (EnableTeamsConsumerAccess) 为用户级外部访问策略启用。 需要同时启用租户级别设置和用户级策略设置，用户Teams外部访问权限。 如果不希望租户中的每个人都启用 Teams 使用者外部访问，应在启用租户级设置之前更新分配给用户的用户级外部访问策略。

如果需要检查存在的用户级外部访问策略及其分配到的用户，可以使用以下步骤：
    
3. 检查存在哪些用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. 对于除"全局"策略外的每个策略，请检查为哪些用户分配了策略。 注意：未分配特定策略的任何用户将回退到"全局"策略

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq “<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>其他 PowerShell 选项

由于所有用户级外部访问策略的 EnableTeamsConsumerAccess 默认设置为 true，因此，如果要更新其中任何策略以调整 EnableTeamsConsumerAccess 设置，可以使用调整的设置创建新的外部访问策略，或者通过以下 PowerShell 将用户重新分配到新策略或现有策略：

- 创建新的外部访问策略 (创建新的外部访问策略，并定义以下 [) ：New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有外部访问策略 (修改现有外部访问策略的设置，包括全局策略 [) ) ：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认值："FederationAndPICDefault"、"FederationOnly"、"NoFederationAndPIC"。 如果需要更改分配了这些策略的用户的策略设置，请为这些用户分配具有正确设置的不同策略。

- 向单个用户分配外部访问策略 [：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 将策略分配给一组用户 [：New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

确信为所有用户正确设置用户级外部访问策略后，可以使用以下 cmdlet 启用控制租户的 Teams 使用者外部访问的租户级设置：

- 将租户联合配置设置 (AllowTeamsConsumer 设置为 true [) ：Set-CsTenantFederationConfiguration (SkypeForBusiness) ](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>禁用家长应用

默认情况下，"家长应用"已启用，因此所有课堂所有者都将在课堂团队中查看该应用。 可以在租户级别使用"允许"和"阻止"[](manage-apps.md#allow-and-block-apps)应用在租户Microsoft Teams应用。 如果在租户级别禁用此功能，则所有用户都将被阻止，即使启用了用户级别权限。

也可使用 [在 Microsoft Teams 中管理应用权限策略]在用户级别禁用 (teams-app-permission-policies.md) 。

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [将策略分配给用户](/powershell/module/skype/grant-csexternalaccesspolicy)

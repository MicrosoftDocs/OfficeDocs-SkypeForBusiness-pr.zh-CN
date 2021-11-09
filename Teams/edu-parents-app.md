---
title: EDU Microsoft Parents 应用的管理员设置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 文章文档先决条件和针对父应用的 PowerShell 设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785145"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在 Microsoft Teams 中部署父Microsoft Teams

"家长应用"可帮助教师使用家长和监护人在班级中安全地联系Teams家长和监护人，这将在教师组织中扩展。 所有家长和监护人数据都是使用学校数据同步预配的，使教师和 IT 人员能够顺利地进行设置。

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
  - 可以在租户级别的"用户>外部访问"中找到此设置，或者，如果要为特定的一组用户启用此设置，请参阅下面的 PowerShell。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>基于每个用户启用联合聊天

1. 安装最新的 PowerShell Microsoft Teams预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 使用具有管理员权限的凭据，在命令窗口中运行以下命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

默认为Teams访问策略启用用户级别 (EnableTeamsConsumerAccess) 的使用者外部访问的策略设置。 租户级别设置 (AllowTeamsConsumer) 和用户级策略设置都需要启用，用户Teams使用者外部访问权限。 如果不希望租户中的每个人都启用 Teams使用者外部访问，应在启用租户级设置之前更新分配给用户的用户级外部访问策略。

如果需要检查存在的用户级外部访问策略及其分配到的用户，可以使用以下步骤：
    
3. 检查存在哪些用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. 对于除"全局"策略外的每个策略，请检查为哪些用户分配了策略。 注意：未分配特定策略的任何用户将回退到"全局"策略

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>其他 PowerShell 选项

由于所有用户级外部访问策略的 EnableTeamsConsumerAccess 默认设置为 true，因此，如果要更新其中任何策略以调整 EnableTeamsConsumerAccess 设置，可以使用调整的设置创建新的外部访问策略，或者通过以下 PowerShell 将用户重新分配到新策略或现有策略：

- 创建新的外部访问策略 (这会创建新的外部访问策略，并定义以下 [) ：New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有外部访问策略 (修改现有外部访问策略的设置，包括全局策略 [) ) ：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认值："FederationAndPICDefault"、"FederationOnly"、"NoFederationAndPIC"。 如果需要更改分配了这些策略的用户的策略设置，请为这些用户分配具有正确设置的不同策略。

- 向单个用户分配外部访问策略 [：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 将策略分配给一组用户 [：New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

确信为所有用户正确设置了用户级外部访问策略后，可以使用以下 cmdlet 启用控制租户Teams使用者外部访问的租户级设置：

- 将租户联合配置设置 (AllowTeamsConsumer 设置为 true [) ：Set-CsTenantFederationConfiguration (SkypeForBusiness) ](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>禁用家长应用

默认情况下，"家长应用"已启用，因此所有课堂所有者都将在课堂团队中查看该应用。 可以在租户级别使用"允许"和"阻止"[](manage-apps.md#allow-and-block-apps)应用在租户Microsoft Teams应用。 如果在租户级别禁用此功能，则所有用户都将被阻止，即使启用了用户级别权限。

也可使用 [在 Microsoft Teams 中管理应用权限策略]在用户级别禁用 (teams-app-permission-policies.md) 。

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [将策略分配给用户](/powershell/module/skype/grant-csexternalaccesspolicy)
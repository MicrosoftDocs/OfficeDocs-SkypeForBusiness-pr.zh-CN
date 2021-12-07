---
title: Microsoft EDU Parents 应用的管理员设置Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 一文，介绍了家长应用的先决条件和设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d875c6cd753e4c2e97477b3a3a88e0f071b5cbe
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2021
ms.locfileid: "61322984"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在应用程序中部署"家长"Microsoft Teams

"家长"应用可帮助教师使用 Teams 聊天安全地与班级团队中的学生家长和监护人联系和互动，这将在教师组织中进行扩展。 所有家长和监护人数据都是使用学校数据同步预配的，使 IT 人员能够顺利地进行设置。

## <a name="requirements"></a>要求

### <a name="school-data-sync"></a>学校数据同步

- 你需要学校数据同步 (SDS) 来填充每个学生的家长和监护人 **相关的联系信息**。
  - [部署 SDS](/schooldatasync/parent-contact-sync)

- 如果在为租户中的学生设置 SDS 和填充与家长和监护人相关的联系人方面需要帮助，请联系 EDU 客户成功团队：：
  - 在 上完成 RFA [FastTrack。](https://www.microsoft.com/fasttrack?rtc=1)
  - 在支持 处打开 [票证](https://aka.ms/sdssupport)。

### <a name="teams-admin-center---policies"></a>Teams管理中心 - 策略

- 课堂团队所有者必须已启用Teams聊天。
- 课堂团队所有者必须具有外部访问权限，Teams **组织未管理的帐户**。
  - 必须在租户级别和用户级别启用此功能。 租户级别设置可在管理中心>**外部访问** Teams设置。 也可通过 PowerShell 访问此设置。 用户级外部访问策略只能通过 PowerShell 访问。 有关进一步指南，请参阅下面的 PowerShell 命令。

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>使用组织不Teams的帐户启用外部访问

1. 安装最新的 powerShell Microsoft Teams预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 使用具有管理员权限的凭据运行以下命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

默认情况下，为Teams级别外部访问策略启用策略设置，该策略设置 () 组织管理 `EnableTeamsConsumerAccess` 的帐户。 需要同时启用租户级别设置和用户级策略设置，用户能够使用未由组织管理Teams帐户进行外部访问。 如果不希望租户中的每个用户都启用此访问权限，应确保禁用租户级别设置，更新分配给用户的用户级外部访问策略，然后启用租户级设置。

若要检查存在哪些用户级外部访问策略及其分配到的用户，可以使用以下步骤：
    
3. 检查存在哪些用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 对于除"全局"策略外的每个策略，请检查为哪些用户分配了策略。

   > [!NOTE]
   > 任何未分配特定策略的用户都将回退到"全局"策略。 添加到租户的任何新用户都将分配有"全局"策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由于所有用户级外部访问策略默认设置为 true，因此，如果要调整特定用户的设置，可以使用调整的设置创建/修改现有外部访问策略，并/或者使用以下 `EnableTeamsConsumerAccess` PowerShell cmdlet 将用户重新分配到新策略或现有策略 `EnableTeamsConsumerAccess` ：

- 创建新的外部访问策略 [：New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有的外部访问策略 (包括"全局"策略 [) ：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认策略："FederationAndPICDefault"、"FederationOnly"和"NoFederationAndPIC"。 "FederationAndPICDefault"策略以前默认分配给所有用户，但新用户现在默认分配有"全局"策略。 如果需要更改分配了这些订阅默认策略的用户的策略设置，请为这些用户分配具有正确设置的不同策略。

- 向单个用户分配外部访问策略 [：Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 将策略分配给一组用户 [：New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

为租户中的用户正确设置用户级外部访问策略后，可以使用以下 cmdlet 为租户启用租户 `AllowTeamsConsumer` () 级别设置：

- 为租户设置联合配置设置 [：Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>启用家长应用

默认情况下，"家长"应用处于禁用状态，因此课堂团队所有者不会在课堂团队中看到该应用，直到允许应用通过Teams中心。 可以使用允许发布者阻止的应用Teams管理中心[允许该应用](manage-apps.md#apps-blocked-by-publishers)。

应用随时可在租户级别使用"允许"和"阻止"应用在[](manage-apps.md#allow-and-block-apps)租户Teams禁用。 如果在租户级别禁用应用，则所有用户都会阻止该应用，即使启用了用户级别权限。

也可在用户级别使用管理应用权限策略在[Microsoft Teams。](teams-app-permission-policies.md)

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

---
title: 家长在家长Teams 教育版
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams介绍家长在家长中的先决条件和Teams 教育版。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d1b84fc78558fcbb1945cbc56b311b5e06234a5
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062526"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在 Microsoft Teams 教育版 中设置父Microsoft Teams 教育版

Teams 教育版 中的家长连接可帮助教师使用 Teams 聊天安全地与班级团队中的学生家长和监护人联系和互动，这将在教师组织中扩展。 所有家长和监护人数据都是使用学校数据同步，使 IT 人员能够顺利地进行设置。

一旦设置了教师和监护人，他们就可以使用聊天功能Teams聊天。 

有关让家长和监护人与教师保持联系的指南，请参阅连接[教师的Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。

有关让教师设置与家长和监护人进行通信的指导，请参阅[与](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)家长和监护人Microsoft Teams。

家长还使用监督聊天。 家长和监护人没有完全Teams权限，这意味着他们无法开始与学生对话或删除完全权限的用户， (教师) 聊天。 有关监督聊天详细信息[，请参阅在](supervise-chats-edu.md)聊天中使用Microsoft Teams。

## <a name="requirements"></a>要求

### <a name="school-data-sync"></a>学校数据同步

- 你需要学校数据同步 (SDS) 来填充每个学生的家长和监护人 **相关的联系信息**。
  - [部署 SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果在为租户中的学生设置 SDS 和填充与家长和监护人相关的联系人方面需要帮助，请联系 EDU 客户成功团队：：
  - 完成 RFA 过程（[FastTrack](https://www.microsoft.com/fasttrack?rtc=1)）。
  - 在支持处创建 [票证](https://aka.ms/sdssupport)。

- 目前，SDS 仅支持父联系人的基于 CSV 的数据导入;但是，可以将 [PowerSchool API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 或 [OneRoster API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 用于所有名单数据，并且只需使用 CSV 添加父联系人。
  - 使用 [SDS v1 CSV 同步格式创建第二个同步配置文件](/schooldatasync/school-data-sync-format-csv-files-for-sds)。
  - 拉取两个填充的 [父](/schooldatasync/parent-contact-sync-file-format) 文件，其中 v1 文件的其余部分为空， (标头) 。
    - User.csv
    - Guardianrelationship.csv
  - 若要查看 v1 CSV 文件的示例集，请参阅文件的最低GitHub[属性](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果要在初始同步后自动拉取 CSV 文件，请阅读 [CSV 文件同步自动化文档](/schooldatasync/csv-file-sync-automation)。
  - 有关设置 SDS 数据同步的帮助，请与客户成功团队[联系或](https://www.microsoft.com/fasttrack?rtc=1)[创建支持票证](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center---policies"></a>Teams管理中心 - 策略

- 课堂团队所有者必须Teams打开聊天。
- 课堂团队所有者必须具有外部访问权限，Teams未由打开 **的组织管理** 的帐户。
  - 必须在租户级别和用户级别启用此功能。 租户级别设置可在管理中心>**外部访问** Teams设置。 也可通过 PowerShell 访问此设置。 用户级外部访问策略只能通过 PowerShell 访问。 有关进一步指南，请参阅下面的 PowerShell 命令。

> [!NOTE]
>家长和监护人在"家长"功能中归类为"外部用户"，这意味着他们没有完全的租户权利。 他们只能访问添加到聊天中的聊天，以及聊天中共享的文件、图像和其他内容。
>
>此外，外部用户 (脱机、) 、忙碌等状态，但可以使用 PowerShell 关闭此功能以保护用户的隐私。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration 并](/powershell/module/skype/set-csprivacyconfiguration) 设置 ``EnablePrivacyMode=true``。
>
>即使家长和监护人是外部用户，他们对聊天的贡献也是可发现的。 阅读对电子数据展示中Teams数据展示调查，了解如何执行电子数据展示[Microsoft Teams](ediscovery-investigation.md)。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>允许使用组织Teams管理的帐户进行外部访问

若要允许教师与 Teams 中的家长和监护人通信，教育租户的 IT 管理员需要更新租户的策略，以允许租户外部的 Teams 帐户进行外部访问。 有关管理外部访问的信息，请参阅在 Microsoft Teams [中管理外部Microsoft Teams](manage-external-access.md)。

下面是为家长和监护人启用外部访问的步骤。

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

    默认情况下，`EnableTeamsConsumerAccess`对于所有用户级外部访问策略， () 启用非组织托管的 Teams 帐户的外部访问的策略设置。 需要启用租户级别设置和用户级策略设置，用户需使用组织不Teams帐户进行外部访问。 如果不希望租户中的每个用户都启用此访问权限，应确保关闭租户级别设置，更新分配给用户的用户级外部访问策略，然后打开租户级设置。

    若要检查存在哪些用户级外部访问策略及其分配到哪些用户级外部访问策略，可以使用以下步骤：

3. 检查是否存在用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 对于除"全局"策略外的每个策略，请检查为哪些用户分配了策略。

   > [!NOTE]
   > 任何未分配特定策略的用户都将回退到"全局"策略。 添加到租户的任何新用户都将分配有"全局"策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由于所有用户级外部 `EnableTeamsConsumerAccess` 访问策略默认设置为 true `EnableTeamsConsumerAccess` ，因此，如果要调整特定用户的设置，可以使用调整的设置创建/修改现有外部访问策略，并/或者使用以下 PowerShell cmdlet 将用户重新分配到新策略或现有策略：

- 创建新的外部访问策略： [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有的外部访问策略 (包括"全局"策略) [：Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认策略："FederationAndPICDefault"、"FederationOnly"和"NoFederationAndPIC"。 "FederationAndPICDefault"策略以前默认分配给所有用户，但新用户现在默认分配有"全局"策略。 如果需要更改分配了这些订阅默认策略的用户的策略设置，请为这些用户分配具有正确设置的不同策略。

- 向单个用户分配外部访问策略： [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 将策略分配给一组用户： [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

为租户中的 `AllowTeamsConsumer` 用户正确设置用户级外部访问策略后，可以使用以下 cmdlet 为租户 () 级别设置：

- 为租户设置联合配置设置： [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>在"家长管理中心"Teams"应用

默认情况下，"家长"应用已关闭，因此课堂团队所有者不会在课堂团队中看到它，直到允许它通过Teams中心。 使用允许发布者阻止的应用Teams管理中心中打开"家长["应用](manage-apps.md#apps-blocked-by-publishers)。

应用随时可在租户级别使用"允许"和"阻止"应用在租户[](manage-apps.md#allow-and-block-apps)Teams关闭。 如果在租户级别将其关闭，则所有用户都会阻止它，即使用户级别的权限处于打开状态。

也可在用户级别使用管理应用权限策略在用户级别关闭"家长"[Microsoft Teams。](teams-app-permission-policies.md)

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

---
title: 管理员在Teams 教育版中设置家长
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams一篇文章，记录Teams 教育版中父级的先决条件和设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a38bfbcc8ec7de5e9c1535b1a597b534e46d009
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190612"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在Microsoft Teams 教育版中设置父连接

Teams 教育版中的家长连接可帮助教师使用Teams安全地与班级团队中学生的父母和监护人联系和联系。

本文为教育 IT 专业人员提供有关父连接的要求和设置的指导。

## <a name="share-guardian-and-educator-resources"></a>共享监护人和教师资源

下面是 IT 管理员可以与监护人和教育工作者共享的一些资源，了解如何开始使用父连接。

- 有关设置监护人的指导，请参阅[Teams中的教师连接](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。
- 有关设置教师的指南，请参阅[Microsoft Teams中与监护人沟通](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)。

## <a name="benefits-of-parent-connection"></a>父连接的优点

家长连接允许教师和监护人使用Teams聊天、发送电子邮件和呼叫。

- 教师可以与监护人开始聊天。
  - 如果监护人没有Teams使用者帐户，他们将收到来自教师的初始消息和电子邮件邀请，邀请他们转到Teams。
- 它适用于监督聊天。 有关详细信息，请参阅[Microsoft Teams中使用监督式聊天](supervise-chats-edu.md)。
  - 默认情况下，监护人具有受限权限，因此他们无法与学生聊天或从聊天中删除用户。
  - 租户管理员可以更改此设置。
- 教师可以单击监护人的电子邮件，使用本机电子邮件客户端向他们发送电子邮件。
- 教师可以单击监护人的电话号码，在Teams中呼叫他们。

> [!IMPORTANT]
> 若要在Teams中单击调用功能，租户需要：
>
> - 公共分支Exchange (PBX) 功能。
> - 连接到 PSTN。
>
> Microsoft 365 A1和 A3 计划不包括 PBX 功能和 PSTN 连接。 可以 [购买每个加载项许可证](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
>
> Microsoft 365 A5计划仅包括使用Teams 电话系统的 PBX 功能。 仍需[购买Teams呼叫计划，或使用第三方解决方案](pstn-connectivity.md)连接到 PSTN 上的外部号码。
>
> 有关获取 PSTN 连接的所有选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。
>
> 有关Teams调用许可的详细信息，请[参阅Teams附加许可选项](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

## <a name="requirements"></a>要求

你需要使用 Microsoft Graph或学校数据同步 (SDS) 来填充每个学生的家长和监护人相关的联系信息。

### <a name="graph-api"></a>Graph API

如果已使用 [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview) 创建学生标识，则可以轻松包含[相关Contact 资源类型](/graph/api/resources/relatedcontact)。

### <a name="school-data-sync"></a>学校数据同步

Teams在设置为定期同步SDS时，使用 学校数据同步 (SDS) 在 SIS 中保持最新联系人数据。

如果从 *学生* 记录中删除监护人，任何涉及他们的现有聊天都将包含聊天所有者可见的横幅。 此横幅将使聊天所有者意识到更改，要求他们从聊天中删除监护人。 Microsoft 不会自动更新聊天成员身份以删除监护人。

- 你需要学校数据同步 (SDS) 来填充每个学生的家长和监护人 **相关的联系** 信息。
  - [部署 SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果在为租户中的学生设置SDS和填充家长和监护人 **相关联系人** 方面需要帮助，请通过以下方式联系 EDU 客户成功团队：
  - 在[FastTrack](https://www.microsoft.com/fasttrack?rtc=1)完成 RFA 过程。
  - 在 [支持](https://aka.ms/sdssupport)处打开票证。

- 目前，SDS仅支持父联系人基于 CSV 的数据引入;但是，可以对所有名册数据使用 [PowerSchool API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync)或 [OneRoster API 同步](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync)，只需使用 CSV 添加父联系人即可。
  - 使用 [SDS v1 CSV 同步格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)创建第二个同步配置文件。
  - 拉取两个填充的 [父文件](/schooldatasync/parent-contact-sync-file-format) ，其余 v1 文件为空 (仅) 标头。
    - User.csv
    - Guardianrelationship.csv
  - 若要查看 v1 CSV 文件的示例集，请参阅GitHub[文件的最低必需属性](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果要在初始同步后自动拉取 CSV 文件，请阅读 [CSV 文件同步自动化文档](/schooldatasync/csv-file-sync-automation)。
  - 有关设置SDS数据同步的帮助，请联系[我们的客户成功团队](https://www.microsoft.com/fasttrack?rtc=1)或[开具支持票证](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>Teams管理中心策略

- 班级团队所有者必须打开Teams聊天。
- 类团队所有者必须具有外部访问权限 **，Teams未由启用的组织管理的帐户**。
  - 必须在租户级别和用户级别启用此功能。 可以在Teams管理中心的 **用户>外部访问** 中找到租户级别设置。 也可以通过 PowerShell 访问此设置。 只能通过 PowerShell 访问用户级别的外部访问策略。 有关进一步指南，请参阅下面的 PowerShell 命令。

#### <a name="parent-and-guardian-restrictions"></a>家长和监护人限制

父母和监护人在“父母连接”中被归类为 *外部用户* ，这意味着他们没有完整的租户权限。 他们只能访问聊天或聊天的一部分以及聊天中共享的文件、图像和其他内容。

对于外部聊天，内部和外部用户都可以将用户添加到聊天中。 若要详细了解外部聊天体验，请参阅[Microsoft Teams中管理外部会议和聊天](manage-external-access.md)。

此外，外部用户还可以看到组织用户 (脱机、可用、忙碌等) 状态，但可以使用 PowerShell 关闭此状态以保护用户的隐私。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) 和 set ``EnablePrivacyMode=true``。

尽管父母和监护人是外部用户，但他们对聊天的贡献是可以发现的。 了解如何通过阅读Microsoft Teams中[的内容电子数据展示调查](ediscovery-investigation.md)来进行Teams电子数据展示调查。

> [!IMPORTANT]
> IT 管理员应让所有班主了解通过聊天共享学生信息的最佳做法，包括学生隐私风险。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>在聊天中阻止家长或监护人

教师可以在“父连接”中发起的聊天中阻止监护人。

类所有者可以：

1. 打开监护人的配置文件卡，选择省略号并 **阻止用户**。
2. 然后，从聊天中删除监护人。

被阻止的用户将无法与类所有者开始其他聊天。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>允许使用组织未管理的Teams帐户进行外部访问

若要允许教师在Teams中与家长和监护人通信，教育租户的 IT 管理员需要更新租户的策略，以允许外部访问租户外部Teams帐户。 有关管理外部访问权限的详细信息，请[查看Microsoft Teams中的“管理外部访问](manage-external-access.md)”。

下面是为父母和监护人启用外部访问权限的步骤。

1. 安装最新的 Microsoft Teams PowerShell 模块预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 使用具有管理员权限的凭据运行以下命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    默认情况下，为所有用户级外部访问策略启用启用外部访问权限的策略设置，其中Teams帐户不是由组织在用户级别管理的 (`EnableTeamsConsumerAccess`) 。 租户级别设置和用户级策略设置都需要启用，用户才能对组织未管理的Teams帐户进行外部访问。 如果不希望租户中的每个用户都启用此访问权限，应确保已关闭租户级别设置，更新分配给用户的用户级外部访问策略，然后打开租户级别设置。

    若要检查存在哪些用户级外部访问策略及其分配给谁，可以使用以下步骤：

3. 检查是否存在用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 对于除“全局”策略以外的每个策略，请检查分配了策略的用户。

   > [!NOTE]
   > 任何未分配特定策略的用户都将回退到“全局”策略。 任何添加到租户的新用户都将分配“全局”策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由于所有用户级外部访问策略默认已 `EnableTeamsConsumerAccess` 设置为 true，因此如果要调整 `EnableTeamsConsumerAccess` 特定用户的设置，可以使用以下 PowerShell cmdlet 创建/修改具有调整设置和/或将用户重新分配到新的或现有策略的现有外部访问策略：

- 创建新的外部访问策略： [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有的外部访问策略 (包括“全局”策略) ： [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认策略：“FederationAndPICDefault”、“FederationOnly”、“NoFederationAndPIC”。 默认情况下，用于分配给所有用户的“FederationAndPICDefault”策略，但默认情况下会为新用户分配“全局”策略。 如果需要更改分配了这些订阅默认策略的用户的策略设置，请为这些用户分配具有正确设置的不同策略。

- 向单个用户分配外部访问策略： [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 向一组用户分配策略： [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

为租户中的用户正确设置用户级外部访问策略后，可以使用以下 cmdlet 为租户启用租户级别设置 (`AllowTeamsConsumer`) ：

- 设置租户的联合身份验证配置设置： [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>在Teams管理中心打开“父级”应用

“家长”应用默认处于关闭状态，因此，在通过Teams管理中心允许之前，课堂团队所有者不会在班级团队中看到它。 使用[发布者阻止的“允许”](manage-apps.md#apps-blocked-by-publishers)应用在Teams管理中心打开了“父级”应用。

可以随时在租户级别使用“允许”关闭应用，并在Teams管理中心[阻止应用](manage-apps.md#allow-and-block-apps)。 如果在租户级别将其关闭，则会阻止所有用户，即使已启用用户级权限。

也可以使用[Microsoft Teams中的管理应用权限策略在](teams-app-permission-policies.md)用户级别关闭 Parents 应用。

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

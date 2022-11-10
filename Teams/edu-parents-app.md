---
title: 管理员Teams 教育版中的 Parents 设置
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams 文章记录了 Teams 教育版 中家长的先决条件和设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4cb61038c08739afcd6a48825f8ddaa0cb7c573
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912811"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>在 Microsoft Teams 教育版 中设置父连接

Teams 教育版中的家长连接可帮助教师使用 Teams 安全地与课堂团队中学生的家长和监护人联系。

本文为 IT 专业人员提供有关父连接的要求和设置的指导。

## <a name="share-guardian-and-educator-resources"></a>共享监护人和教师资源

以下是 IT 管理员可与监护人和教师共享的一些资源，了解如何开始使用父连接。

- 有关设置监护人的指导，请参阅 [在 Teams 中与教师联系](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)。
- 有关设置教师的指导，请参阅 [在 Microsoft Teams 中与监护人通信](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us)。

## <a name="benefits-of-parent-connection"></a>父连接的优点

家长连接允许教师和监护人使用 Teams 聊天、发送电子邮件和通话。

- 教师可以启动与监护人的聊天。
  - 如果监护人没有 Teams 使用者帐户或尚未加入 Teams，他们将收到来自教师的消息以及访问 Teams 的电子邮件邀请。 这仅适用于尚未达到邀请限制，并且聊天是从父连接重新输入的新聊天或现有聊天的情况。
- 它适用于监督聊天。 有关详细信息，请参阅 [在 Microsoft Teams 中使用监督式聊天](supervise-chats-edu.md)。
  - 默认情况下，监护人具有受限的权限，因此他们无法与学生聊天或从聊天中删除用户。
  - 租户管理员可更改此设置。
- 教师可以单击监护人的电子邮件，使用其本机电子邮件客户端向他们发送电子邮件。
- 教师可以单击监护人的电话号码在 Teams 中呼叫他们。

> [!IMPORTANT]
> 若要单击以调用 Teams 中的功能，租户需要：
>
> - 公共分支 Exchange (PBX) 功能。
> - 连接到 PSTN。
>
> Microsoft 365 A1和 A3 计划不包括 PBX 功能和 PSTN 连接。 可以为每个许可证购买 [附加许可证](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
>
> Microsoft 365 A5计划仅包括使用 Teams 电话系统的 PBX 功能。 你仍需要 [购买 Teams 通话套餐或使用第三方解决方案](pstn-connectivity.md) 连接到 PSTN 上的外部号码。
>
> 有关获取 PSTN 连接的所有选项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。
>
> 有关 Teams 通话许可的详细信息，请参阅 [Teams 附加许可选项](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

## <a name="requirements"></a>要求

你需要使用 Microsoft Graph 或学校数据同步 (SDS) 来填充每个学生的家长和监护人相关的联系信息。

### <a name="graph-api"></a>Graph API

如果已使用 [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview) 创建学生标识，可以轻松包含 [relatedContact 资源类型](/graph/api/resources/relatedcontact)。

### <a name="school-data-sync"></a>学校数据同步

当 SDS 设置为定期同步时，Teams 监护人联系人数据会使用学校数据同步 (SDS) 与 SIS 保持同步。

如果从 *学生的* 记录中删除监护人，则涉及他们的任何现有聊天都将包含对聊天所有者可见的横幅。 此横幅将使聊天所有者知道更改，要求他们从聊天中删除监护人。 Microsoft 不会自动更新聊天成员身份以删除监护人。

- 你需要学校数据同步 (SDS) 来填充每个学生的家长和监护人 **相关的联系信息** 。
  - [部署 SDS](/schooldatasync/parents-and-guardians-in-sds)

- 如果在为租户中的学生设置 SDS 和填充家长和监护人 **相关联系人** 方面需要帮助，请通过以下方式联系 EDU 客户成功团队：
  - 在 [FastTrack](https://www.microsoft.com/fasttrack?rtc=1) 完成 RFA 过程。
  - 在 [支持部门](https://aka.ms/sdssupport)开具票证。

- 目前，SDS 仅支持父联系人基于 CSV 的数据引入;但是，可以将 [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 或 [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 用于所有名单数据，只需使用 CSV 添加家长联系人。
  - 使用 [SDS v1 CSV 同步格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)创建第二个同步配置文件。
  - 拉取两个填充的 [父文件](/schooldatasync/parent-contact-sync-file-format) ，其余 v1 文件为空， (只是标头) 。
    - User.csv
    - Guardianrelationship.csv
      - 需要为每个家长和监护人完成 *角色* 值，以指示他们是 *家长* 还是 *监护人*。
  - 若要查看 v1 CSV 文件的示例集，请参阅 [最低必需属性 GitHub 文件](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes)。
  - 如果要在初始同步后自动拉取 CSV 文件，请阅读 [CSV 文件同步自动化文档](/schooldatasync/csv-file-sync-automation)。
  - 有关设置 SDS 数据同步的帮助，请联系 [我们的客户成功团队](https://www.microsoft.com/fasttrack?rtc=1) 或 [开具支持票证](https://edusupport.microsoft.com/support?product_id=data_sync)。

### <a name="teams-admin-center-policies"></a>Teams 管理中心策略

- 课堂团队所有者必须启用 Teams 聊天。
- 类团队所有者必须具有外部访问权限，这些 **帐户不是由组织管理的** 已启用。
  - 必须在租户级别和用户级别启用此功能。 可以在 Teams 管理中心的用户 **>外部访问** 中找到租户级别设置。 还可以通过 PowerShell 访问此设置。 用户级外部访问策略只能通过 PowerShell 进行访问。 有关进一步的指导，请参阅下面的 PowerShell 命令。

#### <a name="parent-and-guardian-restrictions"></a>家长和监护人限制

家长和监护人在父级连接中被归类为 *外部用户* ，这意味着他们没有完全的租户权限。 他们只能访问自己所属的聊天或聊天，以及聊天中共享的文件、图像和其他内容。

对于外部聊天，内部和外部用户可以将用户添加到聊天。 若要了解有关外部聊天体验的详细信息，请参阅 [在 Microsoft Teams 中管理外部会议和聊天](manage-external-access.md)。

此外，外部用户可以看到组织用户的状态 (脱机、可用、忙碌等) ，但可以使用 PowerShell 将其关闭以保护用户的隐私。 在 PowerShell 中，使用 [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) 并设置 ``EnablePrivacyMode=true``。

即使父母和监护人是外部用户，他们对聊天的贡献是可以发现的。 阅读对 [Microsoft Teams 中的内容进行电子数据展示调查，了解如何进行 Teams 电子数据展示调查](ediscovery-investigation.md)。

> [!IMPORTANT]
> IT 管理员应让所有课堂所有者了解通过聊天共享学生信息的最佳做法，包括学生隐私风险。

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>在聊天中阻止家长或监护人

教师可以在父连接中启动的聊天中阻止监护人。

类所有者可以：

1. 打开监护人的个人资料卡，选择省略号并 **阻止用户**。
2. 然后，从聊天中删除监护人。

被阻止的用户将无法开始与类所有者的其他聊天。

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>允许使用非组织管理的 Teams 帐户进行外部访问

若要允许教师与 Teams 中的家长和监护人进行通信，教育租户的 IT 管理员需要更新租户的策略，以允许对租户外部的 Teams 帐户进行外部访问。 有关管理外部访问的详细信息，请参阅 [在 Microsoft Teams 中管理外部访问](manage-external-access.md)。

下面是为家长和监护人启用外部访问的步骤。

1. 安装最新的 Microsoft Teams PowerShell 模块预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 使用具有管理员权限的凭据，运行以下命令：

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    默认情况下，对于所有用户级外部访问策略，将启用非组织在用户级别管理的 Teams 帐户 (`EnableTeamsConsumerAccess`) 的外部访问的策略设置。 需要同时启用租户级设置和用户级策略设置，以便用户使用非组织管理的 Teams 帐户进行外部访问。 如果不希望租户中的每个用户都启用此访问权限，则应确保关闭租户级别设置，更新分配给用户的用户级外部访问策略，然后启用租户级设置。

    若要检查存在哪些用户级外部访问策略以及这些策略被分配给谁，可以使用以下步骤：

3. 检查是否存在用户级外部访问策略。

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. 对于“全局”策略以外的每个策略，请检查为哪些用户分配了策略。

   > [!NOTE]
   > 未分配特定策略的任何用户都将回退到“全局”策略。 添加到租户的任何新用户都将分配“全局”策略。

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

由于默认情况下，所有用户级外部访问策略都 `EnableTeamsConsumerAccess` 设置为 true，因此如果要调整 `EnableTeamsConsumerAccess` 特定用户的设置，可以使用调整的设置创建/修改现有外部访问策略，并/或使用以下 PowerShell cmdlet 将用户重新分配到新的或现有策略：

- 创建新的外部访问策略： [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 自定义现有的外部访问策略 (包括“全局”策略) ： [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 无法修改以下订阅默认策略：“FederationAndPICDefault”、“FederationOnly”、“NoFederationAndPIC”。 “FederationAndPICDefault”策略过去默认分配给所有用户，但新用户现在默认分配“全局”策略。 如果需要为分配了这些订阅默认策略的用户更改策略设置，请为这些用户分配具有正确设置的不同策略。

- 将外部访问策略分配给单个用户： [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 将策略分配给一组用户： [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

为租户中的用户正确设置用户级外部访问策略后，可以使用以下 cmdlet 为租户启用租户级别设置 (`AllowTeamsConsumer`) ：

- 设置租户的联合配置设置： [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>在 Teams 管理中心中打开“家长”应用

默认情况下，Parents 应用处于关闭状态，因此课堂团队所有者不会在课堂团队中看到它，直到通过 Teams 管理中心允许该应用。 使用 [“允许开发人员阻止应用”](manage-apps.md#allow-and-block-apps)在 Teams 管理中心中打开“Parents”应用。

随时可以使用 Teams 管理中心中的 [“允许”和“阻止应用](manage-apps.md#allow-and-block-apps) ”在租户级别关闭应用。 如果在租户级别将其关闭，则所有用户都将阻止它，即使打开了用户级权限也是如此。

还可以使用 [Microsoft Teams 中的管理应用权限策略](teams-app-permission-policies.md)在用户级别关闭 Parents 应用。

## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

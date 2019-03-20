---
title: 使用 Microsoft Teams 管理员角色管理 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
ms.reviewer: islubin
description: 了解如何使用不同的管理角色管理团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5280691b5272765b0c351c38a03e9711b9e0f1b0
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684046"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>使用 Microsoft Teams 管理员角色管理 Teams

使用 Azure Active Directory (Azure AD)，您可以指定用于管理的 Microsoft 团队需要不同的访问级别的管理员。 管理员可以管理整个团队工作负荷，或者他们可以具有委派权限的疑难解答呼叫质量问题或管理需要组织的电话。 

## <a name="teams-roles-and-capabilities"></a>工作组角色和功能

有四个团队管理员角色可用： 团队服务管理员、 团队 communications 管理员、 团队 communications 支持专家、 和团队 communications 支持工程师。 查看下表了解每个角色可以执行的操作，并且该工具管理员可以使用中的 Microsoft 团队管理中心和 PowerShell。

<!-- add Global admin role? -->

| 角色 | 可以执行这些任务 | 可以访问以下工具 |
|----- | ------------------ | ------------------------------ |
| Teams 服务管理员 | 管理 Microsoft 团队服务，管理和创建 Office 365 组 | 中的 Microsoft 团队管理中心和关联的 PowerShell 控件，包括的所有内容：<br><br> 管理会议，包括会议策略、 配置和会议网桥<sup>1、 3</sup><br><br> 管理语音，包括调用策略和电话号码的清单和分配<sup>1</sup><br><br> 管理消息传递，包括消息策略<sup>1、 3</sup><br><br> 管理所有组织范围的设置，包括联合身份验证、 团队升级和团队客户端设置<sup>1、 3</sup><br><br> 管理组织及其关联的设置，包括成员资格 （通过 PowerShell 中，在推出的管理门户中的团队管理支持管理组） <sup>23</sup>中的团队<br><br> 查看用户配置文件页和解决用户呼叫质量问题使用高级故障排除工具集<sup>3</sup> <br><br> 访问、 监视和解决租户的呼叫的质量和使用数据的可靠性公开中呼叫质量仪表板 (CQD)。 创建新的报表、 更新和删除报告，根据需要。 上载并更新 CQD 构建数据 |
| Teams 通信管理员 | 在 Microsoft Teams 服务中管理通话和会议功能 | 管理会议，包括会议策略、 配置和会议网桥<sup>1、 3</sup><br><br> 管理语音，包括调用策略和电话号码的清单和分配<sup>1</sup><br><br> 查看用户配置文件页和解决用户呼叫质量问题使用高级故障排除工具集<sup>3</sup> |
| Teams 通信支持工程师 | 使用**高级**工具解决团队中的通信问题。 | 查看用户配置文件页和解决用户呼叫质量问题使用高级故障排除工具集<sup>3</sup> |
| 团队 Communications 支持专家 | 使用**基本**工具解决团队中的通信问题。| 访问用户配置文件页的疑难解答呼叫分析中的呼叫。 只能查看搜索的特定用户的用户信息。<sup>3</sup>

<sup>1</sup> [PowerShell-商业模块的 Skype](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell 的 Microsoft 团队模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [的 Microsoft 团队管理中心](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
有关可用于管理的 Microsoft 团队的管理工具的详细信息，请参阅[管理 Microsoft 团队](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。

有关限制、 规格和适用于团队的其他要求的详细信息，请参阅[限制和规格的 Microsoft 团队](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>向每个角色分配用户

您可以将用户分配这些角色在 Azure Active Directory 中。 若要了解如何将管理角色分配给 Azure Active Directory 中的用户，请参阅[为用户在 Azure Active Directory 中的管理员角色分配](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>适用于每个角色 Cmdlet

大部分这些管理员角色的 PowerShell 工具中的业务 PowerShell 模块，Skype live 和务必注意这些管理员角色可以访问控件的 cmdlet 的一些共享业务 online 还利用的 Skype 的设置。 若要查看中的业务 PowerShell 模块 Skype cmdlet 的当前给定角色的完整列表，请按照下列步骤：

1. 将该角色分配给用户 （并确保用户具有没有其他角色）。
2. 连接到业务 PowerShell 模块 Skype:<br>
   a. $session = 新 csonlinesession<br>
   b. 导入 pssession $session<br>
   c. 使用**Get-模块**来标识导入的会话 （将是随机生成的名称） 的名称。<br>
3. 使用**Get-command-模块** <*上面名称*> 标识所有可用的 cmdlet

### <a name="related-topics"></a>相关主题

- [Microsoft 团队 PowerShell 概述 （英文)](teams-powershell-overview.md)
- [Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中分配团队所有者和成员](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)


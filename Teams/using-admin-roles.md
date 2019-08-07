---
title: 使用 Microsoft 团队管理员角色管理团队
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
ms.openlocfilehash: fa461f587b2143b1981c3dfc70910572bd4cb004
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "35925420"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft 团队管理员角色管理团队

使用 Azure Active Directory (Azure AD), 你可以将需要不同级别的访问权限的管理员指定为管理 Microsoft 团队。 管理员可以管理整个团队工作负荷, 也可以具有委派权限, 用于解决呼叫质量问题或管理组织的电话需求。 

## <a name="teams-roles-and-capabilities"></a>团队角色和功能

有四个团队管理员角色可用: 团队服务管理员、团队通信管理员、团队通信支持专家和团队通信支持工程师。 查看下表, 了解每个角色可以执行的操作以及管理员可在 Microsoft 团队管理中心和 PowerShell 中使用的工具。



<!-- add Global admin role? -->

| 角色 | 可以执行这些任务 | 可访问以下工具 |
|----- | ------------------ | ------------------------------ |
| Teams 服务管理员 | 管理团队服务, 管理和创建 Office 365 组 | Microsoft 团队管理中心和关联的 PowerShell 控件中的所有内容, 包括:<ul><li> 管理会议, 包括会议策略、配置和会议桥。<sup>1、3</sup></li><li>管理语音, 包括呼叫策略和电话号码库存和作业。<sup>1</sup></li><li>管理消息服务, 包括消息策略。<sup>1、3</sup></li><li>管理所有组织范围的设置, 包括联盟、团队升级和团队客户端设置。 s<sup>1, 3</sup></li><li>管理组织中的团队及其关联的设置, 包括成员身份 (通过 PowerShell 支持的组管理、团队管理中心中的团队管理)。<sup>23 日</sup></li><li>查看用户个人资料页面并使用高级疑难解答工具集解决用户呼叫质量问题。<sup>3</sup> </li><li> 使用呼叫质量仪表板 (CQD) 中的数据向受不良呼叫质量影响的用户进行访问、监控和解决租户的通话质量和可靠性。 根据需要创建新报表、更新和删除报表。 上载和更新 CQD 生成数据。</li><li> [从团队客户端将应用发布到租户应用目录](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Teams 通信管理员 | 管理团队服务内的通话和会议功能。 | 管理会议, 包括会议策略、配置和会议桥。<sup>1、3</sup><br><br> 管理语音, 包括呼叫策略和电话号码库存和作业。<sup>1</sup><br><br> 查看用户个人资料页面并使用高级疑难解答工具集解决用户呼叫质量问题。<sup>3</sup> <br><br> 使用呼叫质量仪表板 (CQD) 中的数据向受不良呼叫质量影响的用户访问、监视和解决租户的通话质量和可靠性。 根据需要创建新报表、更新和删除报表。 上载和更新 CQD 生成数据。|
| Teams 通信支持工程师 | 使用**高级**工具解决团队中的通信问题。 | 查看用户个人资料页面并使用高级疑难解答工具集解决用户呼叫质量问题。<sup>3</sup> <br><br> 使用呼叫质量仪表板 (CQD) 中的数据向受不良呼叫质量影响的用户访问、监视和解决租户的通话质量和可靠性。 |
| 团队沟通支持专家 | 使用**基本**工具解决团队中的通信问题。| 访问用户配置文件页面, 用于解决呼叫分析中的呼叫。 只能查看搜索的特定用户的用户信息。<sup>3</sup> <br><br> 使用在通话质量仪表板 (CQD) 中公开的数据访问、监控租户的通话质量和可靠性并进行故障排除。  

<sup>1</sup> [PowerShell-Skype for business 模块](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell-Microsoft 团队模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft 团队管理中心](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
有关可用于管理 Microsoft 团队的管理员工具的详细信息, 请参阅[管理 Microsoft 团队](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。

有关适用于团队的限制、规范和其他要求的详细信息, 请参阅[Microsoft 团队的限制和规范](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>为用户分配每个角色

你可以在 Azure AD 中向用户分配这些角色。 若要了解如何在 Azure AD 中向用户分配管理角色, 请参阅向[Azure Active Directory 中的管理员角色分配用户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>适用于每个角色的 cmdlet

适用于这些管理员角色的大多数 PowerShell 工具都在 Skype for business PowerShell 模块中运行, 因此请务必注意, 这些管理员角色的一些 cmdlet 有权控制也用于 Skype for business Online 的共享设置。 Skype for Business 管理员角色还可以访问 Skype for business PowerShell 模块中的所有 cmdlet。

若要查看 Skype for Business PowerShell 模块中当前对给定角色可用的 cmdlet 的完整列表, 请按照下列步骤操作:

1. 将该角色分配给用户 (并确保用户没有其他角色)。
2. 连接到 Skype for Business PowerShell 模块:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. 使用 "**获取模块**" 标识导入会话的名称 (它将是随机生成的名称)。<br>
3. 使用上述> 的**Get Command Module** <*name*标识所有可用 cmdlet

### <a name="related-topics"></a>相关主题

- [Microsoft 团队 PowerShell 概述](teams-powershell-overview.md)
- [Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中分配团队所有者和成员](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)


---
title: 使用 Microsoft Teams 管理员角色管理 Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: 了解如何使用管理角色指定需要不同访问权限级别的管理员来管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8ede97c91254c2dfeace83302c20e310e62be12
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282338"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 管理员角色管理 Teams

使用 Azure Active Directory (Azure AD) ，可以指定需要不同访问权限级别的管理员来管理Microsoft Teams。 管理员可以管理整个 Teams 工作负荷，或者他们具有用于解决呼叫质量问题或管理组织电话需求的委派权限。

## <a name="teams-roles-and-capabilities"></a>Teams角色和功能

有几个可用的 Teams 管理员角色：Teams 管理员、Teams 通信管理员、Teams 通信支持专家、Teams 通信支持工程师Teams设备管理员。 查看下表，了解每个角色可以执行哪些操作，以及管理员可在管理中心和 PowerShell Microsoft Teams哪些工具。

要继续，你必须是管理员。本文提供了获取权限的说明。

<!-- add Global admin role? -->

| 角色                                    | 可以执行这些任务                                                           | 可以访问以下工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 管理员             | 管理Teams服务，以及管理和创建Microsoft 365组。        | 管理中心Microsoft Teams关联的 PowerShell 控件中所有内容，包括：<ul><li> 管理会议，包括会议策略、配置和会议网桥。<sup>1，2</sup></li><li>管理语音，包括呼叫策略和电话号码清单和分配。<sup>1，3</sup></li><li>管理消息传送，包括消息传送策略。<sup>1，2</sup></li><li>管理所有组织范围的设置，包括联合、团队升级和团队客户端设置。<sup>1，2</sup></li><li>管理组织中团队及其关联的设置，包括通过 PowerShell (组管理的成员身份、管理中心管理中心内Teams管理) 。<sup>1，2</sup></li><li>管理Teams认证的设备，并设置和分配配置策略。<sup>1</sup></li><li>使用高级故障排除工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> </li><li>访问管理中心Microsoft Teams报表</li><li> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题，) 受呼叫质量不佳影响的用户。 创建新的呼叫质量报告，根据需要更新和删除呼叫质量报告。 Upload和更新 CQD 建筑物数据。</li><li> [将应用发布到租户管理中心中的Microsoft Teams目录](manage-apps.md)</li></ul> |
| Teams 通信管理员      | 管理呼叫和会议服务Teams功能。               | 管理会议，包括会议策略、配置和会议网桥。<sup>1，2</sup><br><br> 管理语音，包括呼叫策略和电话号码清单和分配。<sup>1，3</sup><br><br> 使用高级疑难解答工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题， 创建新的呼叫质量报告，根据需要更新和删除呼叫质量报告。 Upload和更新 CQD 建筑物数据。|
| Teams 通信支持工程师   | 使用高级工具Teams内部 **通信问题**。 | 使用高级故障排除工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题， |
| Teams通信支持专家 | 使用基本工具Teams内部 **通信** 问题。    | 访问用户配置文件页面，对呼叫分析中的呼叫进行故障排除。 只能查看要搜索的特定用户的用户信息。<sup>2</sup> <br><br> 使用在呼叫质量仪表板中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题 (CQD) 。 |
| Teams设备管理员              | 管理配置为与服务Teams的设备。                    | 管理设备配置和更新、查看已连接外围设备的设备运行状况和状态、设置和应用配置文件，以及重新启动设备。<p>Teams设备管理员角色不提供对呼叫质量数据或呼叫分析的访问权限。 若要查看呼叫质量数据或呼叫分析，需要为Teams管理员角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)模块 (公共版本 1.1.6 或更高版本与 Skype for Business Online Connector.) <br>
<sup>2</sup> [Microsoft Teams管理](./manage-teams-skypeforbusiness-admin-center.md)中心 
 <sup>3</sup> Teams管理员帐户必须具有有效的 Teams 许可证。
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
有关可用于管理域的管理工具Microsoft Teams，请参阅[管理Microsoft Teams。](./manage-teams-skypeforbusiness-admin-center.md)

有关适用于此应用的限制、规范和其他要求Teams，请参阅适用于 Microsoft Teams 的限制[和Microsoft Teams。](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>将用户分配到每个角色

可以将用户分配到 Azure AD 中的这些角色。 若要了解如何在 Azure AD 中向用户分配管理角色，请参阅在 Azure Active Directory 中将用户分配到[管理员Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>可用于每个角色的 Cmdlet

这些管理员角色的 PowerShell 工具大多数都使用 Teams PowerShell 模块，必须注意，这些管理员角色有权访问的一些 cmdlet 可以控制 Skype for Business Online 中使用的共享设置。 

查看 cmdlet 的完整列表：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>相关主题

- [Microsoft TeamsPowerShell 概述](teams-powershell-overview.md)
- [Microsoft TeamsPowerShell](/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中分配团队所有者和成员](./assign-roles-permissions.md)

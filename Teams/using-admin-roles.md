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
description: 了解如何使用管理角色指定需要不同访问权限级别的管理员来管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 201cc1d73166825d729b4581d183ea58cfda64af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093732"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 管理员角色管理 Teams

使用 Azure AD (Azure Active Directory) ，可以指定需要不同访问权限级别的管理员来管理 Microsoft Teams。 管理员可以管理整个 Teams 工作负荷，或者具有用于解决呼叫质量问题或管理组织电话需求的委派权限。

## <a name="teams-roles-and-capabilities"></a>Teams 角色和功能

可以使用多个 Teams 管理员角色：Teams 服务管理员、Teams 通信管理员、Teams 通信支持专家、Teams 通信支持工程师和 Teams 设备管理员。 查看下表，了解每个角色可以执行哪些操作，以及管理员可以在 Microsoft Teams 管理中心和 PowerShell 中使用哪些工具。

要继续，你必须是管理员。本文提供了获取权限的说明。

<!-- add Global admin role? -->

| 角色                                    | 可以执行这些任务                                                           | 可以访问以下工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 服务管理员             | 管理 Teams 服务，以及管理和创建 Microsoft 365 组。        | Microsoft Teams 管理中心和关联的 PowerShell 控件中所有内容，包括：<ul><li> 管理会议，包括会议策略、配置和会议网桥。<sup>1，2</sup></li><li>管理语音，包括呼叫策略和电话号码清单和分配。<sup>1</sup></li><li>管理消息传送，包括消息传送策略。<sup>1，2</sup></li><li>管理所有组织范围的设置，包括联合、团队升级和团队客户端设置。<sup>1，2</sup></li><li>管理组织中团队及其关联设置，包括通过 PowerShell (组管理的成员身份、Teams 管理中心中的团队) 。<sup>1，2</sup></li><li>管理 Teams 认证的设备，并设置和分配配置策略。<sup>1</sup></li><li>使用高级故障排除工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> </li><li>访问 Microsoft Teams 管理中心的所有报表</li><li> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题，) 受呼叫质量不佳影响的用户。 创建新的呼叫质量报告，根据需要更新和删除呼叫质量报告。 上传和更新 CQD 建筑物数据。</li><li> [将应用发布到 Microsoft Teams 管理中心的租户应用目录](manage-apps.md)</li></ul> |
| Teams 通信管理员      | 管理 Teams 服务中的呼叫和会议功能。               | 管理会议，包括会议策略、配置和会议网桥。<sup>1，2</sup><br><br> 管理语音，包括呼叫策略和电话号码清单和分配。<sup>1</sup><br><br> 使用高级疑难解答工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题， 创建新的呼叫质量报告，根据需要更新和删除呼叫质量报告。 上传和更新 CQD 建筑物数据。|
| Teams 通信支持工程师   | 使用高级工具排查 Teams **中的通信** 问题。 | 使用高级故障排除工具集查看用户配置文件页面并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题， |
| Teams 通信支持专家 | 使用基本工具排查 Teams **中的通信** 问题。    | 访问用户配置文件页面，对呼叫分析中的呼叫进行故障排除。 只能查看要搜索的特定用户的用户信息。<sup>2</sup> <br><br> 使用在呼叫质量仪表板中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题 (CQD) 。 |
| Teams 设备管理员              | 管理配置为与 Teams 服务一起使用的设备。                    | 管理设备配置和更新、查看已连接外围设备的设备运行状况和状态、设置和应用配置文件，以及重新启动设备。<p>Teams 设备管理员角色不提供对呼叫质量数据或呼叫分析的访问权限。 若要查看呼叫质量数据或呼叫分析，需要为用户分配 Teams 通信管理员角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) 模块 (公共版本 1.1.6 或更高版本与 Skype for Business Online Connector.) <br>
<sup>2</sup> [Microsoft Teams 管理中心](./manage-teams-skypeforbusiness-admin-center.md)
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
有关可用于管理 Microsoft Teams 的管理工具详细信息，请参阅[管理 Microsoft Teams。](./manage-teams-skypeforbusiness-admin-center.md)

有关适用于 Teams 的限制、规范和其他要求详细信息，请参阅 Microsoft Teams [的限制和规范](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>将用户分配到每个角色

可以将用户分配到 Azure AD 中的这些角色。 若要了解如何在 Azure AD 中向用户分配管理角色，请参阅在 Azure Active Directory 中将用户 [分配到管理员角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>可用于每个角色的 Cmdlet

这些管理员角色的 PowerShell 工具大多数都使用 Teams PowerShell 模块，必须注意，这些管理员角色有权访问的一些 cmdlet 可以控制也用于 Skype for Business Online 的共享设置。 

查看 cmdlet 的完整列表：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>相关主题

- [Microsoft Teams PowerShell 概述](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)
- [在 Microsoft Teams 中分配团队所有者和成员](./assign-roles-permissions.md)
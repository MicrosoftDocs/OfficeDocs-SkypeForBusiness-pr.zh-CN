---
title: 使用 Microsoft Teams 管理员角色管理 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 了解如何使用管理角色来指定需要不同级别访问权限来管理 Teams 的管理员。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615448"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>使用 Microsoft Teams 管理员角色管理 Teams

使用 Azure Active Directory (Azure AD) ，可以指定需要不同级别的访问权限来管理 Microsoft Teams 的管理员。 管理员可以管理整个 Teams 工作负载，也可以拥有委派权限来排查呼叫质量问题或管理组织的电话需求。

## <a name="teams-roles-and-capabilities"></a>Teams 角色和功能

有几个 Teams 管理员角色可用：Teams 管理员、Teams 通信管理员、Teams 通信支持专家、Teams 通信支持工程师和 Teams 设备管理员。 查看下表，了解每个角色可以执行哪些操作，以及管理员可以在 Microsoft Teams 管理中心和 PowerShell 中使用哪些工具。

> [!NOTE]
> Skype for Business Online 管理员可以通过 PowerShell 同时管理 **Teams** 和 **Skype for Business Online** 应用策略。

若要跟进，必须是管理员。本文介绍了获取权限的说明。

<!-- add Global admin role? -->

| 角色                                    | 可以执行这些任务                                                           | 可以访问以下工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 管理员             | 管理 Teams 服务，并管理和创建Microsoft 365 组。        | Microsoft Teams 管理中心和关联的 PowerShell 控件中的所有内容，包括：<ul><li> 管理会议，包括会议策略、配置和会议桥梁。<sup>1，2</sup></li><li>管理语音，包括呼叫策略、电话号码清单和分配。<sup>1，3</sup></li><li>管理消息传送，包括消息传送策略。<sup>1，2</sup></li><li>管理所有组织范围的设置，包括联合身份验证、团队升级和团队客户端设置。<sup>1，2</sup></li><li>管理组织中的团队及其关联设置，包括通过 PowerShell 支持的成员身份 (组管理、Teams 管理中心中的团队管理) 。<sup>1，2</sup></li><li>管理 Teams 认证的设备，并设置和分配配置策略。<sup>1</sup></li><li>使用高级故障排除工具集查看用户配置文件页并排查用户呼叫质量问题。<sup>2</sup> </li><li>访问 Microsoft Teams 管理中心中的所有报表</li><li> 使用呼叫质量仪表板中公开的数据访问、监视和排查租户的呼叫质量和可靠性， (CQD) 到受通话质量不佳影响的用户。 根据需要创建新的呼叫质量报告、更新和删除呼叫质量报告。 上传和更新 CQD 生成数据。</li><li> [在 Microsoft Teams 管理中心将应用发布到租户应用目录](manage-apps.md)</li></ul> |
| Teams 通信管理员      | 管理 Teams 服务中的通话和会议功能。               | 管理会议，包括会议策略、配置和会议桥梁。<sup>1，2</sup><br><br> 管理语音，包括呼叫策略、电话号码清单和分配。<sup>1，3</sup><br><br> 使用高级故障排除工具集查看用户配置文件页并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题，) 到受通话质量不佳影响的用户。 根据需要创建新的呼叫质量报告、更新和删除呼叫质量报告。 上传和更新 CQD 生成数据。|
| Teams 通信支持工程师   | 使用 **高级** 工具排查 Teams 中的通信问题。 | 使用高级故障排除工具集查看用户配置文件页并排查用户呼叫质量问题。<sup>2</sup> <br><br> 使用通话质量仪表板 (CQD 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题，) 到受通话质量不佳影响的用户。 |
| Teams 通信支持专家 | 使用 **基本** 工具排查 Teams 中的通信问题。    | “访问用户配置文件”页，用于排查呼叫分析中的呼叫问题。 只能查看要搜索的特定用户的用户信息。<sup>2</sup> <br><br> 使用呼叫质量仪表板 (CQD) 中公开的数据访问、监视和排查租户的呼叫质量和可靠性问题。 |
| Teams 设备管理员              | 管理配置为与 Teams 服务一起使用的设备。                    | 管理设备配置和更新、查看已连接外围设备的设备运行状况和状态、设置和应用配置文件以及重启设备。<p>Teams 设备管理员角色不提供对调用质量数据或呼叫分析的访问权限。 若要查看通话质量数据或呼叫分析，需要分配 Teams 通信管理员角色。 |

<sup>1</sup> [PowerShell - Microsoft Teams 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/) (公共版本 1.1.6 或更高版本与 Skype for Business Online Connector.) 集成<br>
<sup>2</sup> [Microsoft Teams 管理中心](./manage-teams-skypeforbusiness-admin-center.md)
<sup>3</sup> Teams 管理员帐户必须具有有效的 Teams 许可证。
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
有关可用于管理 Microsoft Teams 的管理工具的详细信息，请参阅 [管理 Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md)。

有关适用于 Teams 的限制、规范和其他要求的详细信息，请参阅 [Microsoft Teams 的限制和规范](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>将用户分配到每个角色

可以在 Azure AD 中将用户分配到这些角色。 若要了解如何向 Azure AD 中的用户分配管理角色，请参阅 [将用户分配给 Azure Active Directory 中的管理员角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="cmdlets-available-for-each-role"></a>可用于每个角色的 Cmdlet

这些管理员角色的大部分 PowerShell 工具都位于 Teams PowerShell 模块中，请务必注意，这些管理员角色有权访问某些 cmdlet 来控制也用于 Skype for Business Online 的共享设置。 

若要查看 cmdlet 的完整列表，请执行以下操作：

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>相关文章

- [Microsoft Teams PowerShell 概述](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [在 Microsoft Teams 中分配团队所有者和成员](./assign-roles-permissions.md)

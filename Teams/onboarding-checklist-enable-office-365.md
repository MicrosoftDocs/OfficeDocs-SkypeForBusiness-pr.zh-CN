---
title: 为 Microsoft Teams 启用 Office 365 服务的上线清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在为 Teams 配置 Office 365 时，按照此清单中的核心、待办任务和活动进行操作。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53d20128607a44a0c8a6a9ef520c2a3808e0d495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238393"
---
# <a name="enable-office-365"></a>启用 Office 365
 
| 否 | 活动或任务| 说明| 已完成？ | 其他信息|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $1  | 创建 Office 365 租户| 必须设置 Office 365 租户，贵组织才能从 Teams 受益。 如果你没有 Office 365 租户，请参阅**其他信息**列中的指导。 | | [设置 Office 365 商业版](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果你需要其他帮助，请联系 Microsoft FastTrack for Office 365 团队](https://fasttrack.microsoft.com/office)。 |
| ●2  | 购买 Office 365 许可证 | 根据你在 Teams 展望阶段完成的工作成果，与采购部门合作以确保贵组织购买了所需的许可证 SKU 或附加项服务，并且它们可以分配给租户。 | | [适用于 Microsoft Teams 的 Office 365 许可](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) <br/><br/>[购买 Office 365 商业版订阅许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3%  | 为租户分配 Office 365 许可证 | 通常，你或你的许可管理员将会收到来自 Microsoft 许可的链接，以便将你的许可证添加到 Office 365 租户。 <br/><br/>根据你购买许可证时使用的渠道，你可能需要访问**其他信息**列中所列的指南之一。 | | [将许可证添加到为使用产品密钥购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[将许可证添加到通过批量许可服务中心购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| √(4)  | 可选：启用通信点数 | 通信点数是一项可选功能，你可以使用它来提供免费使用贵组织的会议网桥电话号码的权限，也可以为会议组织者提供向国际会议参与者拨出的功能。 <br/><br/>除了标准音频会议每用户许可证，批量和许可组织可以选择按分钟付费服务来启用音频会议功能。 <br/><br/>确定贵组织是否需要通信点数，如果需要，应通过将通信点数加载项许可证添加到你的租户来启用此功能。 | | [什么是通信点数？](what-are-communications-credits.md) <br/><br/>[为组织设置通信点数](set-up-communications-credits-for-your-organization.md) <br/><br/>[音频会议按分钟付费](audio-conferencing-pay-per-minute.md) |
| 5 个参与者  | 确认许可证可用于 Office 365 租户 | 访问 Office 365 管理门户，确认门户中显示预期在你的 Office 365 租户中使用的许可证 SKU 和数量。 <br/><br/>使用**其他信息**中的参考完成此过程。 | | [我拥有什么 Office 365 商业版订阅？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6 Mb  | 为你的环境配置身份。 | 可以直接在 Office 365 中创建用户（在在线部署模式中），也可以将本地 Active Directory 中的用户同步到你的 Office 365 租户。 <br/><br/>确定应使用云身份、同步的身份还是联合身份。 确定合适的身份类型不属于此清单的内容范围，但是，**其他信息**列中提供了有关这些选项的信息的链接。 <br/><br/>**注意：** 如果你要使用同步的身份或联合身份，请确保本地用户主体名称 (UPN) 匹配 Office 365 UPN，并且配置了所有所需的属性以与 Azure AD Connect 同步。 有关 Teams 所需的属性，请使用 Skype for Business Online 的属性列表。 | | [了解 Office 365 身份和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[通过向 Office 365 进行目录同步来准备预配用户](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步：同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 示例 7  | 确认租户管理员 | 与你的安全团队合作开发 Office 365 管理模型。 <br/><br/>务必确定并记录所有租户和服务管理员。 | | [关于 Office 365 管理角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8 Mb  | 为你的租户实施管理角色 | 验证你的管理模型满足贵组织的需求，并为你的管理员分配 Office 365 管理角色。 | | [在 Office 365 商业版中分配管理角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 步骤 9  | 登录通话质量仪表板 (CQD) 以上载你的构建信息。 | 每个 Teams 部署都应利用 CQD 来了解使用 Teams 的所有通话的质量和可靠性。 <br><br>使用**其他信息**列中所列的 CQD 指导以充分利用此工具。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[《体验质量评审指南》](https://aka.ms/qerguide) <br/><br/>[体验质量评审模板](https://aka.ms/qertemplates) <br/><br/>[为 Microsoft Teams 和 Skype for Business Online 中启用和使用通话质量仪表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10%  | 验证已处理构建信息，并且通话质量仪表板 (CQD) 可用于你的租户。 | | | [通话质量仪表板](https://cqd.lync.com) |

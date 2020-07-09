---
title: 加入清单-启用 Microsoft 365 或 Office 365 服务
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在为团队配置 Microsoft 365 或 Office 365 时，请按照此清单中的核心、待办任务和活动进行操作。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 28a89502a628c3cc9dcdf2c910371bb37568f194
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085168"
---
# <a name="enable-microsoft-365-or-office-365"></a>启用 Microsoft 365 或 Office 365
 
| 否 | 活动或任务| 说明| 已完成？ | 其他信息|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $1  | 创建 Microsoft 365 或 Office 365 组织| 在你的组织可以享受团队的好处之前，你必须设置 Microsoft 365 或 Office 365 组织。 如果您没有 Microsoft 365 或 Office 365 组织，请参阅 "**其他信息**" 列中的指南。 | | [设置 Microsoft 365 或 Office 365 for business](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果需要其他帮助，microsoft 365 或 Office 365 团队的 Microsoft FastTrack 可提供帮助](https://fasttrack.microsoft.com/office) |
| ●2  | 购买 Microsoft 365 或 Office 365 许可证 | 根据你在团队构想阶段执行的工作结果，与你的采购组协作，确保你的组织已购买所需的许可证 Sku 或加载项服务，并已准备好将其分配给租户。 | | [Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) <br/><br/>[购买 Microsoft 365 或 Office 365 for Business 订阅的许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3%  | 将 Microsoft 365 或 Office 365 许可证分配给 organizaton | 通常，你或你的授权管理员将收到来自 Microsoft 许可证的链接，以将你的许可证添加到 Microsoft 365 或 Office 365 组织。 <br/><br/>根据你购买许可证时使用的渠道，你可能需要访问**其他信息**列中所列的指南之一。 | | [将许可证添加到为使用产品密钥购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[将许可证添加到通过批量许可服务中心购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| √(4)  | 可选：启用通信点数 | 通讯信用点数是一项可选功能，可用于提供您的组织的会议桥电话号码的免费访问权限，或者让会议组织者能够拨出到国际会议参与者。 <br/><br/>除了标准音频会议每用户许可证，批量和许可组织可以选择按分钟付费服务来启用音频会议功能。 <br/><br/>确定贵组织是否需要通信点数，如果需要，应通过将通信点数加载项许可证添加到你的租户来启用此功能。 | | [什么是通信点数？](what-are-communications-credits.md) <br/><br/>[为组织设置通信点数](set-up-communications-credits-for-your-organization.md) <br/><br/>[音频会议按分钟付费](audio-conferencing-pay-per-minute.md) |
| 5 个参与者  | 确认许可证对 Microsoft 365 或 Office 365 组织可用 | 转到 Microsoft 365 管理中心并验证它是否显示你的 Microsoft 365 或 Office 365 组织中所需的许可证 Sku 和数量。 <br/><br/>使用**其他信息**中的参考完成此过程。 | | [我有什么 Microsoft 365 或 Office 365 for business 订阅？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6 Mb  | 为你的环境配置身份。 | 可直接在 Microsoft 365 或 Office 365 中创建用户（在联机部署模型中）或从本地 Active Directory 同步到 Microsoft 365 或 Office 365 组织。 <br/><br/>确定应使用云身份、同步的身份还是联合身份。 确定正确的标识类型超出了本清单的范围;但是，你将在 "**其他信息**" 列中找到有关这些选项的信息的链接。 <br/><br/>**注意：** 如果你使用的是同步或联合身份，请确保本地用户主体名称（Upn）与 Microsoft 365 或 Office 365 Upn 匹配，并且所有所需属性均配置为与 Azure AD Connect 同步。 有关 Teams 所需的属性，请使用 Skype for Business Online 的属性列表。 | | [了解 Microsoft 365 或 Office 365 身份和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[准备通过目录同步将用户预配到 Microsoft 365 或 Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步：同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 示例 7  | 确认租户管理员 | 与安全团队协作开发 Microsoft 365 或 Office 365 管理模型。 <br/><br/>务必确定并记录所有租户和服务管理员。 | | [关于 Microsoft 365 或 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8 Mb  | 为你的租户实施管理角色 | 验证你的管理模型是否满足你的组织的需求，并将 Microsoft 365 或 Office 365 管理员角色分配给你的管理员。 | | [在 Microsoft 365 或 Office 365 for business 中分配管理员角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 步骤 9  | 登录通话质量仪表板 (CQD) 以上载你的构建信息。 | 每个 Teams 部署都应利用 CQD 来了解使用 Teams 的所有通话的质量和可靠性。 <br><br>使用**其他信息**列中所列的 CQD 指导以充分利用此工具。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[《体验质量评审指南》](https://aka.ms/qerguide) <br/><br/>[体验质量评审模板](https://aka.ms/qertemplates) <br/><br/>[为 Microsoft Teams 和 Skype for Business Online 中启用和使用通话质量仪表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10%  | 验证已处理构建信息，并且通话质量仪表板 (CQD) 可用于你的租户。 | | | [通话质量仪表板](https://cqd.teams.microsoft.com) |

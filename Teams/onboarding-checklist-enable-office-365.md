---
title: 载入清单 - 启用 Microsoft 365 或 Office 365 服务
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 配置 Microsoft 365 或 Office 365 for Teams 时，请遵循此清单中的核心任务和活动。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9f9d9e40968d8d94f92b3fee5807d0d16bd2c0e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802292"
---
# <a name="enable-microsoft-365-or-office-365"></a>启用 Microsoft 365 或 Office 365
 
| 否 | 活动或任务| 说明| 已完成？ | 其他信息|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $1  | 创建 Microsoft 365 或 Office 365 组织| 必须先设置 Microsoft 365 或 Office 365 组织，组织才能享受 Teams 的好处。 如果你没有 Microsoft 365 或 Office 365 组织，请参阅"其他信息"列中 **的** 指南。 | | [设置 Microsoft 365 或 Office 365 商业版](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果需要其他帮助，Microsoft FastTrack for Microsoft 365 或 Office 365 团队可提供帮助](https://fasttrack.microsoft.com/office) |
| ●2  | 购买 Microsoft 365 或 Office 365 许可证 | 根据在 Teams"构想"阶段完成的工作的结果，与采购组合作，确保组织已购买必要的许可证 SKUS 或附加服务，并且已准备好分配给租户。 | | [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) <br/><br/>[购买 Microsoft 365 或 Office 365 商业版订阅的许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3%  | 将 Microsoft 365 或 Office 365 许可证分配给组织 | 通常，你或你的许可管理员将收到来自 Microsoft 许可的链接，以将你的许可证添加到你的 Microsoft 365 或 Office 365 组织。 <br/><br/>根据你购买许可证时使用的渠道，你可能需要访问 **其他信息** 列中所列的指南之一。 | | [将许可证添加到为使用产品密钥购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[将许可证添加到通过批量许可服务中心购买的订阅](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| √(4)  | 可选：启用通信点数 | 通信积分是一项可选功能，用于为组织的会议网桥电话号码提供免费访问，或使会议组织者能够拨出给国际会议参与者。 <br/><br/>除了标准音频会议每用户许可证，批量和许可组织可以选择按分钟付费服务来启用音频会议功能。 <br/><br/>确定贵组织是否需要通信点数，如果需要，应通过将通信点数加载项许可证添加到你的租户来启用此功能。 | | [什么是通信点数？](what-are-communications-credits.md) <br/><br/>[为组织设置通信点数](set-up-communications-credits-for-your-organization.md) <br/><br/>[音频会议按分钟付费](audio-conferencing-pay-per-minute.md) |
| 5 个参与者  | 确认适用于 Microsoft 365 或 Office 365 组织的许可证 | 转到 Microsoft 365 管理中心，验证其是否显示 Microsoft 365 或 Office 365 组织中预期许可证 SKUS 和数量。 <br/><br/>使用 **其他信息** 中的参考完成此过程。 | | [我拥有哪些 Microsoft 365 或 Office 365 商业版订阅？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6 Mb  | 为你的环境配置身份。 | 可以直接在 Microsoft 365 或 Office 365 (联机部署模型) 中创建用户，或者从本地 Active Directory 同步到 Microsoft 365 或 Office 365 组织。 <br/><br/>确定应使用云身份、同步的身份还是联合身份。 确定正确的标识类型超出了此清单的范围;但是，您将在"其他信息"列中找到有关 **这些选项的信息** 的链接。 <br/><br/>**注意：** 如果使用同步或联合标识，请确保本地用户主体名称 (UPN) 与 Microsoft 365 或 Office 365 UPN 匹配，并且所有必需的属性都配置为与 Azure AD Connect 同步。 有关 Teams 所需的属性，请使用 Skype for Business Online 的属性列表。 | | [了解 Microsoft 365 或 Office 365 标识和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[准备通过目录同步将用户预配到 Microsoft 365 或 Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步：同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 示例 7  | 确认租户管理员 | 与安全团队协作，开发 Microsoft 365 或 Office 365 管理模型。 <br/><br/>务必确定并记录所有租户和服务管理员。 | | [关于 Microsoft 365 或 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8 Mb  | 为你的租户实施管理角色 | 验证管理模型是否满足组织的需求，并将 Microsoft 365 或 Office 365 管理员角色分配给管理员。 | | [在 Microsoft 365 或 Office 365 商业版中分配管理员角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 步骤 9  | 登录通话质量仪表板 (CQD) 以上载你的构建信息。 | 每个 Teams 部署都应利用 CQD 来了解使用 Teams 的所有通话的质量和可靠性。 <br><br>使用 **其他信息** 列中所列的 CQD 指导以充分利用此工具。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[《体验质量评审指南》](https://aka.ms/qerguide) <br/><br/>[体验质量评审模板](https://aka.ms/qertemplates) <br/><br/>[为 Microsoft Teams 和 Skype for Business Online 中启用和使用通话质量仪表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10%  | 验证已处理构建信息，并且通话质量仪表板 (CQD) 可用于你的租户。 | | | [通话质量仪表板](https://cqd.teams.microsoft.com) |

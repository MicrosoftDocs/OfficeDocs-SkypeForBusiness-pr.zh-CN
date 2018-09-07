---
title: 启用的 Microsoft 团队的 Office 365 服务入职培训清单
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 配置 Office 365 团队时，请按照的核心、 待办事项任务和此检查表中的活动。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e657fcefbd86f361f41e47369452b87f6463c83
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865140"
---
# <a name="enable-office-365"></a>启用 Office 365
 
| 否 | 活动或任务| 说明| 已完成？ | 其他信息|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 创建 Office 365 租户| 您的组织可以享受团队之前，必须设置 Office 365 租户。 请参阅是否您不具备 Office 365 租户，请参阅**的其他信息**列中的指南。 | | [设置 Office 365 for business](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果您需要其他帮助，Office 365 团队 Microsoft FastTrack 是可用来帮助](https://fasttrack.microsoft.com/office) |
| 2  | 购买 Office 365 许可证 | 根据的工作的团队 Envision 阶段未的结果，使用您的采购组，以确保您的组织购买必要的许可证，Sku 或加载项服务，他们便可分配给租户。 | | [适用于 Microsoft Teams 的 Office 365 许可](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) <br/><br/>[购买 Office 365 业务订阅许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 为租户分配 Office 365 许可证 | 通常情况下，您许可管理员将收到一个链接从 Microsoft 许可将许可证添加到 Office 365 租户。 <br/><br/>根据您用于购买许可证的通道，您可能需要可访问**的其他信息**列中列出的指南之一。 | | [将许可证添加到使用产品密钥付费订阅](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[通过批量许可服务中心购买订阅中添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 可选： 启用 Communications 字幕式 | Communications 字幕式是一个可选的功能，您使用免费访问提供有关贵组织的会议桥接电话号码，或使会议组织者能够拨出到国际会议参与者。 <br/><br/>标准的音频会议的每用户许可证，除了卷和授权组织可以选择的付薪每分钟报价启用音频会议功能。 <br/><br/>决定是否需要对您的组织，Communications 字幕式和 — 如果 — 启用通过将通信字幕式加载项许可证添加到您的租户。 | | [什么是通信点数？](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) <br/><br/>[为组织设置通信点数](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization) <br/><br/>[音频会议按分钟付费](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute) |
| 5  | 确认许可证适用于 Office 365 租户 | 转到 Office 365 管理门户并验证显示的许可证 Sku 和 Office 365 租户中预期的数量。 <br/><br/>使用中**的其他信息**的引用以遍历通过此过程。 | | [是否有哪些业务订阅的 Office 365？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 配置您的环境的标识。 | 用户可以在 Office 365 中创建直接 （在 online 部署模型中） 或从内部部署 Active Directory 同步到 Office 365 租户。 <br/><br/>确定是否应使用云标识、 同步的标识或联盟的标识。 确定正确的标识类型已超出本检查表; 范围但是，您可以**的其他信息**列中找到这些选项的信息的链接。 <br/><br/>**注意：** 如果您使用同步或联合的身份，确保内部部署用户主体名称 (Upn) 匹配 Office 365 Upn，并与 Azure AD 连接同步配置所有必需的属性。 对于所需的团队的属性，使用属性列表的 Skype 业务 online。 | | [了解 Office 365 标识和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[准备设置用户通过目录同步到 Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD 连接同步： 同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 确认租户管理员 | 使用您安全团队开发 Office 365 管理模型。 <br/><br/>请务必确定并记录所有租户和服务的管理员。 | | [有关 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 实现您的租户管理角色 | 验证您的管理模型满足组织的需求，并将 Office 365 管理员角色分配给您的管理员。 | | [分配 Office 365 中的业务的管理员角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 构建信息登录到呼叫质量仪表板 (CQD) 上载。 | 每个团队部署应利用 CQD 要深入的质量和可靠性使用团队的所有呼叫。 <br><br>使用**的其他信息**列中列出的 CQD 指南获得此工具的最大好处。 | | [规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[《体验质量评审指南》](https://aka.ms/qerguide) <br/><br/>[质量体验查看模板](https://aka.ms/qertemplates) <br/><br/>[打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10  | 验证处理构建信息，以及呼叫质量仪表板 (CQD) 是租户可操作。 | | | [通话质量仪表板](https://cqd.lync.com) |
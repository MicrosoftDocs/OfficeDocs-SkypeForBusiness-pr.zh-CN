---
title: 载入清单 - 启用Microsoft 365或Office 365服务
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 为任务配置任务或任务时，请遵循此清单中的核心Microsoft 365 Office 365 Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e082b1226df351768d33e2ab04ed6902cafe55502816aa757de8d76a51004ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324841"
---
# <a name="enable-microsoft-365-or-office-365"></a>启用Microsoft 365或Office 365
 
| 弱 | 活动或任务| 说明| 已完成？ | 其他信息|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 创建Microsoft 365或Office 365组织| 在组织享受组织服务Teams之前，必须设置Microsoft 365或Office 365组织。 如果您没有组织或Microsoft 365，Office 365"其他信息"**列中的** 指南。 | | [为Microsoft 365或Office 365设置服务](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果需要其他帮助，Microsoft FastTrack Microsoft 365 或 Office 365 团队可提供帮助](https://fasttrack.microsoft.com/office) |
| 2  | 购买Microsoft 365或Office 365许可证 | 根据在 Teams 构想阶段中完成的工作的结果，与采购组合作，确保组织已购买所需的许可证 SKUS 或附加服务，并且已准备好将其分配给租户。 | | [Microsoft Teams服务说明](/office365/servicedescriptions/teams-service-description) <br/><br/>[为商业版订阅Microsoft 365 Office 365许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 将Microsoft 365或Office 365许可证分配给组织 | 通常，你或你的许可管理员将收到来自 Microsoft 许可的链接，以将你的许可证添加到你的Microsoft 365或Office 365组织。 <br/><br/>根据用于购买许可证的渠道，可能需要访问"其他信息"列中列出的 **指南之** 一。 | | [向使用产品密钥付费的订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[向通过批量许可服务中心购买的订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 可选：启用通信信用额度 | 通信积分是一项可选功能，用于为组织的会议网桥电话号码提供免费访问，或让会议组织者能够拨出给国际会议参与者。 <br/><br/>除了标准的音频会议每用户许可证外，批量和许可组织还可以选择按分钟付费产品/服务来启用音频会议功能。 <br/><br/>确定组织是否需要通信信用额度，如果需要，则通过将通信信用额度附加许可证添加到租户来启用通信信用额度。 | | [什么是通信点数？](what-are-communications-credits.md) <br/><br/>[设置组织的通信点数](set-up-communications-credits-for-your-organization.md) <br/><br/>[音频会议按分钟付费](audio-conferencing-pay-per-minute.md) |
| 5  | 确认许可证适用于组织Microsoft 365 Office 365许可证 | 转到"Microsoft 365 管理中心"并验证它是否显示许可证 SKUS 和预期在组织或Microsoft 365 Office 365数量。 <br/><br/>使用要 **演练** 此过程的其他信息中的参考。 | | [我Microsoft 365 Office 365订阅的订阅或套餐？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 配置标识的环境。 | 用户可以在 Microsoft 365 中创建，Office 365直接 (联机部署模型) ，或者从本地 Active Directory 同步到 Microsoft 365 或 Office 365 组织。 <br/><br/>确定是应该使用云标识、同步标识还是联合标识。 确定正确的标识类型超出了此清单的范围;但是，您将在"其他信息"列中找到有关 **这些选项的信息** 的链接。 <br/><br/>**注意：** 如果使用同步或联合标识，请确保本地用户主体名称 (UPN) 与 Microsoft 365 或 Office 365 UPN 匹配，并且所有必需的属性都配置为与 Azure AD 连接 同步。 对于应用所需的属性Teams，请使用 Skype for Business Online 的属性列表。 | | [了解Microsoft 365或Office 365标识Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[准备通过目录同步将用户预配到Microsoft 365或Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD 连接同步：同步到 Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 确认租户管理员 | 与安全团队协作，开发Microsoft 365或Office 365模型。 <br/><br/>请务必标识并记录所有租户和服务管理员。 | | [关于Microsoft 365或Office 365管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 为租户实现管理角色 | 验证管理模型是否满足组织的需求，并将Microsoft 365或Office 365管理员角色分配给管理员。 | | [在企业Microsoft 365 Office 365管理员角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 登录到 CQD 呼叫质量 (仪表板) 上载建筑物信息。 | 每个 Teams 部署都应利用 CQD 来深入了解使用 Teams 的所有调用的质量和可靠性。 <br><br>使用"其他信息"列中列出的 CQD **指南可** 充分利用此工具。 | | [服务管理和质量规划](./prepare-network.md) <br/><br/>[《体验质量评审指南》](./quality-of-experience-review-guide.md) <br/><br/>[质量体验评审模板](https://aka.ms/qertemplates) <br/><br/>[打开和使用呼叫质量仪表板Microsoft Teams Skype for Business Online](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[Upload建筑物信息](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 验证是否处理了建筑物信息，并针对租户 (CQD) 呼叫质量仪表板。 | | | [呼叫质量仪表板](https://cqd.teams.microsoft.com) |
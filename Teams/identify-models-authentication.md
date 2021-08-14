---
title: 标识模型和身份验证Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解适用于云环境的不同标识Microsoft Teams，例如仅云和混合。 此外，还了解多重身份验证。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cea02bf51c474e9be7aca205aa73fd9558f03ad104e5e1a1bde8f5ddc39e95ff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342976"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>标识模型和身份验证Microsoft Teams

Microsoft Teams支持可用于 Microsoft 365 和 Office 365 的所有标识模型，其中包括：

- **仅云**：用户帐户在 Azure AD Microsoft 365 或 Office 365 中创建Azure Active Directory () 。 用户登录凭据 (帐户名和密码) Azure AD 进行验证。

- **混合**：用户帐户通常托管在本地 Active Directory 域服务中， (AD DS) 林。 根据配置，凭据验证可通过 Azure AD、AD DS 或联合标识提供者完成。 此模型使用 Azure AD 数据库将目录从 AD DS 同步到 Azure AD 连接。

有关详细信息，请参阅Microsoft 365[模型和 Azure AD。](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>配置

根据组织决定使用哪个标识模型和配置，实施步骤可能会有所不同。

如果尚未部署标识Microsoft 365或Office 365，请使用此表。 

|标识模式 |部署清单  |其他信息  |
|---------|---------|---------|
|全部     |<ol type="1"><li>比较Microsoft 365和Office 365选项，并获取订阅和租户。</li><li>为租户Microsoft 365 Office 365或组织。</li><li>为Microsoft 365 Office 365购买许可证或许可证</li><li>配置域和管理员用户帐户。</li></ol>  |<ul><li>[Office 365计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[比较Microsoft 365计划](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[购买或删除订阅许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[向订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[为Microsoft 365设置服务](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用设置向导添加域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)可为您提供帮助。  |
|云标识     |<ul><li>使用帐户创建Microsoft 365 管理中心</li></ul> |<ul style="list-style-type:none"><li>[添加用户并分配许可证](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|混合标识     |<ol type="1"><li>安装 Azure AD 连接。</li><li>配置目录同步。</li><li>使用 AD DS 工具管理用户和组。</li></ol> |<ul style="list-style-type:none"><li>[设置目录同步](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|使用联合身份验证的混合标识    |<ol type="1"><li>安装和配置联合标识提供者，例如 AD FS。</li><li>安装 Azure AD 连接并配置目录同步和联合身份验证。</li><li>使用 AD DS 工具管理用户和组。</li></ol> |<ul><li>[规划 AD FS 部署](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[清单：部署联合服务器场](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[为 AD FS 配置 Extranet 访问](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[在 AD FS 与 Azure AD 之间设置信任](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[使用 ADFS 验证和管理单一登录](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[设置目录同步](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>多因素身份验证

密码是最常见的身份验证方法，用于登录计算机或联机服务，但它们也是最易受攻击的。 用户可以选择简单的密码，并使用相同的密码进行不同计算机和服务的多个登录。 

若要为登录提供附加的安全级别，请使用多重身份验证 (MFA) ，这要求使用密码和其他验证方法，例如：

- 发送到电话的短信，要求用户键入验证码。
- 电话呼叫。
- Microsoft Authenticator智能手机应用。
- 混合标识和联合身份验证提供的其他方法。

MFA 受包括Microsoft 365或Office 365计划Microsoft Teams。 强烈建议至少为分配有管理员角色的帐户（例如服务管理员）Teams MFA。 [](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)

还应向用户推出 MFA。 用户注册 MFA 后，下次登录时，他们将看到一条消息，要求他们设置其他验证方法。 

有关详细信息，请参阅适用于的[多重身份验证Microsoft 365。](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
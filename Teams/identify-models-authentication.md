---
title: 适用于 Microsoft 团队的身份模型和身份验证
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
description: 了解 Microsoft 团队的不同标识模型，例如仅限云和混合模型。 此外，还了解多重身份验证。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277112"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>适用于 Microsoft 团队的身份模型和身份验证

Microsoft 团队支持 Microsoft 365 和 Office 365 提供的所有标识模型，其中包括：

- **仅限云**：在 Microsoft 365 或 Office 365 中创建和管理用户帐户，并将其存储在 Azure Active Directory (azure AD) 中。 用户登录凭据 (由 Azure AD 验证的帐户名称和密码) 。

- **混合**：用户帐户通常在本地 Active Directory 域服务中管理 (AD DS) 林。 凭据验证可以由 Azure AD、AD DS 或联合身份提供程序执行，具体取决于配置。 此模型通过 Azure AD Connect 将目录同步从 AD DS 使用到 Azure AD。

有关详细信息，请参阅 [Microsoft 365 标识模型和 AZURE AD](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)。

## <a name="configurations"></a>配置

根据组织对您使用的身份模型和配置的决定，实施步骤可能会有所不同。

如果尚未部署 Microsoft 365 或 Office 365 和标识模型，请使用此表。 

|标识模式 |部署清单  |其他信息  |
|---------|---------|---------|
|全部     |<ol type="1"><li>比较 Microsoft 365 和 Office 365 计划选项并获取订阅和租户。</li><li>为你的租户创建 Microsoft 365 或 Office 365 组织。</li><li>购买适用于租户的 Microsoft 365 或 Office 365 许可证</li><li>配置域和管理员用户帐户。</li></ol>  |<ul><li>[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[比较 Microsoft 365 for business 计划](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[购买或删除订阅许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[向订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[设置 Microsoft 365 for business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用设置向导添加域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 可为您提供帮助。  |
|云标识     |<ul><li>使用 Microsoft 365 管理中心创建用户帐户</li></ul> |<ul style="list-style-type:none"><li>[添加用户并分配许可证](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|混合标识     |<ol type="1"><li>安装 Azure AD Connect。</li><li>配置目录同步。</li><li>通过 AD DS 工具管理用户和组。</li></ol> |<ul style="list-style-type:none"><li>[设置目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|联合身份验证的混合标识    |<ol type="1"><li>安装和配置联合身份提供程序，如 AD FS。</li><li>安装 Azure AD Connect 和配置目录同步和联合身份验证。</li><li>通过 AD DS 工具管理用户和组。</li></ol> |<ul><li>[规划 AD FS 部署](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[清单：部署联合服务器场](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[为 AD FS 配置 Extranet 访问](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[在 AD FS 与 Azure AD 之间设置信任](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[使用 ADFS 验证和管理单一登录](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[设置目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>多因素身份验证

密码是登录到计算机或联机服务的最常用身份验证方法，但它们也最容易受到攻击。 用户可以选择简单的密码，并对不同的计算机和服务使用相同的密码进行多个登录。 

若要为登录提供额外的安全级别，请使用多因素身份验证 (MFA) ，该身份验证需要密码和其他验证方法，如：

- 发送到要求用户键入验证码的电话的文本消息。
- 电话通话。
- Microsoft 身份验证器智能手机应用。
- 混合标识和联合身份验证提供的其他方法。

任何包含 Microsoft 团队的 Microsoft 365 或 Office 365 计划均支持 MFA。 强烈建议您至少需要对 [分配了管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)的帐户进行 MFA，如团队服务管理员。

您还应向您的用户推出 "MFA"。 用户注册了 MFA 后，下次登录时，他们将看到一条消息，要求他们设置其其他验证方法。 

有关详细信息，请参阅 [Microsoft 365 的多重身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)。

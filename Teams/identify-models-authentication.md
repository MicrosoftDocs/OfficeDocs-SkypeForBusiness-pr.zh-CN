---
title: 标识模型和身份验证
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2017
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
description: 了解 Microsoft Teams 中的不同标识模式，例如，云、同步和联合。 此外，还了解多重身份验证。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 330a197f2e042ee8d87e294f9ff822c6bf6d5ac6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121562"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft Teams 中的标识模式和身份验证
==========================================

Microsoft 团队支持 Microsoft 365 和 Office 365 提供的所有标识模型。 支持的标识模式包括：

-   **云标识**：在此模型中，用户在 Microsoft 365 或 Office 365 中创建和管理并存储在 Azure active directory 中，密码由 Azure active directory 验证。

-   **同步标识**：在此模式下，在本地服务器中管理用户标识，帐户和密码哈希同步到云端。 与在云端一样，用户在本地输入相同密码，登录时，由 Azure Active Directory 验证密码。 此模式使用 Microsoft Azure Active Directory Connect 工具。

-   **联合标识**：此模式要求本地标识提供者验证包含用户密码的同步标识。 使用此模式时，不需要将密码同步到 Azure AD，使用 Active Directory 联合身份验证服务 (ADFS) 或第三方标识提供者按照本地 Active Directory 对用户进行身份验证。

<a name="configurations"></a>配置
--------------

根据组织对实现和使用哪些身份模型的决定，实现要求可能会有所不同。 请参阅下面的要求表格，以确保你的部署满足这些先决条件。 如果已部署 Microsoft 365 或 Office 365 并已实现身份和身份验证方法，则可以跳过这些步骤。


|标识模式 |部署清单  |其他信息  |
|---------|---------|---------|
|全部     |<ol type="1"><li>比较 Microsoft 365 和 Office 365 计划选项并获取订阅</li><li>创建 Microsoft 365 或 Office 365 组织</li><li>将 Microsoft 365 或 Office 365 许可证分配给租户</li><li>配置域和管理用户</li><li>继续按照标识模式特定的说明操作</li></ol>          |<ul style="list-style-type:none"><li>[Microsoft 365 和 Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[比较 Microsoft 365 应用 for business 计划](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[管理订阅许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[向订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[设置 Microsoft 365 for business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用设置向导添加用户和域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>注意：如果你需要帮助， [Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618)可提供帮助。</li></ul>          |
|云标识     |<ol type="1"><li>使用 Microsoft 365 管理中心创建用户</li></ol>           |<ul style="list-style-type:none"><li>[单独或批量添加用户](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|同步标识     |<ol type="1"><li>安装 Azure AD Connect</li><li>配置目录同步</li><li>使用本地 Active Directory 管理工具创建用户</li></ol>         |<ul style="list-style-type:none"><li>[设置目录同步](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注意：必须为 Microsoft 365 和 Office 365 同步密码哈希，才能执行身份验证。</li></ul>         |
|联合标识    |<ol type="1"><li>安装 Azure AD Connect</li><li>配置目录同步</li><li>安装和配置联合标识提供者（建议 ADFS）</li><li>使用本地 Active Directory 管理工具创建用户</li></ol>           |<ul style="list-style-type:none"><li>[设置目录同步](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[规划 AD FS 部署](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[清单：部署联合服务器场](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[为 AD FS 配置 Extranet 访问](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[在 AD FS 与 Azure AD 之间设置信任](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[使用 ADFS 验证和管理单一登录](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD 联合兼容性列表](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>注意：不需要将密码同步到 Azure Active Directory。</li></ul>         |

有关其他详细信息，请参阅[选择登录模型](https://go.microsoft.com/fwlink/?linkid=854626)和[了解身份模型和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)指南。


<a name="multi-factor-authentication"></a>多重身份验证
----------------------------

Microsoft 365 和 Office 365 计划支持多重身份验证（MFA），从而提高了用户登录到服务的安全性。 通过 MFA，用户在正确输入密码后，需要在其智能手机上确认电话呼叫、短信或应用通知。 仅当通过此辅助身份验证因素后，用户才可以登录。

任何包含 Microsoft 团队的 Microsoft 365 或 Office 365 计划均支持多重因素身份验证。 下面的 "授权" 部分稍后将讨论包含 Microsoft 团队的订阅计划。

用户注册 MFA 后，下次用户登录时，他们将看到一条消息，询问他们是否设置其第二身份验证因素。 支持的身份验证方法如下：


|租户类型  |可用的 MFA 辅助因素选项  |备注  |
|---------|---------|---------|
|**仅限云**     |Microsoft 365 或 Office 365 的 MFA <ul><li>电话</li><li>短信</li><li>移动应用通知</li><li>移动应用代码</li></ul>        | |
|**混合设置（同步标识或联合标识模式）**     |<ul><li>Microsoft 365 或 Office 365 的 MFA</li><li>Azure MFA 模块（集成了 ADFS）</li><li>物理或虚拟智能卡（集成了 ADFS）</li></ul>         |注意：其他 MFA 解决方案可通过[AZURE AD 标识提供程序兼容性文档](https://www.microsoft.com/download/details.aspx?id=56843)使用         |

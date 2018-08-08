---
title: Microsoft Teams 中的标识模式和身份验证
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
description: 了解 Microsoft Teams 中的不同标识模式，例如，云、同步和联合。 此外，还了解多重身份验证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdc9c61938afe2173f5fe1326a0431d781144c7b
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "18999781"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft Teams 中的标识模式和身份验证
==========================================

Microsoft Teams 支持在 Office 365 中可以使用的所有标识模式。 支持的标识模式包括：

-   **云标识**：在此模式下，在 Office 365 中创建和管理用户，在 Azure Active Directory 中存储用户，以及由 Azure Active Directory 验证密码。

-   **同步标识**：在此模式下，在本地服务器中管理用户标识，帐户和密码哈希同步到云端。 与在云端一样，用户在本地输入相同密码，登录时，由 Azure Active Directory 验证密码。 此模式使用 Microsoft Azure Active Directory Connect 工具。

-   **联合标识**：此模式要求本地标识提供者验证包含用户密码的同步标识。 使用此模式时，不需要将密码同步到 Azure AD，使用 Active Directory 联合身份验证服务 (ADFS) 或第三方标识提供者按照本地 Active Directory 对用户进行身份验证。

<a name="configurations"></a>配置
--------------

根据贵组织决定要实施和使用的标识模式，实施要求可能会有所不同。 请参阅下面的要求表格，以确保你的部署满足这些先决条件。 如果你已部署 Office 365 且已实施标识和身份验证方法，你可以跳过这些步骤。


|标识模式 |部署清单  |其他信息  |
|---------|---------|---------|
|全部     |<ol type="1"><li>比较 Office 365 计划选项并获取订阅</li><li>创建 Office 365 租户</li><li>为租户分配 Office 365 许可证</li><li>配置域和管理用户</li><li>继续按照标识模式特定的说明操作</li></ol>          |<ul style="list-style-type:none"><li>[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[比较 Office 365 商业版计划](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[购买适用于 Office 365 for business 订阅的许可证](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[向订阅添加许可证](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[设置 Office 365 for business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用设置向导添加用户和域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>注意：如果你需要协助，请联系 [Microsoft FastTrack for Office 365 团队](https://go.microsoft.com/fwlink/?linkid=854618)。</li></ul>          |
|云标识     |<ol type="1"><li>使用 Office 365 管理门户创建用户</li></ol>           |<ul style="list-style-type:none"><li>[以单个或批量方式向 Office 365 添加用户](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|同步标识     |<ol type="1"><li>安装 Azure AD Connect</li><li>配置目录同步</li><li>使用本地 Active Directory 管理工具创建用户</li></ol>         |<ul style="list-style-type:none"><li>[为 Office 365 设置目录同步](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注意：必须同步密码哈希，Office 365 才能执行身份验证。</li></ul>         |
|联合标识    |<ol type="1"><li>安装 Azure AD Connect</li><li>配置目录同步</li><li>安装和配置联合标识提供者（建议 ADFS）</li><li>使用本地 Active Directory 管理工具创建用户</li></ol>           |<ul style="list-style-type:none"><li>[为 Office 365 设置目录同步](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[规划 AD FS 部署](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[清单：部署联合服务器场](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[为 AD FS 配置 Extranet 访问](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[在 AD FS 与 Azure AD 之间设置信任](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[使用 ADFS 验证和管理单一登录](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD 联合兼容性列表](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>注意：不需要将密码同步到 Azure Active Directory。</li></ul>         |

有关其他详细信息，请参阅[选择 Office 365 的登录模式](https://go.microsoft.com/fwlink/?linkid=854626)和[了解 Office 365 标识和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)指南。

<a name="multi-factor-authentication"></a>多重身份验证 
----------------------------

Office 365 计划支持多重身份验证 (MFA)，这可提高用户登录 Office 365 服务的安全性。 Office 365 应用 MFA 时，在用户正确输入其密码后，需要用户在其智能手机上确认电话、短信或应用通知。 仅当通过此辅助身份验证因素后，用户才可以登录。

包含 Microsoft Teams 的任何 Office 365 计划都支持多重身份验证。 包含 Microsoft Teams 的 Office 365 订阅计划稍后将在下面的“许可”一节中讨论。

用户注册 MFA 后，下次登录时，他们将看到要求其设置辅助身份验证因素的消息。 支持的身份验证方法如下：


|租户类型  |可用的 MFA 辅助因素选项  |备注  |
|---------|---------|---------|
|**仅限云**     |适用于 Office 365 的 MFA <ul><li>电话</li><li>短信</li><li>移动应用通知</li><li>移动应用代码</li></ul>        |[Office 365 部署的多重身份验证计划](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**混合设置（同步标识或联合标识模式）**     |<ul><li>适用于 Office 365 的 MFA</li><li>Azure MFA 模块（集成了 ADFS）</li><li>物理或虚拟智能卡（集成了 ADFS）</li></ul>         |注意：[与 Azure AD 联合兼容的标识提供者](http://go.microsoft.com/fwlink/p/?LinkId=510953)中提供了其他 MFA 解决方案         |

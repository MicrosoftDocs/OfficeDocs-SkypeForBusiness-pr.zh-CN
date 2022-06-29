---
title: Microsoft Teams 会议室中的身份验证
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 了解如何为Microsoft Teams 会议室配置新式身份验证
ms.openlocfilehash: c50b197f554605b291e6af51b140fa6a2599e408
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240621"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 会议室中的身份验证

Microsoft Teams 会议室的帐户管理在应用程序级别进行处理。 应用程序连接到 Microsoft Teams、Skype for Business 和 Exchange 以获取资源帐户的资源，以启用通话和会议体验。 Teams 会议室使用专用资源帐户来允许始终启用功能、为使用调用计划) 配置的设备调用方案 (，以及自定义锁定机制。 这意味着Teams 会议室的身份验证以不同于最终用户设备的方式进行。  

建议所有使用 Microsoft 365 或 Office 365 Microsoft Teams 会议室的客户进行新式身份验证。 如果本地部署 Exchange 服务器或Skype for Business服务器，请使用 Azure Active Directory (Azure AD) 配置[混合新式身份验证](/office365/enterprise/hybrid-modern-auth-overview)，以便使用新式身份验证。

Microsoft Teams 会议室版本 4.4.25.0 及更高版本支持新式身份验证。

## <a name="modern-authentication"></a>新式身份验证

将新式身份验证与Microsoft Teams 会议室应用程序配合使用时，Active Directory 身份验证库 (ADAL) 用于连接到 Microsoft Teams、Exchange 和 Skype for Business。 新式身份验证机制使用 OAuth 2.0 中的 [资源所有者密码凭据](/azure/active-directory/develop/v2-oauth-ropc) 授权授权类型，这不需要任何用户干预。 这是新式身份验证对用户帐户的工作方式与Microsoft Teams 会议室使用的资源帐户之间的主要区别之一。 因此，不应将Microsoft Teams 会议室资源帐户配置为使用多重身份验证 (MFA) 、智能卡身份验证或基于客户端证书的身份验证 (，这些都可用于最终用户) 。

新式身份验证在Microsoft Teams 会议室和最终用户设备上的工作方式的另一个关键区别是，不能使用资源帐户在 Azure Active Directory 中应用设备级条件访问策略，并且在使用此授权类型时不会传递设备信息Endpoint Manager。 相反，可以在 Microsoft Endpoint Manager中注册设备并应用符合性策略。 有关详细信息，请参阅[条件访问和Intune符合Microsoft Teams 会议室](conditional-access-and-compliance-for-devices.md)。

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>在Microsoft Teams 会议室上启用新式身份验证

若要Microsoft Teams 会议室将新式身份验证与 Skype for Business 和 Exchange 配合使用，请在 Microsoft Teams 会议室 上启用新式身份验证的客户端设置。 可以在设备设置或 XML 配置文件中执行此操作。

> [!NOTE]
> 在为新式身份验证启用客户端设置之前，请确保正确设置环境以使用新式身份验证。

### <a name="using-device-settings"></a>使用设备设置

1. 在Microsoft Teams 会议室上，转到 **“更多** (**...**) 。
    
2. 选择 **“设置”**，然后输入设备管理员用户名和密码。
3. 转到 **“帐户”** 选项卡，打开 **“新式身份验证**”，然后选择 **“保存”并退出**。

### <a name="using-the-xml-config-file"></a>使用 XML 配置文件

在SkypeSettings.xml文件中，将新式身份验证 XML 元素设置为 **True**，如下所示。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要应用设置，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>为新式身份验证准备环境

在开始之前，请确保了解要与 Office 365 和 Azure AD 一起使用的标识模型。 可以在 [Office 365 标识模型和 Azure Active Directory](/Office365/Enterprise/about-office-365-identity) 以及 [Microsoft 365 或 Office 365 的混合标识和目录同步](/Office365/Enterprise/plan-for-directory-synchronization)处找到详细信息。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中启用新式身份验证

若要为Exchange Online启用新式身份验证，请参阅[Exchange Online中启用新式身份验证](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

我们建议在验证Microsoft Teams 会议室设备是否可以使用 Exchange Online 和 Teams 成功登录之前，不要删除Exchange Online的基本身份验证策略或禁用租户的基本身份验证。

有关在Exchange Online中禁用基本身份验证的详细信息，请参阅[Exchange Online中禁用基本身份验证](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合新式身份验证

若要确保本地 Exchange 服务器和/或Skype for Business服务器的身份验证成功，必须确保配置与Microsoft Teams 会议室一起使用的资源帐户以从 Azure AD 获取授权。

Teams 会议室身份验证流因身份验证配置而异。 对于使用托管域的客户，Teams 会议室将 [OAuth 2.0 资源所有者密码凭据](/azure/active-directory/develop/v2-oauth-ropc)与 Azure Active Directory 配合使用。 但是，对于使用联合域的客户，将使用 [OAuth 2.0 SAML 持有者断言流](/azure/active-directory/develop/v2-saml-bearer-assertion) 。

> [!NOTE]
> 标识提供者可能需要特定的配置或设置才能与 Azure Active Directory 或 Office 365 集成。 如果需要有关使用Teams 会议室配置身份验证的帮助，请与标识提供者联系。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>特定于Microsoft Teams 会议室的先决条件

混合新式身份验证概述介绍了在混合拓扑中启用新式身份验证的先决条件，以及[将它用于本地Skype for Business和 Exchange 服务器的先决条件](/office365/enterprise/hybrid-modern-auth-overview)。 本文中讨论的所有先决条件都适用。

但是，由于Microsoft Teams 会议室使用[资源所有者密码凭据](https://tools.ietf.org/html/rfc6749#section-1.3.3)授权和基础 REST API 进行新式身份验证，因此需要注意的是特定于Microsoft Teams 会议室的重要差异。

- 必须Exchange Server 2016 CU8 或更高版本，或Exchange Server 2019 CU1 或更高版本。
- 必须Skype for Business Server 2015 CU5 或更高版本，或 Skype for Business Server 2019 或更高版本。
- 无论你拥有什么拓扑，都不支持 MFA。
- Microsoft Teams 会议室不支持 SIP 和 UPN 不匹配。 必须创建具有相同 UPN 和 SIP 的Microsoft Teams 会议室帐户才能正常工作。
- 如果使用 Azure AD 支持的第三方身份验证提供程序，则必须支持通过 WS-Trust 的活动身份验证流。
- 对于与应用程序配置的资源帐户，请勿使用设备级条件访问策略。 这样做将导致登录失败。 而是在Microsoft Intune中注册设备并应用符合性策略。 有关详细信息，请参阅[条件访问和Intune符合Microsoft Teams 会议室](conditional-access-and-compliance-for-devices.md)。

### <a name="configure-exchange-server"></a>配置Exchange Server

若要在Exchange Server中启用混合新式身份验证，请参阅[如何将本地Exchange Server配置为使用混合新式身份验证](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>配置Skype for Business Server

若要使用Skype for Business Server启用混合新式身份验证，请参阅[如何将本地Skype for Business配置为使用混合新式身份验证](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>删除或禁用Skype for Business和 Exchange

如果安装程序不允许混合新式身份验证，或者需要删除或禁用 Exchange 或 Skype for Business 的混合新式身份验证，请参阅[从 Skype for Business 和 Exchange 删除或禁用混合新式身份验证](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。

### <a name="azure-ad-conditional-access"></a>Azure AD 条件访问

可以配置与基于 IP/位置的访问Microsoft Teams 会议室一起使用的资源帐户。 若要了解详细信息，请参阅 [条件访问：按位置阻止访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

有关设备符合性的详细信息，请参阅[支持的条件访问和Intune Microsoft Teams 会议室符合性策略](supported-ca-and-compliance-policies.md)。

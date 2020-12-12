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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 了解如何为 Microsoft Teams 会议室配置新式验证
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662577"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 会议室中的身份验证

Microsoft Teams 会议室设备的帐户管理在应用程序级别处理。 该应用程序连接到 Microsoft Teams、Skype for Business 和 Exchange，获取会议室帐户的资源，以启用呼叫和会议体验。 设备保持帐户不可知，以允许始终打开功能、为配置了呼叫计划) 的设备调用 (方案和在这些设备上实现的自定义锁定机制。 这意味着，这些设备的身份验证方式与最终用户设备的身份验证方式不同。  

对于将 Microsoft Teams 会议室设备与 Microsoft 365 或 Office 365 一起使用的所有客户，建议使用新式验证。 如果在本地部署 Exchange 服务器或 Skype for Business 服务器，请[](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)配置 Azure Active Directory (Azure AD) 混合新式身份验证以启用新式身份验证。

Microsoft Teams 会议室 4.4.25.0 及更高版本支持新式验证。

## <a name="modern-authentication"></a>新式身份验证

将新式身份验证与 Microsoft Teams 会议室应用程序一起使用时，Active Directory 身份验证库 (ADAL) 用于连接到 Microsoft Teams、Exchange 和 Skype for Business。 Microsoft Teams 会议室设备是一个共享设备，会进行夜间重新启动，以确保平稳运行并获取关键的操作系统、驱动程序、固件或应用程序更新。 新式身份验证机制使用 OAuth 2.0 中的资源所有者密码凭据授权类型，这不需要任何用户干预。 [](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) 这是新式验证如何用于用户帐户与 Microsoft Teams 会议室应用程序使用的资源帐户之间的主要区别之一。 因此，不应将 Microsoft Teams 会议室资源帐户配置为使用多重身份验证 (MFA) 、智能卡身份验证或基于客户端证书的身份验证 (所有这些功能都可用于最终用户) 。

新式验证在 Microsoft Teams 会议室设备和最终用户设备上的工作方式的另一个关键区别是，由于使用此授权类型时不会传递设备信息，因此不能使用资源帐户在 Azure Active Directory 和终结点管理器中应用设备级条件访问策略。 相反，可以使用在 Intune 中管理 Teams 会议室中提供的指南，在 Microsoft Endpoint Manager 中注册设备 [并应用符合性策略](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>在 Microsoft Teams 会议室设备上启用新式验证

若要让 Microsoft Teams 会议室在 Skype for Business 和 Exchange 中使用新式验证，请启用客户端设置，在 Microsoft Teams 会议室设备上进行新式验证。 可以在设备设置或 XML 设置中执行此操作配置文件。

> [!NOTE]
> 为新式身份验证启用客户端设置之前，请确保环境已正确设置为使用新式身份验证。

### <a name="using-device-settings"></a>使用设备设置

1. 在 Microsoft Team Rooms 设备上，转到"更多 **(...) 。**
    
2. 选择 **"** 设置"，然后输入设备管理员用户名和密码。
3. 转到" **帐户"** 选项卡， **打开"新式** 验证"，然后选择"保存 **"并退出**。

### <a name="using-the-xml-config-file"></a>使用 XML 配置文件

在 SkypeSettings.xml 文件中，将新式身份验证 XML 元素设置为 **True，** 如下所示。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要应用设置，请参阅"使用 XML 配置文件远程管理[Microsoft Teams 会议室控制台设置"。](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>为新式身份验证准备环境

开始之前，请确保了解要用于 Office 365 和 Azure AD 的标识模型。 有关详细信息，请参阅 Office [365](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) 标识模型和 Azure Active Directory，以及 [Microsoft 365 或 Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)的混合标识和目录同步。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中启用新式验证

若要为 Exchange Online 启用新式验证，请参阅"在 Exchange Online 中[启用新式验证"。](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 如果你使用 Skype for Business Online，你还应该确保为 Skype for Business Online 启用新式验证。 若要了解有关详细信息，请参阅 [Skype for Business Online：为租户启用新式验证](https://aka.ms/SkypeModernAuth)。

建议在验证 Microsoft Teams 会议室设备可以成功使用 Exchange Online、Teams 和 Skype for Business Online 登录之前，不要删除 Exchange Online 的基本身份验证策略或禁用租户的基本身份验证。

有关在 Exchange Online 中禁用基本身份验证的信息，请参阅"在 Exchange Online 中禁用[基本身份验证"。](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>混合新式身份验证

若要确保成功向本地 Exchange 服务器和/或 Skype for Business 服务器进行身份验证，必须确保将用于 Microsoft Teams 会议室的资源帐户配置为从 Azure AD 获取授权。 

Teams 会议室身份验证流因身份验证配置而异。 对于使用托管域的客户，Teams 会议室将 [OAuth 2.0 资源所有者密码凭据](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) 与 Azure Active Directory 一同使用。 但是，对于使用联合域的客户，使用 [OAuth 2.0 SAML Bearer 断言](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) 流。

> [!NOTE]
> 标识提供者可能需要特定的配置或设置，以与 Azure Active Directory 或 Office 365 集成。 如果需要有关使用 Teams 会议室配置身份验证的帮助，请与标识提供者联系。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>特定于 Microsoft Teams 会议室的先决条件

混合新式身份验证概述中介绍了在混合拓扑中启用新式身份验证的先决条件，以及在本地 [Skype for Business](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)和 Exchange 服务器上使用它的先决条件。 本文中讨论的所有先决条件均适用。

但是，由于 Microsoft Teams[](https://tools.ietf.org/html/rfc6749#section-1.3.3)会议室使用资源所有者密码凭据授权和基础 REST API 进行新式身份验证，因此请注意以下特定于 Microsoft Teams 会议室的重要差异。

- 必须拥有 2016 CU8 Exchange Server更高版本，或者 2019 CU1 Exchange Server更高版本。
- 你必须拥有 Skype for Business Server 2015 CU5 或更高版本，或 Skype for Business Server 2019 或更高版本。
- 无论使用何种拓扑，都不支持 MFA。
- Microsoft Teams 会议室不支持 SIP 和 UPN 不匹配。 必须使用相同的 UPN 和 SIP 创建 Microsoft Teams 会议室帐户，该帐户必须能够正常工作。
- 如果使用 Azure AD 支持的第三方身份验证提供程序，它必须支持通过 WS-Trust 的活动身份验证流。
- 不要对配置有应用程序的资源帐户使用设备级条件访问策略。 这样做将导致登录失败。 相反，使用在管理 Teams 会议室和 Intune 中发布的指南在 Microsoft Intune 中注册设备 [并应用符合性策略](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>配置Exchange Server

若要在 Exchange Server 中启用混合新式 [Exchange Server，请参阅](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)"如何在本地Exchange Server混合新式身份验证。

### <a name="configure-skype-for-business-server"></a>配置 Skype for Business Server

若要使用 Skype for Business Server 启用混合新式身份验证，请参阅"如何将本地 Skype for Business 配置为[使用混合新式身份验证"。](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>删除或禁用 Skype for Business 和 Exchange

如果你的设置不允许混合新式验证，或者你需要为 Exchange 或 Skype for Business 删除或禁用混合新式验证，请参阅从 [Skype for Business](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)和 Exchange 中删除或禁用混合新式验证。

### <a name="azure-ad-conditional-access"></a>Azure AD 条件访问

可以配置用于 Microsoft Teams 会议室的资源帐户，用于基于 IP/位置的访问。 若要了解有关详细信息，请参阅["条件访问：按位置阻止访问"。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

不支持任何其他条件访问策略。 有关设备符合性详细信息，请参阅["使用 Intune 管理 Teams 会议室"。](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)  

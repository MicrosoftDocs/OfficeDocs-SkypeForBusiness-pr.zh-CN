---
title: Microsoft 团队聊天室中的身份验证
ms.author: v-lanac
author: lanachin
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
description: 了解如何配置 Microsoft 团队聊天室的新式验证
ms.openlocfilehash: f44fe0e66e5dd219606b2ceaa3860e01164ccfa4
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666254"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft 团队聊天室中的身份验证

Microsoft 团队聊天室设备的帐户管理在应用程序级别处理。 应用程序连接到 Microsoft 团队、Skype for Business 和 Exchange 以获取房间帐户的资源以启用呼叫和会议体验。 该设备保持不限帐户，以允许始终打开的功能、呼叫方案（适用于使用呼叫计划配置的设备）和在这些设备上实现的自定义锁定机制。 这意味着针对这些设备的身份验证与最终用户设备的使用方式不同。  

对于将 Microsoft 团队聊天室设备与 Microsoft 365 或 Office 365 配合使用的所有客户，建议使用新式验证。 如果你有 Exchange server 或 Skype for business server 的内部部署，请使用 Azure Active Directory （Azure AD）配置[混合新式身份验证](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)，以使用新式身份验证启用。

Microsoft 团队聊天室版本4.4.25.0 及更高版本支持新式身份验证。

## <a name="modern-authentication"></a>新式验证

将新式验证用于 Microsoft 团队聊天室应用程序时，将使用 Active Directory 身份验证库（ADAL）连接到 Microsoft 团队、Exchange 和 Skype for business。 Microsoft 团队聊天室设备是一种共享设备，执行夜间重启，以确保正常运行，并获取关键操作系统、驱动程序、固件或应用程序更新。 新式身份验证机制使用 OAuth 2.0 中的[资源所有者密码凭据](https://tools.ietf.org/html/rfc6749#section-1.3.3)授权授权类型，而不需要任何用户干预。 这是现代身份验证对用户帐户和 Microsoft 团队聊天室应用程序使用的资源帐户之间的主要差异之一。 因此，Microsoft 团队室资源帐户不应配置为使用多重身份验证（MFA）、智能卡身份验证或基于客户证书的身份验证（它们均适用于最终用户）。

新式身份验证在 Microsoft 团队聊天室设备和最终用户设备上的工作方式之间的其他主要区别是，你无法使用资源帐户应用设备级别的条件访问策略，例如 "需要设备标记为合规" 或 "需要混合的 Azure AD 已加入设备" 等。 这是因为设备级概念在应用程序级别使用时不适用于新式身份验证。 相反，你可以在 Microsoft Intune 中注册设备，并使用使用[Intune 管理团队](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)会议室中提供的指南来应用合规性策略。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>在 Microsoft 团队聊天室设备上启用新式验证

对于 Microsoft 团队聊天室，若要对 Skype for Business 和 Exchange 使用新式验证，请在 Microsoft 团队聊天室设备上启用新式验证的客户端设置。 你可以在设备设置或 XML 配置文件中执行此操作。

> [!NOTE]
> 在启用新式验证的客户端设置之前，请确保你的环境已正确设置为使用新式验证。

### <a name="using-device-settings"></a>使用设备设置

1. 在 Microsoft 团队聊天室设备上，转到 "**更多**（**...**）"。
    
2. 选择 "**设置**"，然后输入设备管理员的用户名和密码。
3. 转到 "**帐户**" 选项卡，打开 "**新式身份验证**"，然后选择 "**保存并退出**"。

### <a name="using-the-xml-config-file"></a>使用 XML 配置文件

在 SkypeSettings 文件中，将新式身份验证 XML 元素设置为**True**，如下所示。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要应用设置，请参阅[使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>为新式验证准备环境

开始之前，请确保了解用于 Office 365 和 Azure AD 的身份模型。 你可以在[Office 365 的 "身份模型" 和 "Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) " 以及[Microsoft 365 或 Office 365 的混合标识和目录同步](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)中找到详细信息。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中启用新式验证

若要打开 Exchange Online 的新式身份验证，请参阅[在 Exchange online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。 如果您使用 Skype for Business Online，还应确保已为 Skype for business Online 启用新式验证。 若要了解详细信息，请参阅[Skype for Business Online：针对新式验证启用租户](https://aka.ms/SkypeModernAuth)。

我们建议您不要删除 Exchange Online 的基本身份验证策略，或禁用租户的基本身份验证策略，然后再验证 Microsoft 团队会议室设备在新式身份验证设置处于打开状态且没有设备仍配置为使用基本身份验证时，可成功登录到 Exchange Online 和团队或 Skype for business Online。

有关在 Exchange Online 中禁用基本身份验证的详细信息，请参阅[在 Exchange online 中禁用基本身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合新式身份验证

若要确保对本地 Exchange server 和/或 Skype for business 服务器的身份验证成功，必须确保将用于 Microsoft 团队聊天室的资源帐户配置为从 Azure AD 获取授权。 若要了解有关适用于你的组织的混合标识和方法的详细信息，请阅读以下主题： 

- [什么是密码哈希同步？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [什么是直通身份验证？](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [什么是联盟？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>特定于 Microsoft 团队聊天室的先决条件

在混合拓扑中启用新式身份验证的先决条件属于[混合新式身份验证概述以及将其与本地 Skype For business 和 Exchange 服务器配合使用的先决条件](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)。 本文中讨论的所有先决条件均适用。

但是，由于 Microsoft 团队聊天室使用[资源所有者密码凭据](https://tools.ietf.org/html/rfc6749#section-1.3.3)授权和基础 REST api 进行新式身份验证，因此以下是特定于 Microsoft 团队聊天室的重要差异。

- 您必须拥有 Exchange Server 2016 CU8 或更高版本，或者 Exchange Server 2019 CU1 或更高版本。
- 您必须拥有 Skype for business Server 2015 CU5 或更高版本，或者使用 Skype for business Server 2019 或更高版本。
- 不支持 MFA，无论你有何种拓扑。
- 如果你使用的第三方身份验证提供程序由 Azure AD 支持，则它必须支持 OAuth 并使用资源所有者密码凭据授权。
- 不要对使用应用程序配置的资源帐户使用设备级条件访问策略。 这样做将导致登录失败。 而是在 Microsoft Intune 中注册一个设备，并使用使用[Intune 管理团队](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)会议室中发布的指南来应用合规性策略。

### <a name="configure-exchange-server"></a>配置 Exchange Server

若要在 Exchange Server 中启用混合新式身份验证，请参阅[如何将本地 Exchange Server 配置为使用混合新式身份验证](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>配置 Skype for Business 服务器

若要启用与 Skype for Business 服务器的混合新式身份验证，请参阅[如何将本地 Skype for business 配置为使用混合新式身份验证](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>删除或禁用 Skype for Business 和 Exchange

如果你的设置不允许混合新式身份验证，或者你需要删除或禁用 Exchange 或 Skype for business 的混合新式身份验证，请参阅[删除或禁用 skype for business 和 Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)的混合新式身份验证。

### <a name="azure-ad-conditional-access"></a>Azure AD 条件访问

你可以为基于 IP/位置的访问配置 Microsoft 团队聊天室使用的资源帐户。 若要了解详细信息，请参阅[条件访问：通过位置阻止访问](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支持任何其他条件访问策略。 有关设备合规性的详细信息，请参阅[用 Intune 管理团队会议室](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。  

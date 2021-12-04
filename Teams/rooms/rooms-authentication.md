---
title: 在 Microsoft Teams 会议室
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
description: 了解如何为用户配置新式Microsoft Teams 会议室
ms.openlocfilehash: 9f173759ed2b615bdfcae6c54c2c5e431c197d04
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306297"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>在 Microsoft Teams 会议室

在应用程序Microsoft Teams 会议室处理设备的帐户管理。 应用程序连接到 Microsoft Teams、Skype for Business 和 Exchange，获取会议室帐户的资源，以启用呼叫和会议体验。 设备使用专用资源帐户来允许始终打开功能，为配置有呼叫计划) 的设备调用方案 (，以及在这些设备上实现的自定义锁定机制。 这意味着，这些设备的身份验证方式与最终用户设备的身份验证方式不同。  

建议所有使用新式验证Microsoft Teams 会议室或Microsoft 365 Office 365。 如果在本地部署 Exchange 服务器或 Skype for Business，请配置[混合](/office365/enterprise/hybrid-modern-auth-overview)新式Azure Active Directory (Azure AD) ，以便使用新式身份验证。

4.4.25.0 Microsoft Teams 会议室版本支持新式验证。

## <a name="modern-authentication"></a>新式身份验证

在 Microsoft Teams 会议室 应用程序中使用新式身份验证时，Active Directory 身份验证库 (ADAL) 用于连接到 Microsoft Teams、Exchange 和 Skype for Business。 Microsoft Teams 会议室是一个共享设备，并在夜间执行重新启动，以确保顺利运行并获取关键的操作系统、驱动程序、固件和应用程序更新。 新式身份验证机制使用 OAuth 2.0 中的资源所有者密码凭据授权类型，这不需要任何用户干预。 [](/azure/active-directory/develop/v2-oauth-ropc) 这是新式验证对用户帐户的工作方式与用户所使用的资源帐户之间的主要Microsoft Teams 会议室。 因此，Microsoft Teams 会议室资源帐户不应配置为使用多重身份验证 (MFA) 、智能卡身份验证或基于客户端证书的身份验证 (这一切都适用于最终用户) 。

新式身份验证在 Microsoft Teams 会议室 和最终用户设备上的工作方式的另一个关键区别是，你不能使用资源帐户在 Azure Active Directory 和 Endpoint Manager 中应用设备级条件访问策略，因为使用此授权类型时不会传递设备信息。 相反，可以使用使用 Intune Microsoft Endpoint Manager管理会议室中提供的指南，在 Teams注册设备并应用[符合性策略](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>在 Microsoft Teams 会议室 设备上启用新式验证

若要Microsoft Teams 会议室将新式身份验证与 Skype for Business Exchange，请为 Microsoft Teams 会议室 上的新式身份验证启用客户端Microsoft Teams 会议室。 可以在设备设置或 XML 设置中执行此操作配置文件。

> [!NOTE]
> 为新式身份验证启用客户端设置之前，请确保环境已正确设置为使用新式身份验证。

### <a name="using-device-settings"></a>使用设备设置

1. 在Microsoft Teams 会议室上，转到"**更多****(...) "。**
    
2. 选择 **设置"，** 然后输入设备管理员用户名和密码。
3. 转到"帐户 **"选项卡**，打开"新式 **验证"，** 然后选择"**保存并退出"。**

### <a name="using-the-xml-config-file"></a>使用 XML 配置文件

在 SkypeSettings.xml 文件中，将新式身份验证 XML 元素设置为 **True，** 如下所示。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要应用设置，请参阅使用 XML 配置文件[Microsoft Teams 会议室远程管理主机设置](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>为新式身份验证准备环境

在开始之前，请确保了解要与 Office 365 和 Azure AD 一Azure AD。 有关详细信息，请参阅 Office 365[标识](/Office365/Enterprise/about-office-365-identity)模型和Azure Active Directory混合标识和目录同步（适用于 Microsoft 365[或 Office 365）。](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365

若要为用户启用新式Exchange Online，请参阅在 Exchange Online[中启用新式](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

建议在验证 Microsoft Teams 会议室 设备可以使用 Exchange Online 和 Teams 成功登录之前，不要删除 Exchange Online 的基本身份验证策略或禁用租户的基本身份验证。

有关在客户端中禁用基本身份验证Exchange Online，请参阅在 Exchange Online 中[禁用基本身份验证](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合新式验证

若要确保向本地 Exchange 服务器和/或 Skype for Business 服务器成功进行身份验证，必须确保将用于 Microsoft Teams 会议室 的资源帐户配置为从 Azure AD 获取授权。

Teams 会议室身份验证流因身份验证配置而异。 对于使用托管域的客户，Teams 会议室[使用 OAuth 2.0 资源所有者密码](/azure/active-directory/develop/v2-oauth-ropc)凭据Azure Active Directory。 但是，对于使用联合域的客户，使用[OAuth 2.0 SAML Bearer Flow](/azure/active-directory/develop/v2-saml-bearer-assertion)断言。

> [!NOTE]
> 标识提供者可能需要特定的配置或设置，以与 Azure Active Directory 或 Office 365。 如果需要有关使用身份验证配置身份验证的帮助，请与标识Teams 会议室。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>特定于应用程序Microsoft Teams 会议室

混合新式身份验证概述中介绍了在混合拓扑中启用新式身份验证的先决条件，以及用于本地 Skype for Business 和 Exchange[服务器的先决条件](/office365/enterprise/hybrid-modern-auth-overview)。 本文中讨论的所有先决条件均适用。

但是，Microsoft Teams 会议室[使用资源](https://tools.ietf.org/html/rfc6749#section-1.3.3)所有者密码凭据授权和基础 REST API 进行新式身份验证，因此请注意以下重要差异，这些差异特定于 Microsoft Teams 会议室。

- 必须拥有 2016 CU8 Exchange Server或更高版本，Exchange Server 2019 CU1 或更高版本。
- 必须具有 2015 CU5 Skype for Business Server更高版本，或者 2019 Skype for Business Server更高版本。
- 无论使用何种拓扑，都不支持 MFA。
- Microsoft Teams 会议室 SIP 和 UPN 不匹配。 必须使用相同的 UPN Microsoft Teams 会议室 SIP 创建一个帐户，使该帐户正常工作。
- 如果使用由用户支持的第三方身份验证Azure AD，它必须支持通过 WS-Trust 的活动身份验证流。
- 不要对配置了应用程序的资源帐户使用设备级条件访问策略。 这样做将导致登录失败。 相反，使用 Intune Microsoft Intune管理会议室中发布的指南，在 Teams注册设备[并应用符合性策略](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>配置Exchange Server

若要在 Exchange Server中启用混合新式Exchange Server，请参阅如何配置本地身份验证以[使用混合新式身份验证](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>配置Skype for Business Server

若要使用 Skype for Business Server启用混合新式身份验证，请参阅如何Skype for Business[本地用户以使用混合新式身份验证](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>删除或禁用Skype for Business Exchange

如果设置不允许混合新式验证，或者需要删除或禁用 Exchange 或 Skype for Business 的混合新式验证，请参阅从 Skype for Business 和 Exchange 删除或禁用混合新式[验证](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。

### <a name="azure-ad-conditional-access"></a>Azure AD条件访问

可以配置用于基于 IP/Microsoft Teams 会议室访问的资源帐户。 有关详细信息，请参阅条件 [访问：按位置阻止访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支持任何其他条件访问策略。 有关设备符合性详细信息，请参阅使用[Intune Teams会议室。](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)
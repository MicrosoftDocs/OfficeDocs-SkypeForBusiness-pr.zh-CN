---
title: 关闭旧身份验证方法内部和外部到网络
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 为管理员提供的身份验证方法的更多控制此文章轮廓 cmdlet 使用的企业内部和外部、。 管理员可以打开身份验证方法或关闭到他们的网络的内部或外部。
ms.openlocfilehash: 2922d270f7a033a1523083ed15adefc5fb5f331d
ms.sourcegitcommit: c9b68cbc8199d21a3fa4275db7a663695784afb3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23485804"
---
# <a name="turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>关闭旧身份验证方法内部和外部到网络。

> [!NOTE]
> 如果您要阅读这篇文章，您应知道有关受支持的现代身份验证拓扑，ADAL，且现代的身份验证配置有关但，以防不，此处开始所需的文章： 
 + [https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
 + [https://docs.microsoft.com/en-us/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/en-us/skypeforbusiness/manage/authentication/use-adal)
  
现代身份验证不只是启用更安全的身份验证，如双重身份验证或基于证书的身份验证方法，它可以执行用户授权而无需用户名或密码太。 它是非常方便。

本文将帮助您为业务服务器，通过关闭旧方法外部、 内部，用于进行身份验证，或同时，您的网络到利用 Skype 上拒绝的服务 (DOS) 攻击的即插即用孔。 例如，是一个很好的方法，可帮助停止 DOS 攻击关闭 Windows 集成的身份验证 （其中包括 NTLM 和 Kerberos）。 外部关闭 NTLM 和依赖于基于证书的身份验证有助于不会泄露保护密码。 这是因为 NTLM 使用密码凭据进行身份验证的用户，但不基于证书的身份验证-由现代身份验证-启用。 表示一个理想选项可减少 DOS 攻击是块外部，NTLM 和使用仅基于证书的身份验证，而是。

没关系，我们开始吧。

## <a name="what-would-you-be-changing"></a>什么将您更改？ 

这些 cmdlet 处理 SIP 和 Web 服务访问点。 尽管这些两个通道使用不同的访问方法，匿名访问，请从 NTLM 和 Kerberos 运行色阶 for Business 使用 Skype 的所有标准方法具有加以考虑。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何获取和设置 CsAuthConfig cmdlet

这些 cmdlet 将仅安装发布 2018 年 7 月版累积更新 (6.0.9319.534) 的 Microsoft Skype 业务服务器 2015年，然后您有多种可为您的业务服务器 Skype 推出的拓扑。

## <a name="topologies"></a>拓扑

非常重要记住这些权限是支持的拓扑此方案中涉及 ！ 如果您需要有关阻止方法的帮助，请转到支持，例如，您需要具有以下类型的之间的配置。 

> [!IMPORTANT]
> 在表和下面的说明中，*现代身份验证*缩写为__MA__和*Windows 集成身份验证*缩写为__Win__。 注意，Windows 集成身份验证由组成两种方法： NTLM 和 Kerberos 身份验证。 您需要知道此选项可正确读取表 ！


|       |外部  |内部  |参数  |
|---------|:---------|:---------|---------|
|__类型 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__类型 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__类型 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__类型 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__类型 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__键入 1 的说明：__ 这是默认方案 MA 时处于__打开__状态的 Skype 业务服务器。 换句话说，这是*起始点*MA 配置时。

__类型 2 说明：__ 这种拓扑阻止 NTLM*外部*，但允许 NTLM 或 Kerberos （不支持 ADAL 的客户端）*内部*工作时。 如果您的客户端支持 ADAL 它们将内部使用 MA。

__类型 3 说明：__ 这种拓扑的所有用户需要 MA。 所有 ADAL 支持客户端都能够在此拓扑中，并将未利用密码，如果，例如，您可以关闭使用与基于证书的验证的密码

__类型 4 说明：__ 这种拓扑结构禁止 NTLM*外部*和 MA 内部。 允许*所有客户端*使用传统的身份验证方法*内部*（甚至 ADAL 支持客户端）。

__类型 5 说明：__ 现代 ADAL 客户端将使用 MA 的*外部*，并且不支持 ADAL 任何客户端将使用旧的身份验证方法。 但是，*内部**所有客户端*将使用旧的身份验证 （包括所有 ADAL 支持的客户端）。

它是很方便地丢失跟踪的目标的保护密码中可用的选项。 请记住理想的情况下是使用外部 MA （例如，配置基于证书的身份验证），以避免 DOS 攻击。 如果您利用它内部的现代客户端，您将还未来您关于 Skype 业务服务器受到 DOS 攻击的网络。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>为什么在全局级别使用集 CsAuthConfig

`Set-CsAuthConfig`上注册器和 Web 服务角色的 cmdlet 效果配置。

此 cmdlet 是为了在全局级别的企业服务器您 Skype 运行。 它*可以*运行在池级别但即*不建议这样做*，因为它将添加到您安装的复杂性。 在池级别中，运行以下命令，如果池没有所有包含的角色 （例如，它没有 Web 服务），设置才会设置为注册器角色。 在这种情况下，Web 服务执行的全局级别，可以是令人费解行为 （尤其是当这是无意中） 中的设置。

如果客户端从另一个池使用的注册器设置从一个池和 Web 服务设置和身份验证设置处于不一致状态，可能无法登录 yous 客户端。

此外，如果存在池中只有一个角色： 
* 设置将仅存在角色设置对应的设置。 由于某些设置*未*设置，会不授予任何特殊的警告。 
* 获取将返回对应于存在，该角色的设置，并且不存在的角色的全局设置。
* 如果既角色是存在一个池，这两个组-和 Get-将返回一条错误消息。
* 如果这两种角色存在池，但不在池级别定义策略，获取将返回一条错误消息。

它可能最明智的方式执行 Get-这些值，并屏幕截图或其起始状态记录进行任何更改之前。 您可能还考虑在 OneNote 中保留更改日志。

> [!IMPORTANT]
> 如果您使用的 Lync Web Access (LWA)，必须使用基于表单的访问 (FBA) 的外部访问，重新配置 LWA，以便客户端可以访问它来支持这些方案的匿名访问。 同样，如果您使用的拨入 Pin，将为外部用户仅阻止 FBA。 如果所需更改其 pin，他们将需要登录到其公司为此，请内部。

## <a name="links"></a>链接 ##
- 有关详细的 PowerShell 信息：
    - Get CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md)
    - 设置 CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md)

- 有关如何使用命令或上需要安装它们累积更新的详细方向：
    - Cmdlet 简介[https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - 更新 Skype 业务服务器 2015 （常规）[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    - 为业务服务器 2015，年 7 月 2018 Skype 核心组件累积更新 (6.0.9319.534)[https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)


 
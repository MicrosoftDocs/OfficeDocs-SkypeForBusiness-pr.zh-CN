---
title: 规划在网络内部和外部关闭旧式身份验证方法
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 本文概述了 cmdlet，这些 cmdlet 使管理员可以更加控制在企业内外使用的身份验证方法。 管理员可以在内部或外部打开或关闭身份验证方法。
ms.openlocfilehash: c9d4cce512ebb296cb442c6a78482f19bf7062aaceb8fe8704cbca3c277e4e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306873"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>计划在网络内部和外部关闭旧式身份验证方法。

> [!NOTE]
> 如果你要阅读本文，你应该已经了解支持的新式验证拓扑、ADAL 以及新式验证配置，但是，如果你不了解，以下是需要开始的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
新式验证并不仅仅是启用更安全的身份验证方法（Two-Factor身份验证或基于证书的身份验证方法，它还无需用户名和密码即可执行用户授权。 它相当方便。

本文将帮助您通过关闭用于身份验证（外部、内部或两者）到网络的旧方法，在 Skype for Business 服务器上插入被利用用于拒绝服务 (DOS) 攻击的漏洞。 例如，一种有助于停止 DOS 攻击的不错方法是关闭 Windows 集成身份验证 (包括 NTLM 和 Kerberos) 。 在外部关闭 NTLM 并依赖基于证书的身份验证有助于保护密码免遭泄露。 这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证（由新式身份验证启用）不会。 这意味着减少 DOS 攻击的一个理想选项是，在外部阻止 NTLM，并仅在该位置使用基于证书的身份验证。

好了，让我们开始吧。

## <a name="what-would-you-be-changing"></a>要更改什么？ 

这些 cmdlet 适用于 SIP 和 Web 服务访问点。 尽管这两个通道使用不同的访问方法（从 NTLM 和 Kerberos 到匿名访问）运行游戏，但已考虑 Skype for Business 使用的所有标准方法。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何获取 Get- 和 Set-CsAuthConfig cmdlet

这些 cmdlet 仅在 Microsoft Skype for Business Server 2015 的 2018 年 7 月累积更新 (6.0.9319.534) 后安装，然后您便具有可针对 Skype for Business 服务器推出的各种拓扑。

## <a name="topologies"></a>拓扑

必须记住，这些是此方案中涉及的受支持拓扑！ 例如，如果需要转到"支持"，获得阻止方法的帮助，则需要在下面的类型中配置。 

> [!IMPORTANT]
> 在下表和说明中，新式验证缩写 *为 MA，Windows集成* 身份验证缩写为 __Win。__  提醒一下，Windows身份验证由两种方法（NTLM 和 Kerberos 身份验证）决定。 你需要知道这一点，以正确读取表！


|       |外部  |内部  |参数  |
|---------|:---------|:---------|---------|
|__类型 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__类型 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__类型 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__类型 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__类型 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__类型 1 说明：__ 这是为 MA 打开 MA 时 __的默认Skype for Business Server。__ 换句话说，这是 *配置* MA 时的起点。

__类型 2 说明：__ 此拓扑在外部阻止 *NTLM，* 但允许 NTLM 或 Kerberos (不支持 ADAL) 在内部 *工作*。 如果你的客户端支持 ADAL，他们将在内部使用 MA。

__类型 3 说明：__ 此拓扑要求所有用户使用 MA。 所有支持 ADAL 的客户端都将在此拓扑中工作，例如，如果关闭对基于证书的身份验证的密码的使用，将不会利用密码。

__类型 4 说明：__ 此拓扑在外部阻止 *NTLM，* 在内部阻止 MA。 它允许 *所有客户端在* 内部使用旧身份验证 (支持 ADAL 的客户端) 。

__类型 5 描述：__*从* 外部来说，新式 ADAL 客户端将使用 MA，任何不支持 ADAL 的客户端都将使用旧版身份验证方法。 但是 *，在内部**，所有客户端* 将使用旧版 (包括所有支持 ADAL 的客户端) 。

很容易会失去对可用选项中保护密码的目标的跟踪。 请记住，理想情况是在外部使用 MA (例如，通过配置基于证书的身份验证) 以避免 DOS 攻击。 如果你在内部为新式客户端利用它，则还将针对 DOS 攻击Skype for Business Server网络。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>为什么要在Set-CsAuthConfig级别使用全局

`Set-CsAuthConfig`此 cmdlet 将影响注册器角色和 Web 服务角色上的配置。

此 cmdlet 旨在运行在客户端服务器的全局Skype for Business级别。 *它可以* 在池级别运行，但不建议这样做，因为这会增加安装的复杂性。 在池级别运行这些命令，如果您的池不包含 (例如，它没有 Web 服务) ，则只会为注册器角色设置。 在这种情况下，Web 服务将继续使用全局级别的设置，这可能会令人混淆的行为 (尤其是在无意中完成此操作) 。

如果客户端使用一个池中的注册器设置和另一个池中的 Web 服务设置，并且身份验证设置的状态不一致，则客户端可能无法登录。

此外，如果池只有一个角色： 
* Set- 将仅设置与存在的角色对应的设置。 由于未设置某些设置，因此不会提供 *特殊* 警告。 
* Get- 将返回对应于已存在的角色的设置，以及不存在的角色的全局设置。
* 如果池不存在任何角色，Set- 和 Get- 都将返回错误消息。
* 如果池存在这两个角色，但没有在池级别定义策略，则 Get- 将返回错误消息。

对这些值执行 Get-，以及进行任何更改之前屏幕截图或记录其开始状态可能最明智。 还可以考虑将更改日志保留到OneNote。

> [!NOTE]
> 
> 注意：配置 CsAuthConfig 后，必须在Enable-CsComputer运行此配置，设置才能生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access (LWA) 并且必须使用基于表单的 Access (FBA) 进行外部访问，请重新配置 LWA，以便客户端可以使用匿名访问访问它以支持这些方案。 同样，如果使用拨入 Pin，则 FBA 将仅针对外部用户进行阻止。 如果他们需要更改其 PIN，则需要在内部登录到其公司。

> [!NOTE]
> 
> 如果使用 BlockWindowsAuthExternally 参数在外部阻止 NTLM，请注意这还会在内部阻止 SIP 通道的 NTLM。 但是，Skype for Business 2010 及更高版本的 Lync 客户端仍可登录，因为它们将在内部使用 NTLM over HTTP 登录，然后获取证书以通过 SIP 登录。 但是，2010 之前版本低于 2010 的客户端在这种情况下将无法在内部登录，您可能需要考虑升级这些应用程序，以便您的用户可以恢复安全功能。

> [!IMPORTANT] 
> 某些 Skype for Business Web 应用程序不支持 MA。 因此，通过使用 BlockWindowsAuthExternallyAndInternally 方案，你将无法访问这些应用程序。 没有 MA 支持的应用程序包括 Web 计划程序、拨入页、Skype for Business控制面板 (、) 响应组设置页面。 

## <a name="links"></a>链接 
- 有关 PowerShell 的更多信息：
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 有关如何使用命令或安装命令所需的 CU 的更多方向：
    - [Cmdlet 简介](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015 年常规 (](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)更新) 
    - [2018 年 7 Skype for Business Server 2015 年 7 月，核心组件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534) 



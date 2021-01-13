---
title: 计划从内部和外部到网络关闭旧版身份验证方法
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
description: 本文概述了使管理员可以更加控制在企业内外使用的身份验证方法的 cmdlet。 管理员可以在内部或外部将其身份验证方法打开或关闭到其网络。
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810022"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>计划在网络和外部关闭旧版身份验证方法。

> [!NOTE]
> 如果你要阅读本文，你应该已经了解支持的新式验证拓扑、ADAL 以及新式验证配置，但是，如果你不了解，下面是你需要开始的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
新式验证并不仅仅是启用更安全的身份验证方法（如 Two-Factor 身份验证或基于证书的身份验证方法），它还无需用户名和密码即可执行用户授权。 它很方便。

本文通过关闭用于外部、内部或两者身份验证的较旧方法连接到网络，帮助你在 Skype for Business 服务器上插入被利用用于拒绝服务 (DOS) 攻击的漏洞。 例如，帮助停止 DOS 攻击的一个好方法是关闭 Windows 集成身份验证 (包括 NTLM 和 Kerberos) 。 在外部关闭 NTLM 并依赖基于证书的身份验证有助于保护密码免受泄露。 这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证（由新式身份验证启用）不会。 这意味着减少 DOS 攻击的一个理想选项是，在外部阻止 NTLM，并改为仅使用基于证书的身份验证。

好，让我们开始吧。

## <a name="what-would-you-be-changing"></a>要更改什么？ 

这些 cmdlet 适用于 SIP 和 Web 服务访问点。 尽管这两个通道使用不同的访问方法（从 NTLM 和 Kerberos 到匿名访问）运行域，但 Skype for Business 使用的所有标准方法都已被考虑在内。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何获取 Get-and Set-CsAuthConfig cmdlet

这些 cmdlet 仅在 2018 年 7 月累积更新 (6.0.9319.534) for Microsoft Skype for Business Server 2015 之后安装，然后你便拥有各种可用于 Skype for Business 服务器的拓扑。

## <a name="topologies"></a>拓扑

请记住，此方案中涉及的是受支持的拓扑，这一点很重要！ 例如，如果需要转到"支持"以寻求帮助来阻止方法，则需要在下列类型中配置。 

> [!IMPORTANT]
> 在下表和说明中，新式验证缩写为 __MA，Windows__ 集成身份验证缩写为 __Win。__ 提醒一下，Windows 集成身份验证由两种方法决定：NTLM 和 Kerberos 身份验证。 你需要知道这一点，以正确读取表！


|       |外部  |内部  |参数  |
|---------|:---------|:---------|---------|
|__类型 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__类型 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__类型 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__类型 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__类型 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__类型 1 描述：__ 这是为 Skype for Business Server 打开 MA __时的默认__ 方案。 换句话说，这是配置 MA时的起点。

__类型 2 说明：__ 此拓扑在外部阻止 *NTLM，* 但允许不支持 ADAL (NTLM 或 Kerberos) 在内部 *工作*。 如果你的客户端支持 ADAL，他们将在内部使用 MA。

__类型 3 说明：__ 此拓扑要求所有用户使用 MA。 所有支持 ADAL 的客户端都将在此拓扑中工作，例如，如果关闭对基于证书的身份验证使用密码，将不会利用密码。

__类型 4 说明：__ 此拓扑在外部和 MA *内部* 阻止 NTLM。 它允许 *所有客户端在* 内部使用旧 *身份验证方法 (* 支持 ADAL 的客户端) 。

__类型 5 描述：__ 在外部，新式 ADAL 客户端将使用 MA，任何不支持 ADAL 的客户端都将使用旧版身份验证方法。 但是 *，在内部，**所有* 客户端都将使用旧版 (，包括所有支持 ADAL 的客户端) 。

很容易在可用选项中跟踪保护密码的目标。 请记住，理想情况是在外部使用 MA (例如，通过配置基于证书的身份验证) 以避免 DOS 攻击。 如果你在内部为新式客户端利用它，你还将针对 Skype for Business Server DOS 攻击验证你的网络。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>为什么要在Set-CsAuthConfig级别使用

`Set-CsAuthConfig`此 cmdlet 对注册器角色和 Web 服务角色都影响配置。

此 cmdlet 旨在运行在 Skype for Business 服务器的全局级别。 *它可以* 在池级别运行，但不建议这样做，因为这会增加安装的复杂性。 在池级别运行这些命令，如果您的池不包含 (（例如，它不包含 Web 服务) ）的所有角色，将仅为注册器角色设置设置。 在这种情况下，Web 服务将继续使用全局级别的设置，这可能会令人混淆， (在无意中完成此操作时) 。

如果客户端使用一个池中的注册器设置和另一个池中的 Web 服务设置，并且身份验证设置的状态不一致，则客户端可能无法登录。

此外，如果池只有一个角色： 
* Set- 将仅设置与存在的角色对应的设置。 不会提供任何特殊警告，因为未设置 *某些* 设置。 
* Get- 将返回对应于存在的角色的设置，以及不存在的角色的全局设置。
* 如果池不存在任何角色，Set-和 Get 都将返回错误消息。
* 如果池存在这两个角色，但没有在池级别定义策略，则 Get-将返回一条错误消息。

对这些值执行 Get-，以及进行任何更改之前屏幕截图或记录其开始状态可能最明智。 还可以考虑在 OneNote 中保留更改日志。

> [!NOTE]
> 
> 注意：配置 CsAuthConfig 后，必须在Enable-CsComputer运行此配置，设置才能生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access (LWA) 并且必须使用基于表单的 Access (FBA) 进行外部访问，请重新配置 LWA，以便客户端可以使用匿名访问访问它以支持这些方案。 同样，如果使用拨入 Pin，则 FBA 将仅针对外部用户被阻止。 如果他们需要更改其 PIN，他们将需要在内部登录到其公司以这样做。

> [!NOTE]
> 
> 如果使用 BlockWindowsAuthExternally 参数在外部阻止 NTLM，请注意这还会在内部阻止 SIP 通道的 NTLM。 但是，更新于 2010 的 Skype for Business 和 Lync 客户端仍可登录，因为它们将在内部使用 NTLM over HTTP 登录，然后获取证书以通过 SIP 登录。 但是，在此情形下，2010 之前版本低于 2010 的客户端将无法在内部登录，您可能需要考虑升级这些应用程序，以便用户可以恢复安全功能。

> [!IMPORTANT] 
> 某些 Skype for Business Web 应用程序不支持 MA。 因此，通过使用 BlockWindowsAuthExternallyAndInternally 方案，你将无法访问这些应用程序。 没有 MA 支持的应用程序包括 Web 计划程序、拨入页、Skype for Business 控制面板 (、) 设置页。 

## <a name="links"></a>链接 
- 有关更多 PowerShell 信息：
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 有关如何使用命令或安装命令所需的 CU 的更多方向：
    - [Cmdlet 简介](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015 (](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 常规) 
    - 2018 年 7 月 [Skype for Business Server 2015 核心](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) 组件 CU (6.0.9319.534) 


 

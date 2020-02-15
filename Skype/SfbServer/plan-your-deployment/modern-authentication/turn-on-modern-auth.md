---
title: 规划在内部和外部在网络中关闭旧版身份验证方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 本文概述了可让管理员更好地控制企业内部和外部使用的身份验证方法的 cmdlet。 管理员可以在内部或外部在其网络中打开或关闭身份验证方法。
ms.openlocfilehash: a3f26e0bb29a58b53547083a4410da849c054b03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043714"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>规划在内部和外部将旧版身份验证方法关闭到网络中。

> [!NOTE]
> 如果要阅读本文，您应该已经知道受支持的新式身份验证拓扑、ADAL 和关于新式身份验证配置的信息，但如果你不知道，以下是你需要启动的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
新式验证不只是启用更安全的身份验证方法（如双重身份验证或基于证书的身份验证），它可以在不需要用户名或密码的情况下执行用户授权。 这非常方便。

本文将帮助您在 Skype for business 服务器上插入已受到拒绝服务（DOS）攻击的漏洞，方法是将用于身份验证的较旧方法（外部、内部或两者）关闭到网络中。 例如，用于帮助停止 DOS 攻击的一种很有用的方法是关闭 Windows 集成身份验证（包括 NTLM 和 Kerberos）。 在外部关闭 NTLM 并依赖基于证书的身份验证有助于防止密码泄露。 这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证--由新式 Auth 启用--不会。 这意味着降低 DOS 攻击的理想选择是在外部阻止 NTLM，而在那里仅使用基于证书的身份验证。

完全正确，让我们开始吧。

## <a name="what-would-you-be-changing"></a>您要更改什么？ 

这些 cmdlet 适用于访问的 SIP 和 Web 服务点。 虽然这两个通道使用不同的访问方法，从 NTLM 和 Kerberos 到匿名访问运行，但所有 Skype for Business 使用的标准方法都已考虑在内。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何获取 Get 和 CsAuthConfig cmdlet

这些 cmdlet 将仅安装在 Microsoft Skype for Business Server 2015 的2018年7月6日的累积更新（6.0.9319.534）中，然后你可以为你的 Skype for business server 推出多种拓扑。

## <a name="topologies"></a>拓扑

请务必记住，这是此方案中涉及的受支持的拓扑。 例如，如果您需要转到支持有关阻止方法的帮助，您需要在下面的类型之间配置配置。 

> [!IMPORTANT]
> 在下面的表和说明中，*新式身份验证*以__MA__为缩写， *Windows 集成身份验证*以__Win__形式进行缩写。 作为提醒，Windows 集成身份验证由两种方法组成： NTLM 和 Kerberos 身份验证。 您需要知道这一点才能正确阅读表格！


|       |看  |从  |参数  |
|---------|:---------|:---------|---------|
|__键入1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__类型2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__类型3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__类型4__   |  MA       | 赢        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__类型5__   |  MA + Win       | 赢        | BlockModernAuthInternally         |

__类型1说明：__ 这是 Skype for business __Server 的 MA 打开时__的默认情况。 换句话说，这是配置 MA 时的*起始点*。

__键入2说明：__ 此拓扑在*外部*阻止 ntlm，但允许 Ntlm 或 Kerberos （对于不支持 ADAL 的客户端）*在内部*工作。 如果你的客户端支持 ADAL，它们将在内部使用 MA。

__类型3说明：__ 此拓扑要求对所有用户进行 MA。 你的所有支持 ADAL 的客户端将在此拓扑中运行，例如，如果你关闭了使用基于证书的身份验证的密码，则不会利用密码。

__类型4说明：__ 此拓扑在内部阻止*了 NTLM，* 并在内部阻止了 MA。 它允许*所有客户端**在内部*使用旧版身份验证方法（甚至支持 ADAL 的客户端）。

__类型5说明：__ *外部*，您的新式 ADAL 客户端将使用 MA，任何不支持 ADAL 的客户端都将使用旧版身份验证方法。 但是，*在内部*，*所有客户端*都将使用旧版身份验证（包括所有支持 ADAL 的客户端）。

在可用选项中跟踪保护密码的目的相当容易。 请注意，理想的情况是在外部使用 MA （例如，通过配置基于证书的身份验证），以避免 DOS 攻击。 如果您在内部将其用于新式客户端，则还将为您的网络提供有关 Skype for Business Server DOS 攻击的经得起未来考验。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>为什么要在全局级别使用 CsAuthConfig 设置

注册`Set-CsAuthConfig`器和 Web 服务角色上的 cmdlet 效果配置。

此 cmdlet 应在 Skype for business server 的全局级别运行。 它*可以*在池级别运行，但*不建议这样做*，因为这会增加安装的复杂性。 通过在池级别运行这些命令，如果你的池没有包含所有角色（例如，没有 Web 服务），则将仅为注册器角色设置设置。 在这种情况下，Web 服务将使用来自全局级别的设置，这可能会造成混淆行为（尤其是在无意中执行此操作时）。

如果客户端使用来自一个池的注册器设置和另一个池的 Web 服务设置，并且身份验证设置处于不一致状态，则 yous 客户端可能无法登录。

此外，如果有一个池角色存在： 
* Set-将仅设置与存在的角色对应的设置。 由于*未*设置某些设置，因此不会提供特殊警告。 
* Get-将返回与存在的角色对应的设置，以及不存在的角色的全局设置。
* 如果池的两个角色都不存在，则 Set-和 Get 将返回错误消息。
* 如果池的两个角色都存在，但未在池级别定义策略，则 Get 将返回错误消息。

Wisest 可能是为了获取这些值，并在进行任何更改之前对其开始状态进行屏幕截图或记录。 您还可以考虑保留 OneNote 中的更改日志。

> [!NOTE]
> 
> 注意：配置 CsAuthConfig 后，必须在每台计算机上运行 CsComputer，以便使设置生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access （LWA），并且必须使用基于表单的访问（FBA）进行外部访问，请重新配置 LWA，以便客户端可以通过匿名访问访问它以支持这些方案。 同样，如果使用电话拨入 Pin，则将仅对外部用户阻止 FBA。 如果他们需要更改 pin，则需要在内部登录他们的公司来执行此操作。

> [!NOTE]
> 
> 如果您使用 BlockWindowsAuthExternally 参数对外阻止 NTLM，请注意，这也会在内部为 SIP 通道阻止 NTLM。 但是，如果 Skype for Business 和 Lync 客户端的版本高于2010，将仍可登录，因为他们将使用 HTTP 上的 NTLM 进行登录，并在内部获取证书以通过 SIP 登录。 但是，如果超过2010的客户端在这种情况下无法在内部登录，则可能需要考虑升级这些应用程序，以便用户可以恢复安全功能。


## <a name="links"></a>链接 
- 有关 PowerShell 的详细信息：
    -  [CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 有关如何使用命令或安装这些命令所需的 CU 的更多指导：
    - [Cmdlet 简介](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015 更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)（常规）
    - [2018 年7月 Skype for Business Server 2015 和 Core COMPONENTS CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) （6.0.9319.534）


 

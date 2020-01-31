---
title: 计划在内部和外部关闭旧版身份验证方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 本文概述了可让管理员更好地控制在企业内部和外部使用的身份验证方法的 cmdlet。 管理员可以在内部或外部打开或关闭身份验证方法。
ms.openlocfilehash: bfbcc8a3b7d6ff6be270853b2da7c9f91df63e2e
ms.sourcegitcommit: 5932ec62a42d7b392fa31c6a2a3462389ac24b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573728"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>计划在内部和外部关闭旧版身份验证方法。

> [!NOTE]
> 如果你即将阅读本文，你应该已了解支持的新式身份验证拓扑、ADAL 以及有关新式身份验证配置，但如果不是这样，你需要启动以下文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
新式身份验证不仅支持更安全的身份验证方法（如两因素身份验证或基于证书的身份验证），还可以在不需要用户名或密码的情况下对用户进行授权。 非常方便。

本文将帮助你在 Skype for business 服务器上插入受拒绝服务（DOS）攻击的漏洞，方法是将用于身份验证的较旧方法（外部、内部或内部）关闭到你的网络。 例如，用于帮助阻止 DOS 攻击的一种好方法是关闭 Windows 集成身份验证（包括 NTLM 和 Kerberos）。 从外部关闭 NTLM 并依赖基于证书的身份验证有助于保护密码免遭泄密。 这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证（由新式身份验证启用）不是。 这意味着减少 DOS 攻击的一个理想选择是阻止来自外部的 NTLM，并且改为在此处使用基于证书的身份验证。

完全正确，让我们开始吧。

## <a name="what-would-you-be-changing"></a>您要更改哪些内容？ 

这些 cmdlet 适用于访问的 SIP 和 Web 服务点。 虽然这两个通道使用不同的访问方法（从 NTLM 和 Kerberos 到匿名访问运行），但已考虑 Skype for Business 使用的所有标准方法。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何获取 CsAuthConfig cmdlet 和 Set cmdlet

这些 cmdlet 将仅安装 Microsoft Skype for Business Server 2015 的2018年7月累积更新（6.0.9319.534），然后你可以为 Skype for business 服务器推出各种拓扑。

## <a name="topologies"></a>朴

请务必记住，这是此方案中所支持的拓扑。 如果需要转到支持阻止方法的帮助，则需要在以下类型之间配置配置。 

> [!IMPORTANT]
> 在下面的表和说明中，*新式身份验证*以__MA__为缩写，而*Windows 集成身份验证*的缩写形式为 " __Win__"。 作为提醒，Windows 集成身份验证由两种方法组成： NTLM 和 Kerberos 身份验证。 您需要知道这一点才能正确阅读表格！


|       |外部  |Alink  |参数  |
|---------|:---------|:---------|---------|
|__键入1__   |  马萨诸塞州获胜       | 马萨诸塞州获胜         |  AllowAllExternallyAndInternally       |
|__键入2__   |  州       | 马萨诸塞州获胜         | BlockWindowsAuthExternally        |
|__键入3__   |  州       | 州        | BlockWindowsAuthExternallyAndInternally        |
|__键入4__   |  州       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__键入5__   |  马萨诸塞州获胜       | Win        | BlockModernAuthInternally         |

__键入1说明：__ 这是 Skype for business__服务器的 MA 处于打开状态__时的默认方案。 换句话说，这是配置 MA 的*起始点*。

__键入2说明：__ 此拓扑将阻止来自*外部*ntlm，但允许 Ntlm 或 Kerberos （对于不支持 ADAL 的客户端）*在内部*工作。 如果您的客户支持 ADAL，他们将在内部使用 MA。

__键入3说明：__ 此拓扑要求所有用户都有 MA。 你的所有支持 ADAL 的客户端都将在此拓扑中运行，例如，如果你关闭使用基于证书的身份验证的密码，则不会利用密码。

__键入4说明：__ 此拓扑在内部*阻止 NTLM 以及内部的 MA* 。 它允许*所有客户端**在内部*使用旧身份验证方法（甚至支持 ADAL 的客户端）。

__类型5说明：__ *外部*，现代的 ADAL 客户将使用 MA，任何不支持 ADAL 的客户端都将使用旧身份验证方法。 但是，*在内部*，*所有客户端*都将使用旧版身份验证（包括所有支持 ADAL 的客户端）。

在可用选项中，我们很容易失去保护密码的目标。 请记住，理想情况是在外部使用 MA （例如，通过配置基于证书的身份验证）来避免 DOS 攻击。 如果您为您的现代客户在内部利用它，您还将为您的网络提供有关 Skype for Business 服务器 DOS 攻击的经得起未来考验的证据。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>为什么要在全局级别使用 CsAuthConfig 设置

注册`Set-CsAuthConfig`机构和 Web 服务角色上的 cmdlet 效果配置。

此 cmdlet 应在 Skype for Business 服务器的全球级别运行。 它*可以*在池级别运行，但*不建议*这样做，因为它会增加安装的复杂性。 通过在池级别运行这些命令，如果你的池没有包括所有角色（例如，它没有 Web 服务），则仅为注册机构角色设置 "设置"。 在这种情况下，Web 服务将通过全局级别的设置进行处理，这可能是混乱的行为（尤其是在无意中执行此操作时）。

如果客户端使用来自一个池的注册器设置和另一个池中的 Web 服务设置，并且身份验证设置处于不一致状态，则 yous 客户端可能无法登录。

同样，如果一个池只有一个角色，请执行以下操作： 
* Set-将仅设置与存在的角色对应的设置。 由于*未*设置某些设置，因此不会提供特殊警告。 
* Get-将返回与存在的角色对应的设置，以及不存在的角色的全局设置。
* 如果一个池没有角色，则 "设置" 和 "获取" 将返回错误消息。
* 如果两个角色都存在于一个池，但未在池级别定义的策略，则 Get-将返回错误消息。

它可能会 wisest 来获取这些值，并在进行任何更改之前将其从屏幕截图或记录到其开始状态。 您还可以考虑保留 OneNote 中的更改日志。

> [!NOTE]
> 
> 注意：配置 CsAuthConfig 后，必须在每台计算机上运行 Enable-CsComputer，才能使设置生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access （LWA），并且必须使用基于窗体的 Access （FBA）进行外部访问，请重新配置 LWA，以便客户可以通过匿名访问访问它以支持这些方案。 同样，如果你使用拨入 Pin，将阻止外部用户的 FBA。 如果他们需要更改其 pin 码，他们将需要在内部登录其公司以执行此操作。

> [!NOTE]
> 
> 如果你使用 BlockWindowsAuthExternally 参数对外阻止 NTLM，请注意，这也会在内部针对 SIP 通道阻止 NTLM。 但是，比2010更高的 Skype for business 和 Lync 客户端将仍然能够登录，因为它们将在内部使用 NTLM 通过 HTTP 登录，然后获取证书以通过 SIP 登录。 但是，超过2010的客户将无法在这种情况下在内部登录，并且你可能需要考虑升级这些应用程序，以便你的用户可以恢复安全功能。


## <a name="links"></a>链接 
- 有关 PowerShell 的详细信息：
    -  [CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 有关如何使用命令或对安装所需的 CU 的更多指导，请执行以下操作：
    - [Cmdlet 简介](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)（常规）
    - [2018 年7月 Skype for Business Server 2015，核心组件 CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) （6.0.9319.534）


 

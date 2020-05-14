---
title: 新式验证支持的 Skype for business 拓扑
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
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 443980f6ecf2bdf170974bf0fdc0dd64f3657e67
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219692"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>新式验证支持的 Skype for business 拓扑

本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。

## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business 中的新式验证

Skype for Business 可以利用新式验证的安全优势。 由于 Skype for business 与 Exchange 密切合作，因此 Exchange 的 MA 状态也会影响 Skype for Business 客户端用户将看到的登录行为。 如果你拥有 Skype for Business 拆分域混合，也会应用此项。 这是许多移动部件，但此处的目标是可轻松可视化受支持拓扑的列表。

对于 Skype for Business、Skype for business online、Exchange Server 和 Exchange online，MA 支持哪些拓扑？

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business 中支持的 MA 拓扑

有可能有两个服务器应用程序，以及两个 Microsoft 365 或 Office 365 工作负载，与 MA 使用的 Skype for business 拓扑有关。

- Skype for Business server （CU 5）本地

- Skype for Business online （SFBO）

- Exchange server 本地

- Exchange server online （EXO）

MA 的另一个重要部分是知道用户的身份验证（身份验证）和授权（authZ）将发生的位置。 这两个选项为：

- Azure AD，在 Microsoft 云中联机

- Active Directory 联合服务器（ADFS）本地

因此，它看起来有点类似于在 EXO 和 SFBO 中使用 Azure AD 的云，Exchange Server （EXCH）和 Skype for Business Server （SFB）本地。

![打开 MA 时可涉及的所有应用程序（Exchange 和 Skype for Business）和工作负荷（EXO 和 SFBO）以及这两个授权服务器（ADFS 和 evoSTS）的示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

以下是受支持的拓扑。 请记下图形的键：

- 如果图标灰显或灰色，则不在方案中使用。

- EXO 是 Exchange Online。

- SFBO 是 Skype for Business Online。

- EXCH 是 Exchange 内部部署。

- SFB 是 Skype for business 内部部署。

- 授权服务器由三角形表示，例如，Azure AD 是其背后有云的三角形。

- 箭头指向客户端尝试访问指定服务器资源时将使用的授权服务器。

首先，让我们在仅本地或仅限云的拓扑中使用具有 Skype for Business 的 MA。

> [!IMPORTANT]
> 你是否已准备好在 Skype for Business Online 中设置新式验证？ 启用此功能的步骤在[这里](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|仅云  <br/> |![受支持的 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)用户托管/邮箱位置：联机  <br/> |MA 对于 EXO 和 SFBO 都是打开的。  <br/> 因此，授权服务器是 Azure AD。  <br/> |多因素身份验证（MFA）、基于客户端证书的身份验证（CBA）、条件访问（CA）/Mobile 应用程序管理（MAM）（Intune）。 \*  <br/> |
|仅限本地  <br/> |![受支持的 SFB 与 MA 拓扑，仅限本地使用。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)用户托管/邮箱位置：内部部署  <br/> |MA 针对内部部署的 SFB。  <br/> 因此，授权服务器是 ADFS。  <br/> 有关配置的详细信息，请参阅[本文。](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA （不支持仅限 Windows 桌面-移动客户端）。 无 Exchange 集成功能。  <br/><p> **我们不建议采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> 建议在 Skype for Business 和 Exchange （及其在线版）之间使用相同的 MA 状态，以减少提示次数。

混合拓扑涉及 SFB 拆分域混合的组合。 以下是当前支持的混合拓扑：

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|混合1  <br/> |![支持的 SFB 与 MA 拓扑，Mixed 1 （EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 用户托管/邮箱位置： EXO 和 SFB  <br/> |没有为 SFB 启用 MA;此拓扑中不提供 SFB MA 功能。  <br/> |SFB 的 MA 功能。  <br/> |
|混合2  <br/> |![支持的带有 S4B 混合拓扑2、SFBO 和 MA 的 MA，使用 EXCH on 本地。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 用户托管/邮箱位置： EXCH 和 SFBO  <br/> |MA 仅适用于 SFBO。 授权服务器是托管在 SFBO 中的用户的 Azure AD，但 EXCH 本地的 AD。  <br/> |使用 Intune 的 MFA、CBA、CA/MAM。\*  <br/> |
|混合3  <br/> |![支持的 MA 与 SFB、EXO、MA on、EXCH 和 SFB 在本地使用。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 用户托管/邮箱位置： EXO + SFB 或 EXCH + SFB  <br/> |此拓扑中不提供任何 SFB MA 功能  <br/> |SFB 的 MA 功能。  <br/> |
|混合4  <br/> |![支持的 MA 与 SFB、SFBO、MA 打开、加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 用户托管/邮箱位置： EXCH + SFBO 或 EXCH + SFB  <br/> |MA 对 SFBO 是打开的，因此，授权服务器是托管在 SFBO 中的用户的 Azure AD。 SFB 和 EXO 中的本地用户使用 AD。  <br/> |仅用于联机用户的仅 MFA、CBA、CA/MAM 和 Intune。\*  <br/> |
|混合5  <br/> |![SFB、EXO 和 MA 中支持的 MA，以及 SFBO 和，以及在本地的 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 用户托管/邮箱位置： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 同时在 EXO 和 SFBO 中，因此，授权服务器是托管在 SFBO 中的用户的 Azure AD;EXCH 和 SFB 中的本地用户使用 AD。  <br/> |仅用于联机用户的仅 MFA、CBA、CA/MAM 和 Intune。\*  <br/> |
|混合6  <br/> |![在混合的6拓扑中，新式验证在所有四个可能位置中，而对于新式身份验证，则是理想的理想。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 用户托管/邮箱位置： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 在无处不在，因此授权服务器是所有用户的 Azure AD。 （联机和本地）  <br/>  [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)有关部署步骤，请参阅。 <br/> |对所有用户的 MFA、CBA 和 CA/MAM （通过 Intune）。  <br/> |

\*-MFA 包括 Windows Desktop、MAC、iOS、Android 设备和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 设备;具有 Intune 的 CA/MAM，包括 Android 和 iOS 设备。

> [!IMPORTANT]
> 请务必注意，在某些情况下，用户可能会看到**多个提示**，特别是在客户端可能需要和请求的所有服务器资源中的 MA 状态不相同，这与所有版本的混合拓扑一样。

> [!IMPORTANT]
> 另请注意，在某些情况下（特别是混合1、3和5），必须设置[AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项，以正确配置 Windows 桌面客户端。



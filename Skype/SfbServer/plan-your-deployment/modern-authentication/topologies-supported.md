---
title: 新式验证支持的 Skype for Business 拓扑
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
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持哪些联机和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810092"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>新式验证支持的 Skype for Business 拓扑

本文列出了 Skype for Business 中的新式验证支持哪些联机和本地拓扑，以及适用于每个拓扑的安全功能。

## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business 中的新式验证

Skype for Business 可以利用新式验证的安全优势。 由于 Skype for Business 与 Exchange 紧密配合，因此 Skype for Business 客户端用户将看到的登录行为也将受 Exchange 的 MA 状态影响。 如果你拥有 Skype for Business 拆分域混合，这同样适用。 这有许多移动部件，但此处的目标是轻松直观地显示支持的拓扑列表。

鉴于 Skype for Business、Skype for Business online、Exchange Server和 Exchange Online，MA 支持哪些拓扑？

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business 中支持的 MA 拓扑

可能有两个服务器应用程序和两个 Microsoft 365 或 Office 365 工作负载，它们涉及 MA 使用的 Skype for Business 拓扑。

- Skype for Business server (CU 5) 本地部署

- Skype for Business online (SFBO) 

- 内部部署 Exchange 服务器

- Exchange Server online (EXO) 

MA 的另一个重要部分是了解身份验证 (身份验证) 身份验证 (authZ) 将发生。 两个选项是：

- Microsoft 云中的 Azure AD 联机

- Active Directory 联合服务器 (ADFS) 本地部署

因此，它看起来有点类似，在云中使用 Azure AD 的 EXO 和 SFBO，以及 Exchange Server (EXCH) 和 Skype for Business (SFB) 部署。

![Exchange 和 Skype for Business) 和工作负载 (EXO 和 SFBO) 以及启用 MA 时可能涉及的所有授权服务器 (ADFS 和 evoSTS) 的示例。 (](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

以下是受支持的拓扑。 请注意图形的键：

- 如果图标灰显或灰显，则不用于此方案。

- EXO 是 Exchange Online。

- SFBO 是 Skype for Business Online。

- EXCH 是 Exchange 内部部署。

- SFB 是本地 Skype for Business。

- 授权服务器由三角形表示，例如，Azure AD 是一个三角形，其后面是云。

- 箭头指向在客户端尝试访问指定的服务器资源时将使用的授权服务器。

首先，让我们在仅本地拓扑或仅云拓扑中介绍 SKYPE for Business 的 MA。

> [!IMPORTANT]
> 准备好在 Skype for Business Online 中设置新式验证了吗？ 此处是启用此功能 [的步骤](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|仅云  <br/> |![支持 SFB 和 MA 拓扑，仅云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)用户所居/邮箱位置：联机  <br/> |MA 适用于 EXO 和 SFBO。  <br/> 因此，授权服务器是 Azure AD。  <br/> |多重身份验证 (MFA) 、基于客户端证书的身份验证 (CBA) 、条件访问 (CA) /移动应用程序管理 (MAM) Intune。 \*  <br/> |
|仅 On-prem  <br/> |![支持 SFB 和 MA 拓扑，仅本地。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)用户所定位/邮箱位置：本地  <br/> |MA 适用于本地 SFB。  <br/> 因此，授权服务器是 ADFS。  <br/> 有关配置的详细信息，请参阅 [本文。](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (Windows 桌面 - 不支持移动客户端) 。 无 Exchange 集成功能。  <br/><p> **建议不要采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> 建议 Skype for Business 和 Exchange (及其联机对应设备中的 MA 状态) 减少提示数。

混合拓扑涉及 SFB 拆分域混合的组合。 这些是当前支持的混合拓扑：

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![支持 SFB 和 MA 拓扑，混合 1 (EXO + SFB) 。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 用户所在的用户/邮箱：EXO 和 SFB  <br/> |未为 SFB 启用 MA;此拓扑中没有任何 SFB MA 功能可用。  <br/> |SFB 没有 MA 功能。  <br/> |
|混合 2  <br/> |![支持 MA 和 S4B 混合拓扑 2、SFBO 以及 MA，与 EXCH on-prem 一起工作。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 用户所定位/邮箱：EXCH 和 SFBO  <br/> |MA 仅适用于 SFBO。 授权服务器是托管在 SFBO 中的用户的 Azure AD，而 EXCH 本地的 AD。  <br/> |Intune 的 MFA、CBA、CA/MAM。\*  <br/> |
|混合 3  <br/> |![支持 MA 与 SFB、EXO（MA on）以及 EXCH 和本地 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 用户所在的/邮箱：EXO + SFB 或 EXCH + SFB  <br/> |此拓扑中没有任何 SFB MA 功能可用  <br/> |SFB 没有 MA 功能。  <br/> |
|混合 4  <br/> |![支持 MA 与 SFB、SFBO（MA 打开）以及 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 用户所在的/邮箱：EXCH +SFBO 或 EXCH + SFB  <br/> |MA 适用于 SFBO，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD。 SFB 和 EXO 中的用户使用 AD。  <br/> |MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*  <br/> |
|混合 5  <br/> |![支持 SFB 中的 MA、带 MA 的 EXO 以及具有 MA 的 SFBO，以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 在 EXO 和 SFBO 中均打开，因此授权服务器是托管在 SFBO 中的用户的 Azure AD;EXCH 和 SFB 中的用户使用 AD。  <br/> |MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*  <br/> |
|混合 6  <br/> |![在混合 6 拓扑中，新式验证在所有四个位置均启用 - 对于新式身份验证，是理想选择。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 位于任何地方，因此授权服务器是所有用户的 Azure AD。  (联机和本地)   <br/>  请参阅 [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) 部署步骤。 <br/> |MFA、CBA 和 CA/MAM (通过 Intune) 适用于所有用户。  <br/> |

\* - MFA 包括 Windows 桌面、MAC、iOS、Android 设备和 Windows 手机;CBA 包括 Windows 桌面、iOS 和 Android 设备;使用 Intune 的 CA/MAM 包括 Android 和 iOS 设备。

> [!IMPORTANT]
> 值得注意的是，在某些情况下，用户可能会看到多个提示，尤其是当客户端可能需要和请求的所有服务器资源中的 MA 状态不相同时，与混合拓扑的所有版本的情况一样。

> [!IMPORTANT]
> 另请注意，在某些情况下 (混合 1、3 和 5) 必须设置 [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) 注册表项，以便正确配置 Windows 桌面客户端。



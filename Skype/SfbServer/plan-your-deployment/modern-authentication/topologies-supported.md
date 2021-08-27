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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了哪些联机拓扑和本地拓扑受 Skype for Business 中的新式验证支持，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 92cab2bbef535062743032438533eb9489155bab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584966"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>新式验证支持的 Skype for Business 拓扑

本文列出了哪些联机拓扑和本地拓扑受 Skype for Business 中的新式验证支持，以及适用于每个拓扑的安全功能。

## <a name="modern-authentication-in-skype-for-business"></a>新式验证Skype for Business

Skype for Business可以利用新式验证的安全优势。 由于Skype for Business网站Exchange，客户端用户Skype for Business的登录行为也将受客户端用户的 MA 状态Exchange。 如果你拥有一个拆分域混合Skype for Business也将适用。 这有许多移动部件，但此处的目标是轻松直观地显示支持的拓扑列表。

如果Skype for Business、Skype for Business联机、Exchange Server Exchange，MA 支持哪些拓扑？

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>支持的 MA 拓扑Skype for Business

MA 使用的拓扑中可能涉及两个服务器Microsoft 365或Office 365或Skype for Business工作负荷。

- Skype for Business本地 (CU 5) 服务器

- Skype for Business SFBO (联机) 

- Exchange本地服务器

- Exchange EXO (联机) 

MA 的另一个重要部分是了解身份验证 (身份验证) 身份验证 (身份验证) 身份验证将在何处进行。 两个选项是：

- Microsoft 云中的联机 Azure AD

- Active Directory 联合服务器 (本地) ADFS

因此，它看起来有点类似，EXO 和 SFBO 位于具有 Azure AD 的云中，Exchange Server (EXCH) 和 Skype for Business 服务器 (SFB) 部署。

![启用 MA 时可能涉及的所有应用程序 (Exchange、Skype for Business) 和工作负荷 (EXO 和 SFBO) 以及两个授权服务器 (ADFS 和 evoSTS) 的示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

以下是受支持的拓扑。 请注意图形的键：

- 如果图标灰显或灰显，则不用于此方案。

- EXO Exchange Online。

- SFBO Skype for Business Online。

- EXCH Exchange本地部署。

- SFB Skype for Business本地部署。

- 授权服务器由三角形表示，例如，Azure AD 是一个三角形，其背后的云。

- 箭头指向授权服务器，客户端尝试访问指定的服务器资源时将使用该服务器。

首先，让我们介绍 MA 和Skype for Business本地拓扑或仅云拓扑中的 MA。

> [!IMPORTANT]
> 准备好在 Skype for Business Online 中设置新式验证了吗？ 启用此功能[的步骤在此处。](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|仅云  <br/> |![支持 SFB 和 MA 拓扑，仅云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)用户所管理/邮箱位于：联机  <br/> |MA 对 EXO 和 SFBO 均打开。  <br/> 因此，授权服务器是 Azure AD。  <br/> |多重身份验证 (MFA) 、基于客户端证书的身份验证 (CBA) 、条件访问 (CA) /移动应用程序管理 (MAM) 和 Intune。 \*  <br/> |
|仅 On-prem  <br/> |![支持 SFB 和 MA 拓扑，仅本地。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)用户所管理/邮箱位于：本地  <br/> |MA 为本地 SFB 打开。  <br/> 因此，授权服务器为 ADFS。  <br/> 有关配置的详细信息，请参阅 [本文。](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |仅 (Windows MFA - 不支持移动客户端) 。 没有Exchange集成功能。  <br/><p> **建议不要采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> 建议 MA 状态在 Skype for Business 和 Exchange (及其联机) 相同，以减少提示数。

混合拓扑涉及 SFB 拆分域混合的组合。 目前支持以下混合拓扑：

|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![支持 SFB 与 MA 拓扑、混合 1 (EXO + SFB) 。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 用户所管理/邮箱位于：EXO 和 SFB  <br/> |未为 SFB 启用 MA;此拓扑中没有任何 SFB MA 功能可用。  <br/> |SFB 没有 MA 功能。  <br/> |
|混合 2  <br/> |![S4B 混合拓扑 2 支持 MA，SFBO 加上 MA 与 EXCH on-prem 一起运行。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 用户所定位/邮箱：EXCH 和 SFBO  <br/> |MA 仅适用于 SFBO。 授权服务器是托管在 SFBO 中的用户的 Azure AD，而 AD 适用于本地 EXCH。  <br/> |使用 Intune 的 MFA、CBA、CA/MAM。\*  <br/> |
|混合 3  <br/> |![支持 MA 与 SFB、使用 MA 的 EXO 以及本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 用户所在的用户/邮箱：EXO + SFB 或 EXCH + SFB  <br/> |此拓扑中没有任何 SFB MA 功能可用  <br/> |SFB 没有 MA 功能。  <br/> |
|混合 4  <br/> |![支持 MA 与 SFB、SFBO（MA 打开）以及 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 用户所在的用户/邮箱：EXCH +SFBO 或 EXCH + SFB  <br/> |MA 为 SFBO 打开，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD。 SFB 和 EXO 中的 On-prem 用户使用 AD。  <br/> |MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*  <br/> |
|混合 5  <br/> |![SFB 中支持的 MA、带 MA 的 EXO 和带 MA 的 SFBO，以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 在 EXO 和 SFBO 中均打开，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD;EXCH 和 SFB 中的用户使用 AD。  <br/> |MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*  <br/> |
|混合 6  <br/> |![在混合 6 拓扑中，所有四个假设位置都启用新式验证- 对于新式身份验证，这是理想选择。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 位于任何地方，因此授权服务器是适用于所有用户的 Azure AD。  (联机和本地部署)   <br/>  请参阅 [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) 了解部署步骤。 <br/> |MFA、CBA 和 CA/MAM (Intune) 适用于所有用户。  <br/> |

\*- MFA 包括Windows、MAC、iOS、Android 设备和 Windows 手机;CBA 包括Windows桌面、iOS 和 Android 设备;使用 Intune 的 CA/MAM 包括 Android 和 iOS 设备。

> [!IMPORTANT]
> 必须注意的是，在某些情况下，用户可能会看到多个提示，尤其是当客户端可能需要和请求的所有服务器资源中的 MA 状态不同时，与混合拓扑的所有版本一样。

> [!IMPORTANT]
> 另请注意，在某些情况下， (混合 1、3 和 5) [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项必须设置为正确配置 Windows 桌面客户端。
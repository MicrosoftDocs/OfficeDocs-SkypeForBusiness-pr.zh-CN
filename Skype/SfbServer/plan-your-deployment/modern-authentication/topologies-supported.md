---
title: 支持新式验证的 Skype for Business 拓扑
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: cc849dc1df0f4bf97bb362449ef1ded58596cb91
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001797"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>支持新式验证的 Skype for Business 拓扑
 
本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
  
## <a name="modern-authentication-in-skype-for-business"></a>Skype for Business 中的新式验证

Skype for Business 可以利用新式验证的安全优势。因为 Skype for Business 与 Exchange 密切协作，Skype for Business 客户端用户的登录行为也将受 Exchange 的 MA 状态影响。如果你具有混合 Skype for Business 拆分域，这一点也适用。这其中有很多活动部分，但其目的是为了轻松地将支持的拓扑列表可视化。
  
对于 Skype for Business、Skype for Business Online、Exchange Server 和 Exchange Onlin，MA 支持哪些拓扑？
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Skype for Business 中支持的 MA 拓扑

MA 使用的 Skype for Business 拓扑可能涉及两个服务器应用程序和两个 Office 365 工作负载。
  
- 为业务服务器 (累积更新 5) 内部部署的 Skype
    
- Skype for Business Online (SFBO)
    
- Exchange Server 本地
    
- Exchange Server Online (EXO)
    
MA 的另一个重要部分是了解在何处执行用户身份验证 (authN) 和授权 (authZ)。有两个选项：
  
- Azure AD，在 Microsoft Cloud 中在线进行
    
- Active Directory Federation Server (ADFS) 本地
    
以便它看起来有点如下所示，与 Azure AD 云中 SFBO EXO 与 Exchange Server (EXCH) 和 Skype 的业务服务器 (SFB) 上-prem.
  
![所有应用程序（Exchange 和 Skype for Business）和工作负载（EXO 和 SFBO）以及开启 MA 时会涉及的两种授权服务器（ADFS 和 evoSTS）示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
支持的拓扑如下：请注意图形的图例：
  
- 如果图标变暗或灰显，则表明在此情况下无法使用。
    
- EXO 是 Exchange Online。
    
- SFBO 是 Skype for Business Online。
    
- EXCH 是 Exchange 本地。
    
- SFB 是 Skype for Business 本地。
    
- 授权服务器用三角形表示，例如，Azure AD 是后面有一朵云的三角形。
    
- 箭头指向当客户尝试访问指定的服务器资源时将使用的授权服务器。
    
首先，我们来看看仅本地或仅云拓扑中的 Skype for Business 的 MA。
  
> [!IMPORTANT]
> 是否已准备好在 Skype for Business Online 中设置新式验证？ 启用此功能的步骤所右[此处](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 
  
|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|仅云  <br/> |![支持 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)用户托管/邮箱位置：在线   <br/> |MA 对于 EXO 和 SFBO 为启用状态。  <br/> 因此，授权服务器是 Azure AD。  <br/> |多重身份验证 (MFA)，基于客户端证书身份验证 (CBA)，条件访问 (CA) / 与 Intune 的移动应用程序管理 (MAM)。 \*  <br/> |
|仅本地  <br/> |![支持 SFB 与 MA 拓扑，仅限本地部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)用户托管/邮箱位置：本地  <br/> |MA 对于 SFB 本地为启用状态。  <br/> 因此，授权服务器是 ADFS。  <br/> 有关配置详细信息，请参阅[本文。](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA（仅限 Windows 桌面 - 不支持移动客户端）。不提供 Exchange 集成功能。  <br/> |
   
> [!IMPORTANT]
> 建议 Skype for Business 和 Exchange（及其在线对应项）的 MA 状态应相同，以减少提示数量。 
  
混合拓扑涉及 SFB 拆分域混合组合。当前支持下列混合拓扑：
  
|拓扑名称  <br/> |示例  <br/> |说明  <br/> |支持  <br/> |
|:-----|:-----|:-----|:-----|
|混合 1  <br/> |![支持 SFB 与 MA 拓扑，混合 1 (EXO + SFB)。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 用户托管/邮箱位置：EXO 和 SFB  <br/> |MA 对 SFB 未启用，此拓扑中不提供 SFB MA 功能。  <br/> |SFB 无 MA 功能。  <br/> |
|混合 2  <br/> |![支持 MA 与 S4B 混合拓扑 2，使用本地 EXCH 的 SFBO 加 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 用户托管/邮箱位置：EXCH 和 SFBO  <br/> |MA 仅在适用于 SFBO。 授权服务器是用户驻留在 SFBO，但 EXCH 本地 AD Azure AD。  <br/> |MFA，CBA，CA/MAM 与 Intune。\*  <br/> |
|混合 3  <br/> |![支持 MA 与 SFB，启用了 MA 的 EXO，加本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 用户托管/邮箱位置：EXO + SFB 或 EXCH + SFB  <br/> |此拓扑中不提供 SFB MA 功能  <br/> |SFB 无 MA 功能。  <br/> |
|混合 4  <br/> |![支持 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 用户托管/邮箱位置：EXCH +SFBO 或 EXCH + SFB   <br/> |MA 上的 SFBO，所以授权服务器是 Azure AD 的用户驻留在 SFBO。 在 SFB 和 EXO 上 prem 用户使用 AD。  <br/> |MFA，CBA，CA/MAM 与 Intune 仅联机用户。\*  <br/> |
|混合 5  <br/> |![支持 SFB 中的 MA、具有 MA 的 EXO、具有 MA 的 SFBO 以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 位于 EXO 和 SFBO，因此用户驻留在 SFBO; 授权服务器是 Azure AD在 EXCH 和 SFB 上 prem 用户使用 AD。  <br/> |MFA，CBA，CA/MAM 与 Intune 仅联机用户。\*  <br/> |
|混合的 6  <br/> |![在混合 6 拓扑中，所有 4 个可能位置都启用新式验证 - 采用新式验证时的理想情况。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 上无处不在所以授权服务器是为所有用户的 Azure AD。 (在线和本地)  <br/>  请参阅[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)的部署步骤。 <br/> |MFA、 CBA 和 CA/MAM （通过 Intune) 的所有用户。  <br/> |
   
\*-MFA 包括 Windows 桌面、 MAC、 iOS、 Android 设备和 Windows Phone;CBA 包括 Windows 桌面、 iOS 和 Android 设备;CA/MAM 与 Intune，包括 Android 和 iOS 设备。 
  
> [!IMPORTANT]
> 必须注意的是，在某些情况下，用户可能会看到**多个提示**，尤其是当客户可能需要和请求的服务器资源的 MA 状态不同时，因为这种情况下包含所有版本的混合拓扑。

> [!IMPORTANT]
> 另请注意，在某些情况下 （混合 1、 3 和 5 专门） 必须正确配置 Windows 的桌面客户端设置[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项。
  


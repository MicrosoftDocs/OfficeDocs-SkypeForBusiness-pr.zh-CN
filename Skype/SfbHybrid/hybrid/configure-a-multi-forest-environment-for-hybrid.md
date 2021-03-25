---
title: 部署资源林拓扑
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 以下各节提供有关如何在资源/用户林模型中配置具有多个林的环境的指导，以在混合方案中提供 Skype for Business 功能。
ms.openlocfilehash: 2f4d0c84997dcc0d19439210e72eaf01a7a1ff26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119001"
---
# <a name="deploy-a-resource-forest-topology"></a>部署资源林拓扑
 
以下各节提供有关如何在资源/用户林模型中配置具有多个林的环境的指导，以在混合方案中提供 Skype for Business 功能。 
  
![用于混合的多林环境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>拓扑要求

支持多个用户林。 请注意下列事项： 
    
- 有关混合配置中 Lync Server 和 Skype for Business Server[](plan-hybrid-connectivity.md#server-version-requirements)的支持版本，请参阅规划 Skype for Business Server 与[Microsoft 365 或 Office 365](plan-hybrid-connectivity.md)之间的混合连接中的服务器版本要求。
    
- Exchange Server部署在一个或多个林中，其中可能包含或不包含包含 Skype for Business Server 的林。 确保已应用最新的累积更新。
    
- 有关与 Exchange Server 共存的详细信息，包括本地和联机的各种组合中的支持标准和限制，请参阅 Plan to integrate Skype for [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) Business [and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的功能支持。
    
  
## <a name="user-homing-considerations"></a>用户hoshoing considerations

本地 Skype for Business 用户可以在本地或联机部署 Exchange。 Skype for Business Online 用户应该使用 Exchange Online 以获得最佳体验;但是，这不是必需的。 无论是哪种情况，都不需要本地 Exchange 实现 Skype for Business。
  
## <a name="configure-forest-trusts"></a>配置林信任

在资源林拓扑中，托管 Skype for Business Server 的资源林必须信任每个包含将访问它的用户帐户的帐户林。 如果有多个用户林，则启用跨林身份验证时，必须针对其中每个林信任启用名称后缀路由。 有关说明，请参阅 [管理林信任](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11))。 如果你已Exchange Server另一个林中部署，并且它为 Skype for Business 用户提供功能，则托管 Exchange 的林必须信任托管 Skype for Business Server 的林。 例如，如果 Exchange 部署在帐户林中，这实际上意味着该配置需要帐户和 Skype for Business 林之间的双向信任。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>将帐户同步到托管 Skype for Business 的林中

当 Skype for Business Server 部署在一个林 (资源林) 中，但向一个或多个其他林 (帐户林) 中的用户提供功能时，其他林中的用户必须表示为部署了 Skype for Business Server 的林中的已禁用用户对象。 需要部署和配置标识管理产品（如 Microsoft Identity Manager）以设置用户，以及将用户从帐户林同步到部署 Skype for Business Server 的林。 用户必须作为禁用的用户对象同步到托管 Skype for Business Server 的林中。 用户无法同步为 Active Directory 联系人对象，因为 Azure Active Directory Connect 无法将联系人正确同步到 Azure AD 以便与 Skype 一同使用。
  
无论多林配置如何，托管 Skype for Business Server 的林也可以为同一林中任何已启用的用户提供功能。
  
若要获取正确的标识同步，需要同步以下属性： 
  
|**用户林**|**资源林**|
|:-----|:-----|
|选择的帐户链接属性  <br/> |选择的帐户链接属性  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
所选 [帐户链接属性](/azure/active-directory/hybrid/plan-connect-design-concepts) 将用作源定位标记。 如果您喜欢使用一个不同的不可变属性，您可以这样做;只需确保在 AAD Connect 配置期间编辑 AD FS 声明规则并选择属性。
  
不要同步林之间的 UPN。 在测试期间，我们发现我们需要为每个用户林使用唯一的 UPN，因为您不能在多个林之间使用相同的 UPN。 因此，我们提供了两种可能性，即同步 UPN 或不同步。 
  
- 如果每个用户林中的唯一 UPN 未同步到资源林中关联的已禁用对象，则单一登录 (SSO) 将至少中断初始登录尝试 (假定用户选择了保存密码) 的选项。 在 Skype for Business 客户端中，我们假定 SIP/UPN 值相同。 由于此方案中的 SIP 地址是 user@company.com，但用户林中已启用对象的 UPN 实际上为 user@contoso.company.com，因此初始登录尝试将失败，并提示用户输入凭据。 输入正确/实际 UPN 后，将针对用户林中的域控制器完成身份验证请求，并且登录将成功。
    
- 如果将每个用户林中的唯一 UPN 同步到资源林中关联的已禁用对象，则 AD FS 身份验证将失败。 匹配规则将在资源林中的对象上查找 UPN，该 UPN 已被禁用，无法用于身份验证。 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>创建 Microsoft 365 或 Office 365 组织

接下来，你需要预配 Microsoft 365 或 Office 365 组织以用于你的部署。 有关详细信息，请参阅 Microsoft 云产品/服务订阅、许可证 [、帐户和租户](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。 
  
## <a name="configure-active-directory-federation-services"></a>配置 Active Directory 联合身份验证服务

拥有租户后，您需要在每个用户林 (AD FS) Active Directory 联合身份验证服务。 这假定每个林具有唯一的 SIP 和 SMTP 地址以及 (UPN) 用户主体名称。 AD FS 是可选的，在此处用于获取 SSO (单一) 。 DirSync with Password Sync 也受支持，还可以用于 AD FS。 
  
仅测试具有匹配的 SIP/SMTP 和 UPN 的部署。 如果 SIP/SMTP/UPN 不匹配，可能会导致功能降低，例如 Exchange 集成和 SSO 出现问题。 
  
除非您对来自每个林的用户使用唯一的 SIP/SMTP/UPN，否则您仍可能会遇到 SSO 问题，无论 AD FS 部署在何处： 
  
- 资源/用户林之间的单向或双向信任，其中 AD FS 场部署在每个用户林中，所有用户共享公用 SIP/SMTP 域，但每个用户林的唯一 UPN。 
    
- 仅在资源林中部署了 AD FS 服务器场的资源/用户林之间的双向信任，所有用户共享公用 SIP/SMTP 域，但每个用户林的唯一 UPN。 
    
通过将 AD FS 服务器场置于每个用户林中，并针对每个林使用唯一的 SIP/SMTP/UPN，我们解决了这两个问题。 在身份验证尝试期间，将仅搜索并匹配该特定用户林中的帐户。 这将帮助提供更加无缝的身份验证过程。 
  
这将是 R2 AD FS Windows Server 2012标准部署，应在继续之前正常工作。 有关说明，请参阅[如何安装 AD FS 2012 R2 For Microsoft 365 或 Office 365。](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx) 
  
部署后，您必须编辑声明规则以匹配之前选择的"源定位标记"。 在 AD FS MMC 中的"信赖方信任"下，右键单击 **"Microsoft 365** 标识平台"或 **"Microsoft Office 365** 标识平台"，然后选择"编辑声明规则 **"。** 编辑第一个规则，将 ObjectSID 更改为 **employeeNumber**。 
  
![多林编辑规则屏幕](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>配置 AAD Connect

在资源林拓扑中，资源林和任何帐户林中的用户属性 (帐户) 同步到 Azure AD。 为此，最简单且推荐的方法就是让 Azure AD Connect 同步和合并已启用用户帐户的所有林和包含 Skype for Business 的林中的用户标识。 有关详细信息，请参阅为 Skype for Business 和 Teams 配置[Azure AD Connect。](configure-azure-ad-connect.md)

请注意，AAD Connect 不提供帐户和资源林之间的本地同步。 必须使用 Microsoft Identity Manager 或类似产品单独配置，如前面所述。
  
完成操作且 AAD Connect 正在合并时，如果查看 metaverse 中的对象，应看到类似以下内容： 
  
![多林 Metaverse 对象屏幕](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
绿色突出显示的属性从 Microsoft 365 或 Office 365 合并，黄色来自用户林，蓝色来自资源林。 
  
这是一个测试用户，你可以看到 AAD Connect 已标识用户中的 sourceAnchor 和 cloudSourceAnchor，以及 Microsoft 365 或 Office 365 中的资源林对象，在我们的案例 1101 中，这是之前选择的 employeeNumber。 然后，它能够将该对象合并到您上面看到的对象中。 
  
有关详细信息，请参阅 [将本地目录与 Azure Active Directory 集成](/azure/active-directory/hybrid/whatis-hybrid-identity)。 
  
AAD Connect 应该使用默认值进行安装，以下情况除外： 
  
1. 单一登录 - 已部署 AD FS 且正常工作：选择 **"不配置"。**
    
2. 连接目录：添加所有域。
    
3. 标识本地目录中的用户：选择"用户 **标识** 存在于多个目录"，然后选择 **ObjectSID** 和 **msExchangeMasterAccountSID** 属性。
    
4. 在 Azure AD 中标识用户：源定位标记：在阅读选择良好的 [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)属性 、用户主体名称 - **userPrincipalName** 后选择的属性。
    
5.  可选功能：选择是否已部署 Exchange 混合。
    
    > [!NOTE]
    >  如果您只有 Exchange Online，则由于 CNAME 重定向，在自动发现期间 OAuth 失败可能出问题。 若要更正此错误，你需要通过从 Skype for Business Server 命令行管理程序运行以下 cmdlet 来设置 Exchange 自动发现 URL：
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS 场：选择"使用现有 Windows Server 2012 **R2 AD FS** 场"，然后输入 AD FS 服务器的名称。
    
7.  完成向导并执行必要的验证。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>配置 Skype for Business Server 的混合连接

遵循配置 Skype for Business 混合的最佳实践。 有关详细信息，请参阅规划混合[连接和](plan-hybrid-connectivity.md)[配置混合连接](configure-hybrid-connectivity.md)。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>配置混合连接Exchange Server

如有必要，请按照配置 Exchange 混合的最佳实践操作。 有关详细信息，请参阅混合 [Exchange Server部署](/exchange/exchange-hybrid)。 

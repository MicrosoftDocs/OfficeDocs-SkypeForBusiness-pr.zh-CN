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
description: 以下各节提供了有关如何配置在资源/用户林模型中具有多个林的环境以在混合方案中提供 Skype for Business 功能的指南。
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221476"
---
# <a name="deploy-a-resource-forest-topology"></a>部署资源林拓扑
 
以下各节提供了有关如何配置在资源/用户林模型中具有多个林的环境以在混合方案中提供 Skype for Business 功能的指南。 
  
![混合的多林环境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>拓扑要求

支持多个用户林。 请注意以下几点： 
    
- 有关混合配置中的 Lync Server 和 Skype for business Server 支持的版本，请参阅在[Skype For Business Server 与 Microsoft 365 或 Office 365 之间规划混合连接](plan-hybrid-connectivity.md)中的[服务器版本要求](plan-hybrid-connectivity.md#server-version-requirements)。
    
- 可以在一个或多个林中部署 Exchange 服务器，其中可能包含（也可能不包含）包含 Skype for Business Server 的林。 请确保您已应用最新的累积更新。
    
- 有关与 Exchange Server 共存的详细信息（包括在各种本地和联机组合中支持的条件和限制），请参阅[Plan for 集成 Skype For business 和 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[功能支持](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。
    
  
## <a name="user-homing-considerations"></a>用户托管注意事项

驻留在本地的 Skype for Business 用户可以让 Exchange 驻留在本地或联机。 Skype for Business Online 用户应使用 Exchange Online 获得最佳体验;但是，这并不是必需的。 在这两种情况下，无需在本地 Exchange 中实施 Skype for Business。
  
## <a name="configure-forest-trusts"></a>配置林信任

在资源林拓扑中，托管 Skype for Business Server 的资源林必须信任包含将访问它的用户帐户的每个帐户林。 如果有多个用户林，若要启用跨林身份验证，请务必为每个林信任启用名称后缀路由。 有关说明，请参阅[管理林信任](https://technet.microsoft.com/library/cc772440.aspx)。 如果您在另一个林中部署了 Exchange 服务器，并且它为 Skype for Business 用户提供了功能，则承载 Exchange 的林必须信任托管 Skype for Business Server 的林。 例如，如果 Exchange 已部署在帐户林中，这将有效地表示在该配置中需要帐户和 Skype for business 林之间的双向信任。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>将帐户同步到托管 Skype for Business 的林中

当 Skype for Business Server 部署在一个林中（资源林），但向一个或多个其他林（帐户林）中的用户提供功能时，其他林中的用户必须在部署了 Skype for Business Server 的林中表示为禁用的用户对象。 需要部署和配置身份管理产品（如 Microsoft Identity Manager），以设置帐户林的用户并将其同步到部署 Skype for Business Server 的林中。 用户必须以被禁用的用户对象的形式托管 Skype for Business Server 的林中进行同步。 无法将用户同步为 Active Directory contact 对象，因为 Azure Active Directory Connect 不会将联系人正确同步到 Azure AD，以便与 Skype 一起使用。
  
无论任何多林配置如何，托管 Skype for Business Server 的林也可以为同一林中存在的任何已启用用户提供功能。
  
若要获取正确的标识同步，需要同步以下属性： 
  
|**用户林**|**资源林**|
|:-----|:-----|
|选择的帐户链接属性  <br/> |选择的帐户链接属性  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[选择的帐户链接属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)将用作源定位点。 如果您希望使用不同且不可变的属性，则可以执行此操作;只需确保编辑 AD FS 声明规则并在 AAD 连接配置过程中选择属性。
  
请勿在林之间同步 Upn。 我们在测试过程中发现，我们需要对每个用户林使用唯一的 UPN，因为不能在多个林之间使用同一 UPN。 因此，我们提供了两种可能性，即同步 UPN 或不同步。 
  
- 如果每个用户林中的唯一 UPN 未同步到资源林中的关联禁用对象，则首次登录（SSO）至少将被中断（假定用户选择了 "保存密码" 选项）。 在 Skype for Business 客户端中，我们假定 SIP/UPN 值相同。 由于此方案中的 SIP 地址为 user@company.com，但用户林中启用的对象的 UPN 实际上是 user@contoso.company.com，因此初始登录尝试将失败，并且系统会提示用户输入凭据。 在输入其正确/实际 UPN 时，身份验证请求将针对用户林中的域控制器完成，登录将成功。
    
- 如果每个用户林中的唯一 UPN 已同步到资源林中关联的禁用对象，则 AD FS 身份验证将失败。 匹配规则将在资源林中的对象上查找 UPN，该 UPN 已被禁用，无法用于身份验证。 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>创建 Microsoft 365 或 Office 365 组织

接下来，你将需要设置 Microsoft 365 或 Office 365 组织以用于你的部署。 有关详细信息，请参阅[Microsoft 云产品服务的订阅、许可证、帐户和租户](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。 
  
## <a name="configure-active-directory-federation-services"></a>配置 Active Directory 联合身份验证服务

拥有租户后，你将需要在每个用户林中配置 Active Directory 联合身份验证服务（AD FS）。 这假设您有每个林的唯一 SIP 和 SMTP 地址和用户主体名称（UPN）。 AD FS 是可选的，在此处用于获取单一登录（SSO）。 也支持使用密码同步的 DirSync，也可替代 AD FS 使用。 
  
仅测试具有匹配的 SIP/SMTP 和 Upn 的部署。 不具有匹配的 SIP/SMTP/Upn 可能会导致功能下降，例如 Exchange 集成和 SSO 问题。 
  
除非您对每个林中的用户使用唯一的 SIP/SMTP/UPN，否则您仍可以遇到 SSO 问题，而不考虑部署 AD FS 的位置： 
  
- 在每个用户林中部署了 AD FS 服务器场的资源/用户林之间的单向或双向信任，所有用户共享公用 SIP/SMTP 域，但对于每个用户林都具有唯一的 UPN。 
    
- 仅在资源林中部署了 AD FS 场的资源/用户林之间的双向信任，所有用户都共享公用 SIP/SMTP 域，但对于每个用户林为唯一的 UPN。 
    
通过在每个用户林中放置 AD FS 服务器场，并对每个林使用唯一的 SIP/SMTP/UPN，我们会解决这两个问题。 在身份验证尝试过程中，仅搜索特定用户林中的帐户并匹配这些帐户。 这将有助于提供更无缝的身份验证过程。 
  
这将是 Windows Server 2012 R2 AD FS 的标准部署，在继续之前，它应正常工作。 有关说明，请参阅 how [To INSTALL AD FS 2012 R2 For Microsoft 365 或 Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。 
  
部署后，您必须编辑声明规则以匹配之前选择的源定位点。 在 AD FS MMC 中，在 "信赖方信任" 下，右键单击 " **microsoft 365 Identity platform** " 或 " **Microsoft Office 365 标识平台**"，然后选择 "**编辑声明规则**"。 编辑第一个规则，然后将 ObjectSID 更改为**employeeNumber**。 
  
![多林编辑规则屏幕](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>配置 AAD Connect

在资源林拓扑中，需要将资源林和任何帐户林中的用户属性同步到 Azure AD 中。 执行此操作的最简单和建议的方法是让 Azure AD Connect 同步并合并已启用用户帐户和包含 Skype for Business 的林的*所有*林的用户标识。 有关详细信息，请参阅[为 Skype For business 和团队配置 AZURE AD Connect](configure-azure-ad-connect.md)。

请注意，AAD 连接不提供帐户和资源林之间的本地同步。 必须使用 Microsoft Identity Manager 或类似产品单独进行配置，如前文所述。
  
完成和 AAD 连接合并后，如果您查看元节中的对象，您应该会看到类似于以下的内容： 
  
![多林元节对象屏幕](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
绿色突出显示的属性已从 Microsoft 365 或 Office 365 合并，黄色来自用户林，蓝色来自资源林。 
  
这是一种测试用户，可以看到 AAD 连接已识别来自用户的 sourceAnchor 和 cloudSourceAnchor，以及 Microsoft 365 或 Office 365 中的资源林对象，在我们的1101示例中，这是之前选择的 employeeNumber。 然后，它能够将此对象合并到上面看到的内容中。 
  
有关详细信息，请参阅[将本地目录与 Azure Active Directory 集成](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)。 
  
应使用默认值安装 AAD Connect，但以下情况除外： 
  
1. 已部署和工作的单一登录（AD FS）：选择 "不**配置**"。
    
2. 连接目录：添加所有域。
    
3. 标识本地目录中的用户：选择**多个目录中存在的用户标识**，然后选择**ObjectSID**和**msExchangeMasterAccountSID**属性。
    
4. 在 Azure AD 中标识用户：源锚点：选择您在阅读[选择一个好的 sourceAnchor 属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)（用户主体名称- **userPrincipalName**）后选择的属性。
    
5.  可选功能：选择是否已部署 Exchange 混合。
    
    > [!NOTE]
    >  如果您仅拥有 Exchange Online，则在自动发现过程中可能存在由于 CNAME 重定向导致 OAuth 故障的问题。 若要更正此错误，您需要通过从 Skype for Business Server 命令行管理程序运行以下 cmdlet 来设置 Exchange 自动发现 URL：
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS 服务器场：选择 "**使用现有 Windows Server 2012 R2 AD fs 场**"，并输入 AD FS 服务器的名称。
    
7.  完成向导并执行必要的验证。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>为 Skype for Business Server 配置混合连接

遵循配置 Skype for Business 混合的最佳实践。 有关详细信息，请参阅[规划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>为 Exchange Server 配置混合连接

如有必要，请遵循配置 Exchange 混合的最佳实践。 有关详细信息，请参阅[Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)。 
  

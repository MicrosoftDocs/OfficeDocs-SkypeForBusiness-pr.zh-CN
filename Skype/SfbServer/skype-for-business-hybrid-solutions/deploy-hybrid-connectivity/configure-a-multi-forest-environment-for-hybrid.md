---
title: 配置多目录林环境中的混合业务的 Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: 以下各节提供有关如何配置为 Skype 提供业务功能的混合方案资源/用户目录林模型中的多个林的环境指导。
ms.openlocfilehash: ea2e650925dee8851419baca2a64d70585b19036
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>配置多目录林环境中的混合业务的 Skype
 
以下各节提供有关如何配置为 Skype 提供业务功能的混合方案资源/用户目录林模型中的多个林的环境指导。 
  
![适用于混合部署的多林环境](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>验证林拓扑

支持多个用户林。注意以下几项： 
  
- 对于单个用户目录林或多用户目录林部署中，必须有 Skype 业务服务器的单个部署。
    
- 在混合配置 Lync Server 和 Skype 业务服务器的受支持版本，请参阅在[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)[拓扑要求](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology)。
    
- 可以在其中可能包含或不包含的林 Skype 业务服务器的一个或多个目录林中部署 Exchange Server。 确保您应用了最新的累积更新。
    
- 有关 Exchange Server 与共存的详细信息，包括支持条件和限制的各种组合的内部部署和联机，请参阅[计划集成 Skype 业务和交换](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[支持的功能](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。
    
有关详细信息，请参阅[有关业务服务器 2015年的 Skype 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
## <a name="user-homing-considerations"></a>用户驻留注意事项

Skype 为业务用户驻留在本地上可以有交换穴内部部署或联机。 Skype 的在线业务的用户应使用 Exchange Online 获得最佳的体验;但是，这不是必需的。 在部署 Exchange 不需要在任一情况下实现业务的 Skype。
  
## <a name="configure-forest-trusts"></a>配置林信任

所需的信任是资源林与每个用户林之间的双向可传递信任。 如果您有多个用户林，则要启用跨林身份验证，必须为这些林中的每个林启用名称前缀路由。 有关说明，请参阅[管理林信任](https://technet.microsoft.com/en-us/library/cc772440.aspx)。 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>同步到承载业务的 Skype 林中的帐户

当 Skype 的业务服务器被部署在一个目录林 （资源目录林），但提供的功能到一个或多个其他目录林中的用户 （帐户目录林） 时，必须为目录林中的被禁用的用户对象代表其他目录林中的用户的 Skype 的企业服务器被部署。 标识管理产品，如 Microsoft 标识管理器需要部署和配置设置和同步到该目录林中部署 Skype 业务服务器的位置的帐户目录林中的用户。 用户必须到林中为已禁用的用户对象的业务服务器承载 Skype 进行同步。 用户无法同步为 Active Directory 联系对象，因为 Azure 活动目录连接将不正确地同步联系人到 Azure 用于与 Skype 的广告。
  
任何多目录林配置，无论业务服务器承载 Skype 林还可以位于同一个目录林中任何已启用用户提供功能。
  
若要获得正确的身份同步，需要同步下列属性： 
  
|**用户的目录林**|**资源目录林**|
|:-----|:-----|
|选择的帐户链接属性  <br/> |选择的帐户链接属性  <br/> |
|邮件   <br/> |邮件   <br/> |
|代理地址  <br/> |代理地址  <br/> |
|ObjectSID  <br/> |msRTCSIP OriginatorSID  <br/> |
   
[选择帐户链接属性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)将用作源定位。 如果你有偏好使用的不同且不变的属性，则可以这样做，只是务必要编辑 AD FS 声明规则并在 AAD Connect 配置期间选择该属性。
  
不同步在目录林之间的 UPN。 在测试期间，我们发现我们需要将唯一的 UPN 用于每个用户林，因为不能在多个林中使用相同的 UPN。 因此，出现了两种可能性：同步 UPN 或不同步。 
  
-  如果未将每个用户林中的唯一 UPN 与资源林中相关联的已禁用对象同步，至少会针对初始登录尝试中断单一登录（假设用户选择了保持密码的选项）。在 SfB 客户端中，我们假设 SIP/UPN 值相同。由于在此情况下 SIP 地址是 user@company.com，但用户林中已启用对象的 UPN 实际上是 user@contoso.company.com，初始登录尝试将会失败，并且系统将提示用户输入凭锯。在输入正确/实际 UPN 时，将会针对用户林中的域控制器完成身份验证请求，并且登录将会成功。
    
- 如果使每个用户林中的唯一 UPN 与资源林中相关联的已禁用对象同步，则 AD FS 身份验证将会失败。匹配的规则可找到资源林中对象的 UPN，但该 UPN 处于禁用状态，无法用于身份验证。 
    
## <a name="create-an-office-365-tenant"></a>创建 Office 365 租户

接下来需要设置要用于部署的 Office 365 租户。 有关详细信息，请参阅[Office 365 提供步骤](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx)。 
  
## <a name="configure-ad-fs"></a>配置 AD FS

具有租户之后，接着需要在每个用户林中配置 Active Directory 联合身份验证服务 (AD FS)。这假设您具有每个林的唯一 SIP 及 SMTP 地址和用户主体名称 (UPN)。AD FS 是可选的，在此处用来获取单一登录。DirSync with Password Sync 也受支持，并且还可以替代 AD FS 使用。 
  
只会测试具有匹配的 SIP/SMTP 和 UPN 的部署。不具有匹配的 SIP/SMTP/UPN 可能导致缩减功能，例如 Exchange 集成和单一登入有问题。 
  
除非您为每个目录林的用户使用唯一的 SIP/SMTP/UPN，您仍然可以运行到单一登录 (SSO) 问题-而不考虑部署 AD FS 的位置： 
  
- 对于在每个用户林中部署了 AD FS 服务器场的资源/用户林之间的单向或双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。 
    
- 对于仅在资源林中部署了 AD FS 服务器场的资源/用户林之间的双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。 
    
通过在每个用户林中放置 AD FS 服务器场并将唯一的 SIP/SMTP/UPN 用于每个林，我们解决了这两个问题。在身份验证期间，将只搜索并匹配特定用户林中的帐户。这将有助于提供更无缝的身份验证流程。 
  
这将是 Windows Server 2012 R2 AD FS 的标准部署，应处于正常工作状态才能继续。 有关说明，请参阅[如何安装 Office 365 的 AD FS 2012 R2](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。 
  
部署之后，您必须编辑声明规则以与先前选择的“来源作者”相匹配。在 AD FS MMC 中，在“依赖方信任”下，右键单击 Microsoft Office 365 身份平台，然后单击“编辑声明规则”。编辑第一个规则并将 ObjectSID 更改为 employeeNumber。 
  
![多林编辑规则屏幕](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>配置 AAD Connect

AAD Connect 将用于在不同林之间以及不同林与 Office 365 之间合并帐户。您应该在资源林中部署 AAD Connect。必须能够在多个林与 Office 365 之间同步，Dirsync 不支持此操作。 
  
AAD Connect 不会在内部部署林之间同步帐户。它使用 AD 连接来读取已在内部部署林之间同步的对象（通过 FIM 或类似产品）。然后，它利用筛选规则创建其元节中相匹配的已启用和已禁用对象的单一表示，然后将该单一已合并对象复制到 Office 365 中。 
  
完成之后并且 AAD Connect 正在合并时，如果您查看元节中的对象，应该看到类似如下的内容： 
  
![多林元节对象屏幕](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
已从 Office 365 中合并绿色突出显示的属性，黄色来自用户林，蓝色来自资源林。 
  
这是一个测试用户，您可以看到 AAD Connect 已识别用户和资源林对象及 Office 365 中的 sourceAnchor 和 cloudSourceAnchor，在我们的案例 1101 中，是先前选择的 employeeNumber。然后，系统能够将此对象合并到您在上方看到的内容中。 
  
有关详细信息，请参阅[集成内部标识使用 Azure 活动目录](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)。 
  
应使用大部分默认值安装 AAD Connect。以下步骤例外： 
  
1.  单一登录-与 AD FS 已部署并正在运行，选择未配置
    
2. 连接您的目录-添加的所有域 
    
3.  识别内部目录中的用户：**用户身份存在跨多个目录**中选择，然后选择**ObjectSID**和**msExchangeMasterAccountSID**属性
    
4. 在 Azure AD 中标识用户： 源定位-选择您选择阅读[选择好的 sourceAnchor 特性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)后的特性、 用户主体名称的**范围内**
    
5.  可选功能的选择是否有交换混合部署。
    
    > [!NOTE]
    >  如果您只有 Exchange Online，则在自动发现期间，可能会因为 CNAME 重定向而出现 OAuth 失败问题。 若要解决此问题，您需要从 Skype 业务服务器管理外壳程序运行以下 cmdlet 来设置 Exchange 自动发现 URL:
  
    一组 CsOAuthConfiguration ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS 服务器场：选择**使用现有 Windows Server 2012 R2 AD FS 服务器场**并输入 AD FS 服务器的名称。
    
7.  完成向导并执行必要的验证。
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>为 Skype for Business Server 配置混合模式

按照有关业务混合配置 Skype 的最佳做法。 计划的详细信息，请参阅[规划业务服务器 2015年的 Skype 的混合部署](https://technet.microsoft.com/en-us/library/jj205403.aspx)，和配置信息，请参阅[配置混合使用 Skype 的在线业务](https://technet.microsoft.com/en-us/library/jj204669.aspx)。 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>为 Exchange Server 配置混合模式

如有必要，遵循配置 Exchange 混合部署的最佳做法操作。 有关详细信息，请参阅[Exchange Server 混合部署](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx)。 
  


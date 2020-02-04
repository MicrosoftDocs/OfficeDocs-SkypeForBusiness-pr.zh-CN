---
title: Skype for Business Server 2015 的环境要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要：配置 Skype for business Server 2015 的非服务器要求。 在部署之前，您需要配置各种内容，包括 Active Directory、DNS、证书和 Fileshares。
ms.openlocfilehash: 60244391a04b1bab31464bd0ef0b804510e40955
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41678956"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**摘要：** 配置 Skype for business Server 2015 的非服务器要求。 在部署之前，您需要配置各种内容，包括 Active Directory、DNS、证书和 Fileshares。
  
Skype for business Server 2015 的环境要求是什么？ 我们已将不直接与服务器相关的所有内容放入本主题，因此不必再点击一下。 如果您要查找服务器必备条件，您可以查看[Skype for Business server 2015 文档的服务器要求](server-requirements.md)。还会单独记录[网络规划](../../plan-your-deployment/network-requirements/network-requirements.md)。 否则，这就是我们在本文中所获得的内容：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [域名系统 (DNS)](environmental-requirements.md#DNS)
  
- [证书](environmental-requirements.md#Certs)
  
- [文件共享](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

虽然服务器和服务的大量配置数据存储在 Skype for business Server 2015 的中央管理存储中，但仍有一些内容存储在 Active Directory 中：
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||Lync Server 2013 和 Lync Server 2010 的扩展可保持与以前支持的版本的向后兼容性。  <br/> |
|Data  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||应用程序的联系人对象（如 "响应组" 应用程序和 "会议助理" 应用程序）。  <br/> |
||为实现向后兼容而发布的数据。  <br/> |
||中央管理存储的服务控制点（SCP）。  <br/> |
||Kerberos 身份验证帐户（可选计算机对象）。  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可以使用哪些域控制器操作系统？列表如下：

- Windows Server 2019 （您必须安装 Skype for Business Server 2015 累积更新5或更高版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
现在，你将 Skype for business Server 2015 部署到的任何域的域功能级别以及你将 Skype for business Server 2015 部署到的任何林的林功能级别必须是以下各项之一：

- Windows Server 2019 （您必须安装 Skype for Business Server 2015 累积更新5或更高版本）
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
这些环境中能否有只读域控制器？ 当然可以，只要另外有可写入的域控制器即可。
  
现在，知道 Skype for business Server 2015 不支持单标记的域，这一点很重要。 单标签域是什么？ 如果一个根域带有 contoso.local 标签，那么不会有任何问题。 而如果一个根域直接命名为 local，则无法工作，也就是说不支持这种命名方式。 [知识库中的这篇文章](https://support.microsoft.com/kb/300684/en-us)略为详细地介绍了相关内容。
  
Skype for Business Server 2015 也不支持重命名域。 如果你确实要执行此操作，则需要卸载 Skype for business Server 2015，请执行域重命名，然后重新安装 Skype for business Server 2015。
  
最后，你可能正在使用锁定的 AD DS 环境处理域，这完全正确。 有关如何在部署文档中将 Skype for business Server 2015 部署到此类环境中的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype for Business Server 2015 支持的拓扑包括：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 具有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们有一些图表和说明，可帮助你确定你的环境中所拥有的拓扑，或者在安装 Skype for Business Server 2015 之前可能需要安装哪些内容。 为简单起见，我们还提供了密钥：
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![具有单个域的 Active Directory 单林图表](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不会比此更容易，它是单个域林，这是一个常见拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 因此，在其中创建用户的域可能不同于将 Skype for business Server 2015 部署到的域。 为什么要考虑这一点？ 请牢记，在部署 Skype for Business Server 前端池时，池中的所有服务器都必须位于单个域中。 你可以通过 Skype for Business 服务器对 Windows 通用管理员组的支持进行跨域管理。
  
返回到上图，你可以看到一个域中的用户可以从同一域或不同域访问 Skype for Business 服务器池，即使这些用户位于子域中也是如此。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
可能是你有一个类似于此图表的拓扑，其中有一个林，但在该林内是多个域，具有单独的广告命名空间。 如果是这种情况，此图是一个很好的说明，因为我们的用户在访问 Skype for Business Server 2015 的三个不同域中。 实线指示他们正在访问其自己的域中的 Skype for business 服务器池，而虚线指示他们将转到其他树中的池。
  
可以看到，相同域、相同树甚至不同树中的用户都能成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 支持在中央林拓扑中配置的多个林。 如果你不确定自己的拓扑结构，请注意拓扑中的中央林使用自身内部的对象表示其他林中的用户，并承载此林中任意用户的用户帐户。
  
其工作方式如何？ 嗯，目录同步产品（如 Forefront Identity Manager 或 FIM）在其现有范围内管理你的组织的用户帐户。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
很明显，如果你的广告基础结构就地迁移到此拓扑可能不是很简单，但是如果你已经存在，或者仍在规划林基础结构，则这可能是一个不错的选择。 你可以将 Skype for Business Server 2015 部署集中在单个林中，用户可以搜索、通信和查看任何林中的其他用户的状态。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
还支持资源林拓扑;林专用于运行服务器应用程序的位置，如 Microsoft Exchange Server 和 Skype for business Server 2015。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意，ExchangeServer 可以部署在与 Skype for Business Server 相同的资源林中，也可以部署在不同的林中。
  
若要在此类型的拓扑中部署 Skype for Business Server 2015，你可以在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象（如果 Microsoft Exchange Server 已在环境中，可能会为你完成此操作）。 然后，你将需要一个目录同步工具（如 Forefront Identity Manager 或 FIM），以便通过其生命周期管理用户帐户。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](environmental-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在该拓扑中，存在一个或多个用户林，且 Skype for Business Server 部署在专用资源林中。 Exchange Server 可以部署在本地的相同资源林中，也可以部署在不同资源林中，且可配置为与 Exchange Online 混合使用，或者可以由 Exchange Online 专门为本地帐户提供电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>具有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 组织还有 Office 365，并使用 [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) 将其本地帐户与 Office 365 同步。 启用了 Skype for Business 的用户通过 Office 365 和 Skype for Business Online 启用。 Skype for Business Server 不部署在本地。
  
单一登录身份验证由位于用户林中的 Active Directory 联合身份验证服务场提供。
  
在此方案中，支持部署本地 Exchange、Exchange Online 或 Exchange 混合解决方案，或者根本不部署 Exchange。 （图中只显示了本地 Exchange，但是也完全支持其他 Exchange 解决方案。）
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在该方案中，存在一个或多个本地用户林，Skype for Business 部署在专用资源林中并配置为用于与 Skype for Business Online 的混合模式。 Exchange Server 可以部署在本地的相同资源林中，也可以部署在不同资源林中，且可配置为与 Exchange Online 混合使用。 或者可以由 Exchange Online 专门为本地帐户提供电子邮件服务。
  
有关详细信息，请参阅[配置适用于混合 Skype for Business 的多林环境](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype for business 服务器2015需要 DNS，原因如下：
  
- DNS 使 Skype for business Server 2015 能够发现内部服务器或池，从而实现服务器到服务器的通信。
    
- DNS 使客户端机器可以发现用于 SIP 事务的前端池或标准版服务器。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端机器连接至用于即时消息 (IM) 或会议的边缘服务器或 HTTP 反向代理。
    
- 它使未登录的统一通信 (UC) 设备可以发现运行设备更新 Web 服务的前端池或标准版服务器，以获取更新和发送日志。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- DNS 还用于 DNS 负载平衡。
    
请务必注意，Skype for business 服务器2015不支持国际化域名（IDNs）。
  
这一点非常重要，请记住，DNS 中的任何名称与 Skype for business Server 2015 使用的任何服务器上配置的计算机名称相同。 具体来说，不能在这种环境中使用短名称，必须为拓扑生成器使用 FQDN。
  
尽管使用 FQDN 似乎是已加入域的计算机的合理做法，但如果有尚未加入域的边缘服务器，那么它就可能使用默认的短名称，无域后缀。 请确保在 DNS 或边缘服务器上，或在此情况下的任何 Skype for business Server 2015 服务器或池中都不是这种情况。
  
且绝对不要使用 Unicode 字符或下划线。 标准字符（Z、A-z、0-9 和连字符）是要由外部 DNS 和公共证书颁发机构支持的字符（需要为证书中的 SN 分配 Fqdn，别忘了），因此，如果需要，您将有大量 grief。请注意您的姓名。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，你要做的一件最重要的事情就是确保证书有条不紊。 Skype for Business Server 2015 需要用于传输层安全（TLS）和相互传输层安全性（MTLS）连接的公钥基础结构（PKI）。 基本上，为了以标准化的方式进行通信，Skype for Business Server 会使用证书颁发机构 (CA) 颁发的证书。
  
以下是 Skype for Business Server 2015 使用证书的一些内容：
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 Web 应用程序和 Outlook Web Access (OWA) 通信
    
因此，证书计划必须具备。 现在，我们来看看在请求证书时需要牢记的一些事情：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype for Business Server 2015 支持 SHA-1 和 SHA-1 系列的摘要大小（224、256、384和512），并且满足或超过操作系统要求。
    
- 对于运行 Skype for Business Server 2015 的内部服务器，自动注册受支持。
    
- Skype for business Server 2015 Edge 服务器不支持自动注册。
    
- 将基于 web 的证书请求提交到 Windows Server 2003 CA 时，必须从运行 Windows Server 2003 的计算机或 Windows XP 提交该证书请求。
    
> [!NOTE]
> 虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。 
  
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 

> [!NOTE]
> Skype for Business 服务器2015不支持 CNG 证书。
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
因此，我们需要考虑许多更舒适的级别，并向 CA 申请证书。 我们将在下方给出进一步的指南，帮助你尽可能轻松地进行规划。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

你将需要大多数内部服务器的证书，并且很可能会收到来自内部 CA （位于你的域中的 CA）的证书。 如果愿意，你可以从外部 CA（位于互联网上）请求这些证书。 如果你不确定要向哪个公共 CA 请求证书，可以查阅[统一通信证书合作伙伴](/SkypeForBusiness/certification/services-ssl)列表。
  
当 Skype for Business Server 2015 与其他应用程序和服务器（如 Microsoft Exchange Server）通信时，你还将需要证书。 显然，这必须是其他这些应用程序与服务器能够以受支持的方式使用的证书。 Skype for Business Server 2015 和其他 Microsoft 产品支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。 如果你对此感兴趣，我们将为 OAuth 和 Skype for business Server 2015 添加一个计划文章。
  
Skype for Business Server 2015 还包括对（不需要）使用 SHA-256 加密哈希函数签名的证书的支持。 要支持使用 SHA-256 进行外部访问，外部证书需要由公共 CA 使用 SHA-256 颁发。
  
为了尽量简单地尝试操作，我们已将标准版服务器、前端池和其他角色的证书要求添加到下表中，使用虚构的 contoso.com 用于示例（你可能会使用某些内容）适用于你的环境的其他情况）。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 根据下方的示例名称，如果你已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将其加入证书的“使用者替代名称 (SAN)”中。
    
标准版服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|**批注**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |在标准版服务器标准版服务器上，服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 相同）  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com  <br/> |你无法在拓扑生成器中覆盖内部 Web FQDN。  <br/> 如果您有多个会议简单 URL，则必须将其全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 拨入简单 URL  <br/> • 每个 SIP 域的会议简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |如果你有多个匹配简单的 Url，则必须将所有这些 Url 包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
前端池中前端服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|**批注**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 不同）  <br/> • 服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com  <br/> |如果你有多个匹配简单的 Url，则必须将所有这些 Url 包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |如果你有多个匹配简单的 Url，则必须将所有这些 Url 包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |控制器的 FQDN 和控制器池的 FQDN。  <br/> 如果此池是客户端的自动登录服务器以及组策略中所需的严格 DNS 匹配，则你还需要 sipdomain （对于你拥有的每个 SIP 域）的条目。  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> 如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 每个 SIP 域的会议简单 URL  <br/> • 拨入简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |控制器外部 Web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com  <br/> |
   
独立中介服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable 分支装置的证书：
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |设备的 FQDN  <br/> |SIP.\<sipdomain\>（每个 SIP 域仅需要一个条目）  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>持久聊天服务器的证书

安装持久聊天服务器时，你将需要一个证书，该证书由您的 Skype for Business Server 2015 内部服务器使用的同一个 CA 颁发。 需要针对运行持久聊天 Web 服务的每台服务器执行文件上载/下载。 我们强烈建议你在开始永久聊天安装之前拥有所需的证书，并且如果你的 CA 是外部的，则甚至更多的是你的证书（这可能需要少许时间）。
  
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype for Business Server 2015 支持使用**单个公共证书**访问和网络会议边缘外部接口，以及 a/V 身份验证服务，该服务均通过 Edge 服务器提供。 边缘内部接口通常使用内部 CA 颁发的专用证书，但如果愿意，也可以使用受信任的 CA 颁发的公共证书。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果你在部署移动功能并需要支持移动客户端的自动发现，则需要在证书上包含某些使用者替代名称条目，以支持来自移动客户端的安全连接。
  
不确定需要哪些证书？ 您需要在以下证书上包含 SAN 名称以支持自动发现：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
我们将在下表中列出具体细节。
  
现在，你可以在这里进行少量预规划，但有时你已部署了 Skype for Business Server 2015，而无需部署移动性，并且在你的环境中已有证书的情况下会出现。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果你在寻找这方面的信息，而且有大量的 SIP 域（导致添加 SAN 的成本更为高昂），你可以将反向代理配置为使用 HTTP 处理初始自动发现服务请求，而非使用 HTTPS（默认配置）。 移动规划主题提供了这方面的详细信息。
  
控制器池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
或者，你也可以使用 SAN=\*.\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 你的反向代理侦听器将具有适用于你的外部 Web 服务 URL 的 SANs。 如果你已部署控制器（可选），部分示例包括 SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype for Business Server 2015 可以对所有文件存储使用相同的文件共享。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 有关 Windows Server 2012 的 DFS 的更多信息，请查看[此 DFS 页面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果你使用的是，则应群集 Windows Server 2012 或 Windows Server 2012 R2。 Windows Server 2008 R2 也是可接受的。 为什么要使用最新的 Windows？ 较旧的版本可能不具备启用所有功能的正确权限。 可以使用群集管理器创建文件共享，此[方法在群集项目上创建文件共享](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster)将帮助您了解这些详细信息。
    
> [!CAUTION] 
> 您应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 
  


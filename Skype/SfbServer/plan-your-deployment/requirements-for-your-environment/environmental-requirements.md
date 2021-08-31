---
title: 2015 年 Skype for Business Server 环境要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要：配置 2015 年 2 月Skype for Business Server要求。 执行部署之前，需要配置各种内容，包括 Active Directory、DNS、Certs 和文件共享。
ms.openlocfilehash: e27d854b2755a3d0d8613f12fb80342879faab26
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725951"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>2015 年 Skype for Business Server 环境要求
 
**摘要：** 配置 2015 年 Skype for Business Server非服务器要求。 执行部署之前，需要配置各种内容，包括 Active Directory、DNS、Certs 和文件共享。
  
2015 年 10 月Skype for Business Server要求是什么？ 我们已经将与服务器不直接相关的所有内容都放在本主题中，因此你不必执行太多单击操作。 如果要查找 Server Prerequisites，请查看[server requirements for Skype for Business Server 2015](server-requirements.md)文档。此外，还[](../../plan-your-deployment/network-requirements/network-requirements.md)单独记录了网络规划。 否则，这是我们在本文中介绍的：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [域名系统 (DNS)](environmental-requirements.md#DNS)
  
- [证书](environmental-requirements.md#Certs)
  
- [文件共享](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

尽管服务器和服务大量的配置数据存储在 Skype for Business Server 2015 的中央管理存储中，但 Active Directory 中仍存储有一些内容：
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||Lync Server 2013 和 Lync Server 2010 的扩展，用于保持与以前受支持的版本的向后兼容性。  <br/> |
|Data  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||应用程序的联系对象 (响应组应用程序和响应会议助理应用程序) 。  <br/> |
||为了向后兼容而发布的数据。  <br/> |
||中央管理存储 (SCP) 服务控制点。  <br/> |
||Kerberos 身份验证 帐户 (可选计算机对象) 。  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

那么，可以使用哪些域控制器操作系统？ 我们具有以下列表：

- WindowsServer 2019 (必须具有 2015 Skype for Business Server 2015 累积更新 5 或) 
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
现在，部署 Skype for Business Server 2015 的任何域的域功能级别以及部署 Skype for Business Server 2015 的任何林的林功能级别必须执行以下操作之一：

- WindowsServer 2019 (必须具有 2015 Skype for Business Server 2015 累积更新 5 或) 
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
这些环境中能否具有只读域控制器？ 当然可以，只要同一站点中还有可写入的域控制器Skype for Business Server。
  
现在，必须了解的是，Skype for Business Server 2015 不支持单标签域。 它们是什么？ 如果你有标记为 contoso.local 的根域，则没有问题。 如果你的根域只是名为 local，则不起作用，因此它不受支持。 有关此内容，本知识库文章 [进行了进一些介绍](https://support.microsoft.com/kb/300684/en-us)。
  
Skype for Business Server 2015 也不支持重命名域。 如果确实需要这样做，则需要卸载 Skype for Business Server 2015、重命名域，然后重新安装 Skype for Business Server 2015。
  
最后，你可能正在处理具有锁定的 AD DS 环境的域，这一切都对。 我们在部署文档提供有关如何将 Skype for Business Server 2015 部署到此类环境中的信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype for Business Server 2015 支持的拓扑包括：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 资源林拓扑中的Skype for Business林拓扑中具有多个Exchange Online
    
- 资源林拓扑中的多个林，Skype for Business Online 和 Azure Active Directory 连接
    
我们提供了图表和说明，可帮助您确定您的环境中具有的拓扑，或在安装 2015 年 2 月 2015 之前可能需要设置Skype for Business Server拓扑。 为简单一点，我们还包括一个密钥：
  
![是用于拓扑图的图标Skype for Business键。](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![包含单个域的 Active Directory 单林关系图。](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
这一点并不简单，它是一个域林，这是一种常见拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多组域图。](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图同样显示一个林，但它也有一个或多个子域 (此特定示例中有三个子) 。 因此，在 中创建用户的域可能不同于部署 2015 Skype for Business Server域。 为什么担心这一点？ 请记住，在部署前端Skype for Business Server时，该池中的所有服务器都需要位于单个域中。 可以通过通用管理员组Skype for Business Server跨域Windows管理。
  
返回到上图，可以看到一个域中的用户可以从同一个域或不同域访问 Skype for Business Server 池，即使这些用户位于子域中。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单个林、多个树和脱节命名空间图。](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
可能是您具有类似于此图的拓扑，其中您具有一个林，但该林中有多个域，具有单独的 AD 命名空间。 如果是这样，此图就是一个很好的说明，因为我们有三个不同的域中的用户访问 Skype for Business Server 2015。 实线表示他们访问Skype for Business Server域中的池，虚线表示他们一起进入不同树中的池。
  
可以看到，同一域、同一树甚至不同树中的用户都可以成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑图中的多个林。](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 支持在中央林拓扑中配置的多个林。 如果您不确定自己拥有什么，拓扑中的中央林将使用其中的对象来表示其他林中的用户，并承载林中任何用户的用户帐户。
  
这如何工作？ 目录同步产品（ (Forefront Identity Manager 或 FIM）) 管理组织的用户帐户。 在林中创建或删除帐户时，该更改将同步到中央林中的相应联系人。
  
很明显，如果 AD 基础结构就地迁移到此拓扑可能不是那么容易，但如果已经位于该拓扑中，或者仍在规划林基础结构，这可能是一个不错的选择。 您可以将 2015 Skype for Business Server集中到单个林中，同时用户可以搜索、沟通和查看任何林中其他用户的存在。 使用同步软件自动处理所有用户联系人更新。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>资源林拓扑中的Skype for Business林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图中的多个林。](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
还支持资源林拓扑;林专用于运行服务器应用程序，如 Microsoft Exchange Server 和 Skype for Business Server 2015。 此资源林还承载活动用户对象的同步表示形式，但没有启用登录的用户帐户。 因此，资源林是用户对象所在的其他林的共享服务环境，并且它们与资源林具有林级信任关系。
  
请注意，Exchange Server可以部署在同一资源林中，Skype for Business Server部署在不同的林中。
  
若要在此类型的拓扑中部署 Skype for Business Server 2015，可以在资源林中为用户林中的每个用户帐户创建一个已禁用的用户对象 (如果环境中已有 Microsoft Exchange Server，则此操作可能会为) 。 然后，你需要目录同步工具 (Forefront Identity Manager 或 FIM) 来管理用户帐户的生命周期。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>资源林拓扑中的Skype for Business林拓扑中具有多个Exchange Online
<a name="BKMK_multipleforestopology"> </a>

此拓扑类似于在资源林拓扑中的多个林Skype for Business[拓扑](environmental-requirements.md#BKMK_multipleforestopology)。
  
在此拓扑中，存在一个或多个用户林，Skype for Business Server专用资源林中部署此拓扑。 Exchange Server部署在同一资源林或不同林中，并配置为与 Exchange Online 混合，或者电子邮件服务可能由 Exchange Online 专门为本地帐户提供。 没有可用于此拓扑的图表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>资源林拓扑中的多个林，Skype for Business Online 和 Azure Active Directory 连接
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。 这两个林具有信任关系。 它们使用 Azure AD Microsoft 365 Office 365或 连接。 所有用户均可以通过 Skype for Business 或 Microsoft 365 Office 365。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，本地有多个林，具有一个资源林拓扑。 Active Directory 林之间具有完全信任关系。 Azure Active Directory 连接工具用于在内部部署用户林和本地用户林之间Microsoft 365或Office 365。
  
 组织还具有 Microsoft 365 或 Office 365，并使用 Azure Active Directory 连接 将其[](/previous-versions/azure/azure-services/dn832695(v=azure.100))本地帐户与 Microsoft 365 或 Office 365。 启用此功能的用户Skype for Business通过 Microsoft 365 或 Office 365 Skype for Business Online。 Skype for Business Server本地部署。
  
单一登录身份验证由位于用户林中的 Active Directory 联合身份验证服务服务器场提供。
  
在此方案中，支持在本地部署Exchange、Exchange Online混合 Exchange 解决方案，或者完全Exchange部署。  (该图Exchange本地部署，但其他Exchange解决方案也完全受支持。) 
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>具有混合部署的资源林拓扑中的多个Skype for Business
<a name="BKMK_multipleforestopology"> </a>

在此方案中，存在一个或多个本地用户林，Skype for Business部署在专用资源林中，并配置为使用 Skype for Business Online 的混合模式。 Exchange Server可本地部署在同一资源林或不同林中，并可以配置为与 Exchange Online。 或者，电子邮件服务可能由本地帐户Exchange Online专门提供。
  
有关详细信息，请参阅为混合部署配置多林[Skype for Business。](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 需要 DNS，原因如下：
  
- DNS 允许 Skype for Business Server 2015 发现内部服务器或池，从而允许服务器到服务器的通信。
    
- DNS 允许客户端计算机发现用于 SIP Standard Edition前端池或前端服务器。
    
- 它将会议的简单 URL 与承载这些会议的服务器关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器或 HTTP 反向代理，以便即时消息 (IM) 或会议。
    
- 它允许未登录 (UC) 设备的统一通信发现运行设备更新 Web 服务的前端池或 Standard Edition 服务器，以获取更新和发送日志。
    
- 使用 DNS，移动客户端可以自动发现 Web 服务资源，而无需用户手动输入其设备设置中的 URL。
    
- 它用于 DNS 负载平衡。
    
值得注意的是，2015 Skype for Business Server 2015 不支持通过 IDN (国际化) 。
  
请记住，DNS 中的任意名称与在 2015 年 2015 年 10 月使用的任何服务器上配置的计算机Skype for Business Server相同。 具体来说，环境中不能有任何短名称，并且必须具有用于拓扑生成器的 FQDN。
  
这看起来对于已加入域的任何计算机来说都符合逻辑，但如果边缘服务器未加入域，则其默认名称可能是短名称，没有域后缀。 对于这一点，请确保 DNS 或边缘服务器或任何 Skype for Business Server 2015 服务器或池中都未发生此情况。
  
绝对不要使用 Unicode 字符或下划线。 标准字符 (即 A-Z、a-z、0-9 和连字符) 是外部 DNS 和公共证书颁发机构支持的字符 (你需要将 FQDN 分配给证书中的 SN，不要忘记) ，因此，如果命名时牢记这一点，你可以免去许多麻烦。
  
有关网络 DNS 要求的进一步阅读，请查看 [我们的规划文档的](../../plan-your-deployment/network-requirements/network-requirements.md) 网络部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，可以执行最重要的操作之一是确保证书已按顺序排列。 Skype for Business Server 2015 年需要公钥基础结构 (PKI) ，用于传输层安全性 (TLS) MTLS (MTLS) 连接。 基本上，为了以标准化的方式安全地通信，Skype for Business Server证书颁发机构颁发的证书 (CA) 。
  
以下为 2015 Skype for Business Server使用证书的一些内容：
  
- 客户端和服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 OWA Outlook Web Access (Web 应用程序) 
    
因此，必须规划证书。 现在，我们来看看请求证书时需要记住的一些内容列表：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书都必须使用操作系统支持的签名算法进行签名。 Skype for Business Server 2015 支持摘要大小为 (224、256、384 和 512 位) 的 SHA-1 和 SHA-2 套件，并且满足或超过操作系统要求。
    
- 在 2015 年 10 月运行的内部服务器Skype for Business Server自动注册。
    
- 2015 边缘服务器不支持自动Skype for Business Server注册。
    
- 向 Windows Server 2003 CA 提交基于 Web 的证书请求时，必须在运行 Windows Server 2003 SP2 或 Windows XP 的计算机上进行提交。
    
> [!NOTE]
> 虽然 KB922706 为解决针对 Windows Server 2003 证书服务 Web 注册注册 Web 证书的问题提供支持，但无法使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。 
  
> [!NOTE]
> 不支持使用 RS UNSUPPORT-PSS 签名算法，并且可能导致登录和呼叫转发问题等错误。 

> [!NOTE]
> Skype for Business Server 2015 不支持 CNG 证书。
  
- 支持加密密钥长度为 1024、2048 和 4096。 建议使用密钥长度 2048 及更大。
    
- 默认摘要算法（即哈希签名）算法为 RSA。 还ECDH_P256、ECDH_P384和ECDH_P521算法。
    
因此，有很多值得思考的问题，当然，从 CA 请求证书时，有多种舒适级别。 我们将在下面为您提供一些进一步指导，尽可能使规划更加难用。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

大多数内部服务器都需要证书，很可能你会从位于域安全中心的内部 CA (获取证书) 。 如果需要，可以从位于 Internet (外部 CA 请求这些) 。 如果您想知道应转到哪一个公共 CA，请查看统一 [通信证书合作伙伴](../../../SfbPartnerCertification/certification/services-ssl.md) 列表。
  
当 Skype for Business Server 2015 与其他应用程序和服务器（如 Microsoft Exchange Server）通信时，您还需要证书。 显然，这应该是其他应用和服务器可以支持的方式使用的证书。 Skype for Business Server 2015 和其他 Microsoft 产品支持 Open Authorization (OAuth) 协议，用于服务器到服务器身份验证和授权。 如果你对此感兴趣，我们提供了另一篇有关 OAuth 和 Skype for Business Server 2015 的规划文章。
  
Skype for Business Server 2015 还包括对 (的支持，而无需) SHA-256 加密哈希函数签名的证书。 若要支持使用 SHA-256 进行外部访问，外部证书需要由公共 CA 使用 SHA-256 颁发。
  
为了尝试让事情变得简单，我们将 Standard Edition 服务器、前端池和其他角色的证书要求置于下表中，其中将虚拟 contoso.com 用于示例 (你可能会对环境) 使用其他内容。 这些证书都是标准 Web 服务器证书，具有不可导出的私钥。 还需要注意其他一些注意事项：
  
- 使用证书向导请求 (EKU) 将自动配置服务器增强型密钥用法。
    
- 每个证书友好名称在计算机存储中必须是唯一的。
    
- 根据下面的示例名称，如果你已在你的 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将它们添加到证书的"主题备用名称" (SAN) 。
    
用于服务器Standard Edition证书：
  
|**证书**|**主题名称/公用名**|**使用者替代名称**|**示例**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |对于 Standard Edition Server，服务器 FQDN 与池 FQDN 相同。  <br/> 该向导会检测在安装过程中指定的任何 SIP 域，并自动将它们添加为主题备用名称。  <br/> 您还可以使用此证书进行服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 相同)   <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN= \* .contoso.com  <br/> |无法替代拓扑生成器中的内部 Web FQDN。  <br/> 如果你有多个 Meet 简单 URL，你必须将它们全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 拨入简单 URL  <br/> • 每个 SIP 域的 Meet 简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |如果你有多个 Meet 简单 URL，你必须将它们全部包含为主题替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
前端池中前端服务器的Enterprise Edition证书：
  
|**证书**|**主题名称/公用名**|**使用者替代名称**|**示例**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。  <br/> 您还可以使用此证书进行服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 不同)   <br/> • 服务器 FQDN  <br/> • Skype for Business池 FQDN  <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN= \* .contoso.com  <br/> |如果你有多个 Meet 简单 URL，你必须将它们全部包含为主题替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |如果你有多个 Meet 简单 URL，你必须将它们全部包含为主题替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**主题名称/公用名**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |控制器的 FQDN，控制器池的 FQDN。  <br/> 如果此池是客户端的自动登录服务器，并且组策略要求执行严格的 DNS 匹配，则还需要为已登录的每个 SIP 域输入 sip.sipdomain () 。  <br/> |pool.contoso.com;SAN=dir01.contoso.com  <br/> 如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 相同)   <br/> • 服务器 FQDN  <br/> • Skype for Business池 FQDN  <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 每个 SIP 域的 Meet 简单 URL  <br/> • 拨入简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |控制器外部 Web FQDN 必须与前端池或前端服务器不同。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
独立中介服务器的证书：
  
|**证书**|**主题名称/公用名**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net;SAN=medsvr-pool.contoso.net;SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance 的证书：
  
|**证书**|**主题名称/公用名**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |设备的 FQDN  <br/> |SIP。\<sipdomain\>  (每个 SIP 域服务器只需要一个)   <br/> |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>持久聊天服务器的证书

安装持久聊天服务器时，您需要由与 Skype for Business Server 2015 内部服务器相同的 CA 颁发的证书。 需要为每台运行持久聊天 Web 服务（用于文件下载）的服务器Upload此操作。 强烈建议在开始安装持久聊天 (证书) 证书，如果 CA 是外部 CA，则更需要 (因此颁发这些证书可能需要一) 。
  
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问和边缘 (证书) 

Skype for Business Server 2015 支持将单个公共证书用于访问和 Web 会议边缘外部接口，以及 A/V 身份验证服务，该服务全部通过边缘服务器 (提供) 。 边缘内部接口通常使用内部 CA 颁发的专用证书，但如果愿意，也可以对此使用公共证书（如果证书来自受信任的 CA）。
  
反向代理 (RP) 也将使用公共证书，它使用 HTTP (（更精确地说，TLS over HTTP) ）加密从 RP 到客户端以及 RP 到内部服务器的通信。
  
### <a name="certificates-for-mobility"></a>移动证书

如果要部署移动功能并且支持移动客户端的自动发现，则需要在证书上添加一些其他主题替代名称条目，以支持来自移动客户端的安全连接。
  
哪些证书？ 你需要在此处的证书上自动发现 SAN 名称：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
我们将在下表中列出具体内容。
  
现在，这是一些预先规划良好的地方，但有时你已部署 Skype for Business Server 2015，不想部署移动功能，并且当你的环境中已有证书时，这一点会一直执行。 通过内部 CA 重新颁发证书通常非常简单，但使用公共 CA 颁发的公共证书，成本可能会稍高一些。
  
如果这是您正在寻找的内容，并且您有很多 SIP 域 (这会使添加 SAN 的成本更高) ，您可以将反向代理配置为将 HTTP 用于初始自动发现服务请求，而不是使用 HTTPS (这是默认配置) 。 规划移动功能主题对此有详细信息。
  
控制器池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN=lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
您也可以使用 SAN= \* 。\<sipdomain\>
  
反向代理 (公共 CA) 证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
此 SAN 需要分配给分配给反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 反向代理侦听器将具有外部 Web 服务 URL 的 SN， () 。 例如，SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com（如果已部署控制器， (可选) ）。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype for Business Server 2015 能够将同一文件共享用于所有文件存储。 您需要记住以下事项：
  
- 文件共享需要位于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，这包括分布式文件系统 (DFS) 以及用于文件存储的独立磁盘 (RAID) 的冗余阵列。 有关 DFS for Windows Server 2012，请查看[此 DFS 页面](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))。
    
- 我们建议文件共享使用共享群集。 如果你正在使用一个 R2，则应该Windows Server 2012或Windows Server 2012 R2。 Windows服务器 2008 R2 也是可接受的。 为什么使用最新Windows？ 旧版本可能没有启用所有功能所需的正确权限。 可以使用群集管理员创建文件共享，本如何在群集上创建文件共享一[](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster)文将帮助你了解这些详细信息。
    
> [!CAUTION] 
> 你应知道，不支持将网络 (NAS) 用作文件共享，因此请使用上面列出的选项之一。 

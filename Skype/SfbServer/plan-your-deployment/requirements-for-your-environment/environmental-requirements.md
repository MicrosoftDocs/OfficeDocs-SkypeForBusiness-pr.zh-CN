---
title: Skype for Business Server 2015 的环境要求
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要： 配置您的业务服务器 2015 Skype 为非服务器要求。 有许多您需要配置进行部署，其中包括 Active Directory、 DNS、 证书和 Fileshares 之前的事。
ms.openlocfilehash: 0d71140678654442caef112f6132695c76d3ea6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的环境要求
 
**摘要：**配置您的业务服务器 2015 Skype 为非服务器要求。 有许多您需要配置进行部署，其中包括 Active Directory、 DNS、 证书和 Fileshares 之前的事。
  
Skype 的业务服务器 2015年的环境要求是什么？ 嗯，我们已经将一切不直接相关到本主题中，因此您不必为以得在周围单击服务器。 如果您正在查找的服务器系统必备组件，您可以签出[业务服务器 2015年的 Skype 的服务要求](server-requirements.md)的单据[网络规划](../../plan-your-deployment/network-requirements/network-requirements.md)也有分别。 否则，这就是我们在这篇文章中已经有了：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [域名系统 (DNS)](environmental-requirements.md#DNS)
  
- [证书](environmental-requirements.md#Certs)
  
- [文件共享](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

虽然大量的服务器和服务的配置数据存储在 Skype 的业务服务器 2015年中央管理存储，有仍存储在 Active Directory 中的一些事项：
  
|**活动目录对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||Lync Server 2013 和 Lync Server 2010 中，以保持向后兼容以前的扩展受支持的版本。  <br/> |
|数据  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||应用程序 （如响应组应用程序的和会议助理应用程序的） 的的联系人对象。  <br/> |
||为实现向后兼容而发布的数据。  <br/> |
||服务控制点 (SCP) 的中央管理存储。  <br/> |
||Kerberos 身份验证帐户（可选计算机对象）。  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可以使用哪些域控制器操作系统？列表如下：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
现在，域功能级别的业务服务器 2015 到部署 Skype 任何域和林功能级别的业务服务器 2015 到部署 Skype 任何林必须为以下之一：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
这些环境中能否有只读域控制器？当然可以，只要另外有可写入的域控制器即可。
  
现在，是需要了解的业务服务器 2015 Skype 不支持单标记域。 单标签域是什么？ 如果您有一个标有 contoso.local 的根域，将会很好。 如果有一个刚刚被提名为本地的根域时，将不会工作，并不因此支持。 稍微对此已写入[此知识文库文章中](https://support.microsoft.com/kb/300684/en-us)。
  
商业服务器 2015年的 Skype 也不支持域的重命名。 如果真的有这样做，将需要卸载的业务服务器 2015，Skype 执行域重命名，然后再重新业务服务器 2015年安装 Skype。
  
最后，您可能会处理锁定的 AD DS 环境中，域并没关系。 我们有如何将 Skype 的业务服务器 2015年部署到这种环境中部署文档的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype 业务服务器 2015年受支持的拓扑包括：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们有图和描述，以帮助您确定哪种拓扑中具有您的环境中，或者您可能需要安装 Skype 业务服务器 2015年之前设置。 为了简单起见，我们在包括密钥：
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![支持的 SFB 与 MA 拓扑，仅限云。](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不会得到比这更简单，单一域林，这是一个常见的拓扑结构。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 因此用户所创建的域可能不同于域 Skype 的业务服务器 2015年部署到。 为什么要考虑这一点？ 请切记，当部署 Skype 业务前端服务器池，此池中的所有服务器都必须能够在单个域。 您可以跨域管理通过 Skype 业务服务器支持的 Windows 通用的管理员组。
  
回到上面的关系图，您可以看到，即使这些用户在子域中将是能够访问 Skype 业务服务器池从同一个域或不同的域，一个域中的用户。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
它可能是选中了一个拓扑类似于此图中，您拥有一个目录林，但在该林中的多个域，具有不同的 AD 命名空间。 如果真是这样，则此关系图的好图中，我们访问的业务服务器 2015年的 Skype 的三个不同的域中有用户。 实线表示他们正在访问 Skype 业务服务器池在其自己的域中，而虚线表示他们会到其他树池完全。
  
可以看到，相同域、相同树甚至不同树中的用户都能成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype 的业务服务器 2015年支持配置在中央林拓扑中的多个目录林。 如果您不确信这是您拥有什么，中央林拓扑中的使用对象在它来表示中林和主机目录林中的任何用户的用户帐户的用户。
  
工作原理是什么？ 好吧，（如前沿标识管理器或 FIM） 目录同步产品管理它们的存在在整个组织的用户帐户。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
显然，AD 架构是否适当地转向这种拓扑可能不是很容易，但如果你已经有，或仍计划自己的目录林基础结构，这可以是一个不错的选择。 虽然用户可以搜索、 交流和查看任何目录林中的其他用户的状态，您可以集中您的业务服务器 2015年部署单个林内，Skype。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
资源林拓扑，还支持;它是其中一个目录林专用于运行服务器应用程序，如 Microsoft Exchange Server 和业务服务器 2015年的 Skype。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意，可以在同一个林中资源 Skype 业务服务器或在不同的目录林中部署 Exchange Server。
  
为了部署 Skype 业务服务器 2015 这种拓扑中，您需要在资源目录林中的用户目录林中的每个用户帐户创建一个已禁用的用户对象 （如果 Microsoft Exchange Server 已在该环境中，这可能会为您）。 然后目录同步工具 （如前沿标识管理器或 FIM） 将需要管理其生命周期的用户帐户。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](environmental-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在此拓扑中，有一个或多个用户目录林和 Skype 业务服务器被部署在一个专用的资源目录林。 Exchange Server 可以部署的内部相同的资源目录林或不同树林中，并且配置为混合使用 Exchange Online，或可能以独占方式由 Exchange Online 内部帐户提供电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 该组织还具有 Office 365 并使用[Azure 活动目录连接](https://go.microsoft.com/fwlink/p/?LinkId=614836)与 Office 365 同步其内部帐户。 启用业务的 Skype 的用户启用通过 Office 365 和 Skype 在线业务。 Skype 业务服务器不在内部部署。
  
通过 Active Directory 联合身份验证服务场位于用户目录林提供了单一登录身份验证。
  
在这种情况下，支持部署 Exchange 内部，Exchange 在线混合交换解决方案，或者没有在所有部署的 Exchange。 （下面的图表显示只交换内部，但其他 Exchange 解决方案还完全支持）。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在此方案中，有一个或更多内部部署用户林和 Skype 的业务在一个专用的资源目录林部署和配置为混合模式与 Skype 的在线业务。 Exchange Server 可以部署的内部相同的资源目录林或不同树林中，并且可能配置为使用 Exchange Online 的混合。 或者，可能为本地帐户以独占方式由 Exchange 在线提供电子邮件服务。
  
有关详细信息，请参阅[配置多目录林环境中的混合业务的 Skype](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype 的业务服务器 2015年需要 DNS，原因如下：
  
- DNS 使 Skype 的业务服务器 2015 发现内部的服务器或池，以便服务器到服务器的通信。
    
- DNS 允许客户端计算机发现前端池或用于 SIP 事务的标准版服务器。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器，或者 HTTP 反向代理，为即时消息 (IM) 或会议。
    
- 它允许统一的通信 (UC) 没有登录的设备发现的前端池或设备的更新 web 服务来获取更新和发送日志运行的标准版服务器。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- DNS 还用于 DNS 负载平衡。
    
请务必注意业务服务器 2015年的 Skype 不支持国际化的域名 （idn，则）。
  
极其重要的要记住，任何在 DNS 中的名称是由业务服务器 2015 Skype 的任何服务器上配置的计算机名相同。 具体来说，我们在环境中，不能有任何的短名称，并且必须具有拓扑生成器的 Fqdn。
  
这看起来像是逻辑的任何一台计算机已经加入到域中，但如果您未加入到域边缘服务器，它可能有默认值为短的名称，与没有域后缀。 请确认这不是这样，在 DNS 中或在边缘服务器上或业务服务器 2015年服务器或池，就此而言任何 Skype 上。
  
并明确不使用 Unicode 字符或下划线。 标准的字符 （A-Z、 a-z、 0-9 和连字符） 是那些打算支持的外部 DNS 和公共证书颁发机构 (您将需要在证书中，SN 向指定 Fqdn 别忘了)，因此您将舍弃自己很多的麻烦如果记住名称与此。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，您要做的一件最重要的事情就是确保证书有条不紊。 Skype 的业务服务器 2015年需要公钥基础结构 (PKI) 的传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 连接。 从根本上说，要以标准化的方式安全地通讯，Skype 业务服务器使用由证书颁发机构 (Ca) 颁发的证书。
  
以下是一些有关业务服务器 2015 Skype 使用证书的用途的事情：
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 web 应用程序和 Outlook Web Access (OWA) 交谈
    
因此证书计划的必须。 现在，让我们看看一些需要在申请证书时，请记住的事情的列表：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype 的业务服务器 2015年支持 sha-1 和 SHA 2 套摘要大小 （224 256、 384、 512 位），并达到或超过操作系统的要求。
    
- 内部服务器运行 Skype 业务服务器 2015年支持自动注册。
    
- 自动注册不是支持 Skype 业务服务器 2015年边缘服务器。
    
- 提交到 Windows Server 2003 CA 的基于 web 的证书请求时，必须将其提交从运行任何 Windows Server 2003 SP2 或 Windows XP 的计算机。
    
> [!NOTE]
> 虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。 
  
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
因此，这是很多事情来考虑，并肯定，还有各种与从 CA 申请证书的舒适程度。 我们将提供您一些进一步的指导下进行规划过程中尽可能轻松。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

需要的证书为您的内部服务器的大多数，很可能会从内部 CA （它是一个在您的域中） 获取这些。 如果愿意，你可以从外部 CA（位于互联网上）请求这些证书。 如果您想知道哪些公共 CA 应该转到，可以将其检出的[统一通信证书的合作伙伴](https://support.microsoft.com/kb/929395/en-us)的列表。
  
也要与其他应用程序和服务器，如 Microsoft Exchange Server 通信业务服务器 2015年的 Skype 时需要证书。 显然，这必须是其他这些应用程序与服务器能够以受支持的方式使用的证书。 Skype 业务服务器 2015年和其他 Microsoft 产品支持打开授权 (OAuth) 协议进行服务器到服务器的身份验证和授权。 如果您有兴趣在此，我们有其他计划项目 OAuth 和 Skype 业务服务器 2015年。
  
Skype 的业务服务器 2015年还包括对支持 （不需要） 使用 sha-256 加密哈希函数签名的证书。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。
  
尝试并使事情保持简单，我们已经投入的证书要求的标准版服务器、 前端池和其他角色下, 表中，与所使用的示例 （您可能会使用一些虚构 contoso.com其他为您的环境）。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 按照下面的示例名称，如果您已在您的 DNS 配置 sipinternal.contoso.com 或 sipexternal.contoso.com 他们需要被添加到该证书的主题备用名称 (SAN)。
    
标准版服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**主题备用名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |在标准版服务器标准版服务器上，服务器 FQDN 等同于池的 FQDN。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是相同的服务器的 FQDN）  <br/> 和  <br/> • 满足简单的 Url  <br/> 拨入 • 简单的 URL  <br/> • 管理简单的 URL  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN =\*。 contoso.com  <br/> |不能重写内部 web 拓扑生成器中的 FQDN。  <br/> 如果您有多个会议简单 URL，则必须将其全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> 拨入 • 简单的 URL  <br/> • 满足每个 SIP 域的简单 Url  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个满足简单的 Url，您需要包括的主题备用名称为他们所有。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
在前端池前端服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**主题备用名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （它不是服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype 业务池的 FQDN 的  <br/> 和  <br/> • 满足简单的 Url  <br/> 拨入 • 简单的 URL  <br/> • 管理简单的 URL  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个满足简单的 Url，您需要包括的主题备用名称为他们所有。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> 拨入 • 简单的 URL  <br/> • 管理简单的 URL  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个满足简单的 Url，您需要包括的主题备用名称为他们所有。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**使用者名称/常用名称**|**主题备用名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认  <br/> |控制器池  <br/> |主任和主管池的 FQDN 的 FQDN。  <br/> 如果该池是客户端的自动登录服务器并在组策略中严格 DNS 匹配的需要，您也需要条目为 sip.sipdomain （对于您拥有每个 SIP 域）。  <br/> |pool.contoso.com;SAN=dir01.contoso.com  <br/> 如果此导演池是自动登录服务器为客户端和 DNS 匹配的严格要求在组策略中，您还需要 SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是相同的服务器的 FQDN）  <br/> • 服务器 FQDN  <br/> • Skype 业务池的 FQDN 的  <br/> 和  <br/> • 满足简单的 Url  <br/> 拨入 • 简单的 URL  <br/> • 管理简单的 URL  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN =\*。 contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> • 满足每个 SIP 域的简单 Url  <br/> 拨入 • 简单的 URL  <br/> 或者  <br/> • 为简单的 Url 通配符项  <br/> |主管外部 web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN =\*。 contoso.com  <br/> |
   
独立的中介服务器的证书：
  
|**证书**|**使用者名称/常用名称**|**主题备用名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN=medsvr01.contoso.net  <br/> |
   
高存活力的分支装置的证书：
  
|**证书**|**使用者名称/常用名称**|**主题备用名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认  <br/> |设备的 FQDN  <br/> |SIP。\<sipdomain\> （需要每个 SIP 域只有一个条目）  <br/> |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>持久聊天服务器的证书

安装您永久的聊天服务器时，您将需要与您 Skype 的业务服务器 2015年内部服务器使用相同的 ca 颁发的证书。 这需要为每个服务器运行持续聊天 Web 服务文件上载/下载完成。 我们强烈建议您在具有所需的证书开始持续聊天安装之前，如果您的 CA 是外部的甚至是更 （这些事情可能需要一些时间来颁发）。
  
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype 的业务服务器 2015年支持使用**单个公用证书**的访问和 web 会议边缘外部接口，再加上 A / V 身份验证服务，这提供通过边缘服务器。 您边内部接口通常会使用专用您内部 CA 颁发的证书，但如果您愿意，可用于公用证书这同样，如果它来自受信任的 CA。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果您部署的行动，便在移动客户端支持自动发现您将需要包括在您的证书，以支持移动客户端的安全连接上一些其他主题备用名称条目。
  
不确定需要哪些证书？您需要在以下证书上包含 SAN 名称以支持自动发现：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
我们将在下表中列出具体细节。
  
现在，这是其中一些预先计划很好，但有时您已经部署了 Skype 的业务服务器 2015年而不打算部署移动，和，提出推进时您的环境中已经有证书。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果这是您要查找的并且有大量的 SIP 域 （这会使添加更昂贵的 SAN），您可以配置您的反向代理服务器 HTTP 用于初始的自动发现服务请求，而不是使用 HTTPS （这是默认值配置）。 移动规划主题提供了这方面的详细信息。
  
导演池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
或者，您可以使用 SAN =\*。\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 反向代理侦听程序将为您的外部 Web 服务 URL(s) 具有 San。 一些示例为 SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com，如果您已经部署了主管，（这是可选的）。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype 的业务服务器 2015年就能够使用的所有文件存储相同的文件共享。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 进一步的阅读上 Windows Server 2012 的 DFS，检查出[此 DFS 页](https://technet.microsoft.com/en-us/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果您正在使用它，您应该群集 Windows Server 2012 或 Windows Server 2012 R2。 Windows Server 2008 R2 也是可以接受的。 为什么最新的 Windows？ 较旧的版本可能不具备启用所有功能的正确权限。 您可以使用群集管理器创建的共享文件，并[创建群集](https://support.microsoft.com/kb/284838)KB 文章将帮助您完成这些详细信息。
    
> [!CAUTION]
> 您应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 
  


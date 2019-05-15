---
title: Skype for Business Server 2015 的环境要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 摘要： 配置业务服务器 2015 Skype 非服务器的要求。 有很多还要执行您的部署，包括 Active Directory、 DNS、 证书和 Fileshares 之前配置您的内容。
ms.openlocfilehash: 71916081a9ea138d22f41fd4f2813834a74e941b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33909076"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**摘要：** 配置业务服务器 2015 Skype 的非服务器要求。 有很多还要执行您的部署，包括 Active Directory、 DNS、 证书和 Fileshares 之前配置您的内容。
  
什么是 Business Server 2015 的 Skype 环境要求？ 嗯，我们已将不直接相关到本主题中，因此不需要做为得多单击周围的服务器的所有内容。 如果您正在查找的服务器的先决条件，您可以签出[的业务服务器 2015年的 Skype 的服务器要求](server-requirements.md)单据[网络规划](../../plan-your-deployment/network-requirements/network-requirements.md)还介绍了单独。 否则，这是我们在本文中已经有了：
  
- [Active Directory](environmental-requirements.md#AD)
  
- [域名系统 (DNS)](environmental-requirements.md#DNS)
  
- [证书](environmental-requirements.md#Certs)
  
- [文件共享](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

虽然业务服务器 2015年中央管理存储大量的服务器和服务的配置数据存储在 Skype，有仍 Active Directory 中存储的事情：
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||支持的版本的 Lync Server 2013 和 Lync Server 2010，以保持与以前的向后兼容的扩展。  <br/> |
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
    
现在，业务服务器 2015 到，部署 Skype 任何域的域功能级别和 Skype 部署的 Business Server 2015 到，任何林中的林功能级别必须为下列选项之一：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
这些环境中能否有只读域控制器？ 当然可以，只要另外有可写入的域控制器即可。
  
现在，务必要了解的业务服务器 2015 Skype 不支持单标签域。 单标签域是什么？ 如果您有一个标有 contoso.local 的根域，这将为工作正常。 如果您有刚刚名为本地的根域，将不会工作，并因此不支持。 更多有关此已写入[此知识库文章中](https://support.microsoft.com/kb/300684/en-us)。
  
Skype 的业务服务器 2015年也不支持域的重命名。 如果您真正需要执行的操作，然后您将需要卸载 Skype 的业务服务器 2015年执行域重命名，然后重新安装 Skype 的业务服务器 2015年。
  
最后，您可能正在与使用锁定的 AD DS 环境中，域并没关系。 我们有如何部署到环境中部署文档的排序业务服务器 2015 Skype 的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype 业务服务器 2015年受支持的拓扑是：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们有图表和可帮助您确定哪些拓扑中具有您的环境，或者您可能需要安装业务服务器 2015 Skype 之前设置的说明。 为了简单起见，我们正在还包括键：
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![支持的 SFB 与 MA 拓扑，仅限云。](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不变得更简单比这、 它是单域林，这是常用的拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 使业务服务器 2015年部署到的域中创建用户可能不同域 Skype。 为什么要考虑这一点？ 请记住，当您部署业务 Server 前端池的 Skype 务必，该池中的所有服务器都必须能够在单个域。 您可以跨域管理通过 Skype Business Server 支持的 Windows 通用管理员组。
  
返回到上图中，您可以看到一个域中的用户能够访问 Skype 的业务服务器池从同一个域或从不同域中，即使子域中这些用户。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
它可能选中了拓扑类似于此图中，您有一个资源林中，但在该林中是使用单独的 AD 命名空间的多个域。 如果是这样，此图会的良好的图中，因为我们访问 Skype 的业务服务器 2015年的三个不同域中具有用户。 实线指示他们正在访问自己域中的业务服务器池的 Skype 而虚线表示它们完全转到不同树中的池。
  
可以看到，相同域、相同树甚至不同树中的用户都能成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype 的业务服务器 2015年并支持中央林拓扑中配置的多个林。 如果您不确定这是您拥有什么，中央林拓扑中的使用对象中来表示其他林中和承载任何用户林中的用户帐户中的用户。
  
工作原理是什么？ 嗯，目录同步产品 （如 Forefront Identity Manager 或 FIM） 管理它们存在整个组织的用户帐户。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
很显然，如果您的 AD 基础结构是就地移到此拓扑可能不是简单，但如果您已存在，或仍规划自己林中的基础结构，这可以是一个不错的选择。 用户可搜索、 通信，并查看任何林中其他用户的状态时，您可以集中用于在一个林中，业务服务器 2015年部署您 Skype。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
此外支持资源林拓扑中;是其中一个林专用于运行服务器应用程序，如 Microsoft Exchange Server 和 Skype 的业务服务器 2015年。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意，可以在同一个资源林中 Skype 业务服务器或不同的林中部署 Exchange 服务器。
  
若要部署在这种拓扑的业务服务器 2015 Skype，您将在资源林中的每个用户林中的用户帐户创建一个已禁用的用户对象 （如果 Microsoft Exchange Server 已在环境中，此操作可能会为您）。 然后您将需要目录同步工具 （如 Forefront Identity Manager 或 FIM） 可以管理其生命周期的用户帐户。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](environmental-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在此拓扑中，有一个或多个用户林和 Skype 业务服务器部署在专用的资源林中。 Exchange Server 可以是在本地部署中相同的资源林或另一个林和与 Exchange Online 的混合配置或可能为内部部署帐户以独占方式通过 Exchange Online 提供电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 组织还具有 Office 365，并使用[Azure Active Directory 连接](https://go.microsoft.com/fwlink/p/?LinkId=614836)将其内部部署帐户与 Office 365 同步。 为业务联机通过 Office 365 和 Skype 启用了用户启用了 for Business 的 Skype。 Skype 业务服务器不在本地部署。
  
由位于用户林的 Active Directory 联合身份验证服务服务器场提供单一登录身份验证。
  
在此方案中，支持部署 Exchange 内部部署，Exchange Online 混合 Exchange 解决方案，或没有根本部署的 Exchange。 （此图显示了仅 Exchange 内部部署，但还完全支持的其他 Exchange 解决方案）。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在此方案中，有一个或多个内部部署用户林中和 for Business 的 Skype 专用的资源林中部署配置为混合模式与 Skype 的业务联机。 Exchange Server 可以是在本地部署中相同的资源林或另一个林，并且可能与 Exchange Online 的混合配置。 此外，可能为内部部署帐户以独占方式通过 Exchange Online 提供电子邮件服务。
  
有关详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype 的业务服务器 2015年需要 DNS，原因如下：
  
- DNS 使 Skype 的业务服务器 2015 发现内部服务器或池，允许进行服务器到服务器通信。
    
- DNS 允许客户端可以发现的前端池或 Standard Edition server 所使用的 SIP 事务的计算机。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器，或 HTTP 反向代理，即时消息 (IM) 或会议。
    
- 这会让统一的通信 (UC) 未登录的设备发现的前端池或 Standard Edition 服务器正在运行设备更新 web 服务以获取更新和发送日志。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- DNS 还用于 DNS 负载平衡。
    
请务必注意业务服务器 2015年的 Skype 不支持国际化的域名 (Idn)。
  
极其重要记住，在 DNS 中的任何名称是与正在使用业务服务器 2015 Skype 任何服务器上配置的计算机名称相同。 具体而言，我们不能在环境中，有任何短名称，并且必须具有的拓扑生成器的 Fqdn。
  
这看起来像会逻辑的任何计算机已加入域，但是如果您有未加入您的域的边缘服务器，它可能具有默认值为短的名称，与任何域后缀。 请确保这不是这样，在 DNS 中或者对边缘服务器或任何 Skype 业务服务器 2015年服务器或池，该专家。
  
并不明确使用 Unicode 字符或下划线。 标准字符 （这是 A-Z、 a-z、 0-9 和连字符） 是要支持的外部 DNS 和公共证书颁发机构的那些 (您需要向证书中的 SN 分配 Fqdn 不要忘记)，因此您将空闲自己大量麻烦如果与此名称记住。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，您要做的一件最重要的事情就是确保证书有条不紊。 Skype 的业务服务器 2015年需要公钥基础结构 (PKI) 的传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 连接。 一般情况下，安全地标准化方式进行通信，Skype 业务服务器使用证书颁发机构 (Ca) 颁发的证书。
  
以下是一些业务服务器 2015年的 Skype 使用证书的事情：
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 谈话对方 web 应用程序和 Outlook Web Access (OWA)
    
因此，证书规划的必须。 现在，让我们看一下一些您需要申请证书时需要注意的事项列表：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype 的业务服务器 2015年支持 sha-1 和摘要式 160、SHA-2 套件大小 （224、 256、 384 和 512 位）、 和满足或超出的操作系统要求。
    
- 为业务服务器 2015年运行 Skype 的内部服务器支持自动注册。
    
- 自动注册不是支持 Skype 业务 Server 2015 边缘服务器。
    
- 提交到 Windows Server 2003 CA 的基于 web 的证书请求时，必须将其提交从运行 Windows Server 2003 SP2 或 Windows XP 的计算机。
    
> [!NOTE]
> 虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。 
  
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
因此，很多需要考虑的事项，并且肯定，没有各种舒适程度使用从 CA 请求证书。 我们将为您提供一些进一步的指导下进行规划尽可能轻松。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

所需证书的内部服务器，大多数和很可能将从内部 CA （它是一个位于您的域） 获取它们。 如果愿意，你可以从外部 CA（位于互联网上）请求这些证书。 如果您想知道哪些公共 CA 应转到，您可以将其签出[统一通信证书伙伴](https://support.microsoft.com/kb/929395/en-us)列表中。
  
您还将与其他应用程序和服务器，例如 Microsoft Exchange Server 通信的业务服务器 2015 Skype 时需要证书。 显然，这必须是其他这些应用程序与服务器能够以受支持的方式使用的证书。 Skype 业务服务器 2015年和其他 Microsoft 产品支持的服务器到服务器身份验证和授权 Open Authorization (OAuth) 协议。 如果您感兴趣这，我们将其他规划文章 OAuth 和 Skype 的业务服务器 2015年。
  
Skype 的业务服务器 2015年还包括对支持 （而无需） 使用 160、SHA 256 加密哈希函数签名的证书。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。
  
若要尝试并保持内容变得非常简单，我们已置于 Standard Edition server、 前端池和其他角色的证书要求下表中，使用虚构的 contoso.com 所使用的 （您可能要使用的内容的示例其他针对您的环境）。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 按照下面的示例名称，如果您在您的 DNS 配置 sipinternal.contoso.com 或 sipexternal.contoso.com 他们需要添加到证书的使用者替代名称 (SAN)。
    
对于 Standard Edition 服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |在 Standard Edition 服务器 Standard Edition server，服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是服务器的 FQDN 相同）  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN =\*。 contoso.com  <br/> |无法覆盖内部 web FQDN 在拓扑生成器。  <br/> 如果您有多个会议简单 URL，则必须将其全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> • 电话拨入式简单 URL  <br/> 每个 SIP 域的 • 会议简单 Url  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您就得到包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
在前端池前端服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这不是服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype 业务池 FQDN  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您就得到包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您就得到包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |控制器的 FQDN，控制器池的 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且严格的 DNS 匹配的组策略要求，您还需条目 sip.sipdomain （每个 SIP 域必须）。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> 如果此控制器池是客户端的自动登录服务器，并且严格的 DNS 匹配所需在组策略中，您还需要 SAN=sip.contoso.com;San = sip.fabrikam.com  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype 业务池 FQDN  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN =\*。 contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> 每个 SIP 域的 • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |控制器外部 web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN =\*。 contoso.com  <br/> |
   
独立的中介服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance 的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认  <br/> |设备的 FQDN  <br/> |SIP。\<sipdomain\> （需要每个 SIP 域只能有一个条目）  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>持久聊天服务器的证书

安装您持久聊天服务器时，您将需要与业务服务器 2015年内部服务器使用由您 Skype 相同的 ca 颁发的证书。 这需要完成的每台服务器运行持久聊天 Web 服务用于文件上载/下载中。 我们强烈建议您在开始持久聊天安装之前, 以及外部 CA 是否具有所需的证书甚至更 （这些事项做可能需要一些时间才能颁发）。
  
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype 的业务服务器 2015年支持**单个公共证书**的使用访问、 web 会议边缘外部接口，以及 A / V 身份验证服务，它提供通过边缘服务器。 边缘内部接口通常将使用您的内部 CA 颁发的专用证书，但如果您希望使用，可用于公共证书这同样，如果它来自受信任的 CA。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果您正在部署移动功能，并且您的移动客户端支持自动发现，您将需要包括在您的证书才能支持从移动客户端的安全连接某些其他使用者替代名称条目。
  
不确定需要哪些证书？ 您需要在以下证书上包含 SAN 名称以支持自动发现：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
我们将在下表中列出具体细节。
  
现在，这是其中少量预规划很好，有时您已经部署了 Skype 的业务服务器 2015年而不打算部署的移动功能，但的提出下行时您的环境中已经有证书。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果这是您查找在并且您有大量的 SIP 域 （这会使添加成本较高的 SAN），您可以配置反向代理 HTTP 用于初始自动发现服务请求，而不是使用 HTTPS （这是默认值配置）。 移动规划主题提供了这方面的详细信息。
  
控制器池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此外，您可以使用 SAN =\*。\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 您的反向代理侦听器将具有 San 您外部 Web 服务 URL。 如果您已经部署了控制器 （这是可选的），会 SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com，一些示例。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

可以使用相同的文件共享的所有文件存储的业务服务器 2015 Skype。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 对于进一步读取在 Windows Server 2012 的 DFS 上，检查出[此 DFS 页面](https://technet.microsoft.com/en-us/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果您正在使用它，您应该组成群集 Windows Server 2012 或 Windows Server 2012 R2。 Windows Server 2008 R2 也是可接受的。 为什么最新的 Windows？ 较旧的版本可能不具备启用所有功能的正确权限。 您可以使用群集管理器创建文件共享，以及[如何创建文件共享群集上的](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster)本文将帮助您与这些详细信息。
    
> [!CAUTION] 
> 您应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 
  


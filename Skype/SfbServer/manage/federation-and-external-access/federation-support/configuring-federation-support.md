---
title: 为 Skype for Business Online 客户配置联合身份验证支持
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '如果您在您的组织中部署 Skype for business, 则可以与一个或多个 Skype for business Online 客户的域联盟。 '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280108"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>为 Skype for business Server 中的 Skype for Business Online 客户配置联合身份验证支持 

你可以通过以下任一方式向组织中的用户提供通信服务:

  - 在你的组织中部署 Skype for Business 服务器 (称为*本地服务*), 并在你的组织中设置 skype for business 用户帐户。
  - 使用托管提供商设置 Microsoft Skype for Business Online 客户帐户, 并使用托管提供商 (称为*联机服务*) 设置用户帐户。

如果您在您的组织中部署 Skype for business, 则可以与一个或多个 Skype for business Online 客户的域联盟。 若要在本地 Skype for Business 部署的用户和 Skype for business Online 客户的用户之间启用联盟, 必须为 Skype for business Online 客户的域和用户配置支持。

> [!NOTE]  
> 本文档仅介绍配置组织以支持与 Skype for Business Online 客户联合的过程。 本文档不介绍配置 Skype for Business Online 客户以支持联盟的过程。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>与 Skype for Business Online 客户进行联盟的先决条件

要与 Skype for business Online 客户联盟, 您应该已经完成了组织中 Skype for business 服务器的初始部署和配置。 这包括以下内容：

  - 在您的组织中部署至少一个标准版服务器或一个企业版前端池。 
  - 为 Skype for business 服务器启用内部用户帐户。 
  - 至少部署一个 Edge 服务器和支持外部用户访问所需的其他组件。 有关详细信息, 请参阅[管理对 Skype for Business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。
  - 在你的组织中启用联合身份验证支持并配置适当的方法来控制联盟域的访问。 有关详细信息, 请参阅为你的组织[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)和[管理 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 为你的组织中的用户启用外部用户访问。 有关详细信息, 请参阅[将外部用户访问策略分配给启用 Skype For business 的用户](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>为 Skype for Business Online 域配置联合身份验证支持

与 Skype for Business Online 客户进行联盟需要你完成以下步骤:

  - 为 Skype for Business Online 2010 客户的域配置支持 (例如, contoso.onmicrosoft.com)。 在[与 Skype For Business Online 客户进行联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)中指定, 你应该已为你的组织启用了联盟。 启用联盟需要指定用于控制联盟域的访问的方法。 如果将组织配置为使用发现, 则将域添加到组织的允许列表是可选的。 如果未启用域发现, 则必须将 Skype for business Online 客户的域名添加到 "允许的域" 列表。 你可以使用 Skype for Business Server 控制面板或通过运行**CSAllowedDomain** cmdlet 来添加域名。 有关使用 Skype for Business 服务器控制面板 (包括启用域发现) 的详细信息, 请参阅[在 Skype For Business 服务器中管理组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 有关使用**CSAllowedDomain** cmdlet 添加域的详细信息, 请参阅[CSAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > Skype for Business Online 客户可以有多个域。 如果要与多个域联盟, 则必须为要支持联盟的每个单独域配置支持, 并且 Skype for Business Online 客户必须为每个域启用联盟, 以便进行联盟。

  - 配置对要与之进行联盟的 Skype for Business Online 客户域的托管提供商的支持。 使用此部分中的过程配置对托管提供程序的支持。

    > [!NOTE]  
    > 只有具有 Skype for Business Online 客户域的联盟才需要此步骤, 而不是针对在联盟伙伴位置上部署的任何域的联盟。


### <a name="to-configure-support-for-a-hosting-provider"></a>为托管提供商配置支持

1.  从前端服务器, 启动 Skype for business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、"skype for business**服务器**", 然后单击 " **skype for business 服务器管理外壳程序**"。

2.  运行**CsHostingProvider** cmdlet 以创建和配置托管提供程序。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述示例设置了以下参数：
    
      - **标识**为你创建的托管提供程序指定唯一的字符串值标识符。 请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。
    
      - **ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定域名 (FQDN)。 不能修改此值。 如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **VerificationLevel**指定如何验证从托管提供程序发送的消息 (或 if) 以确保它们是从该提供商处发送的。
    
      - **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 **True **，否则无法在这两个组织之间交换消息。
    
      - **EnabledSharedAddressSpace ** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers**指示托管提供商是否用于托管 Skype For business 服务器帐户。 如果设置为 **False **，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal**指示托管提供商使用的代理服务器是否包含在您的 Skype For business 服务器拓扑中。
    
    有关使用此 cmdlet 的详细信息, 请参阅[CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>为使用 Skype for Business Online 客户的联盟配置用户访问权限 

您必须配置组织中所有用户的用户帐户, 以便允许他们与联盟伙伴通信。 此配置适用于所有联盟合作伙伴, 包括您支持联合的任何 Microsoft Skype for Business Online 客户域。 有关为用户帐户配置联合身份验证支持的详细信息, 请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)和[将外部用户访问策略分配给启用 Skype for business 的用户的外部用户访问策略](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for business Server 中验证与 Skype for business Online 客户的通信

要使您的组织中的 Skype for Business 用户能够与 Skype for business Online 客户的用户进行通信, 您必须已完成以下步骤:

  - 满足所有先决条件。 这包括部署内部和边缘服务器、为你的组织启用联合身份验证支持以及设置用户帐户。 有关详细信息, 请参阅[与 Skype For Business Online 客户进行联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 在内部部署中配置了域访问支持。 这包括创建主机提供程序条目和配置你的部署, 以允许从 Skype for Business Online 客户的域访问。 有关详细信息, 请参阅[配置 Skype For Business Online 域的联合身份验证支持](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - 已配置你的用户帐户以支持联合身份验证。 有关详细信息, 请参阅为[使用 Skype For Business Online 客户的联盟配置用户访问权限](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成所有这些步骤后, Skype for Business Online 客户的管理员完成了其在线服务的所有配置, 以支持与组织的联盟, 请通过测试通信之间的通信来验证您的组织中的内部用户和 Skype for Business Online 客户的用户。 如果通信不成功, 请使用边缘服务器中的日志记录工具捕获日志和跟踪文件, 以便对问题进行故障排除。 

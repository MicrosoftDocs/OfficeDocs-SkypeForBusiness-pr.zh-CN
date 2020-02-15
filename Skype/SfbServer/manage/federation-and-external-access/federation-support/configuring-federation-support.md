---
title: 为 Skype for Business Online 客户配置联合支持
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: '如果您在组织中部署 Skype for Business，则可以与一个或多个 Skype for Business Online 客户的域联盟。 '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037282"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for business Server 中为 Skype for business Online 客户配置联合支持 

可以通过以下任一方式为组织中的用户提供通信服务：

  - 在组织中部署 Skype for business Server （称为*本地服务*）并在组织中设置 Skype for business 用户帐户。
  - 使用托管提供商设置 Microsoft Skype for Business Online 客户帐户，并使用托管提供商设置用户帐户（称为 "*联机服务*"）。

如果您在组织中部署 Skype for Business，则可以与一个或多个 Skype for Business Online 客户的域联盟。 若要在本地 Skype for Business 部署的用户和 Skype for business Online 客户的用户之间启用联盟，您必须配置对适用于 Skype for business Online 客户的域和用户的支持。

> [!NOTE]  
> 本文档仅介绍配置组织以支持与 Skype for Business Online 客户联合的过程。 本文档不介绍配置 Skype for Business Online 客户以支持联合的过程。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>与 Skype for Business Online 客户进行联盟的先决条件

若要与 Skype for business Online 客户联合，您应已在组织中完成了 Skype for business Server 的初始部署和配置。 其中包括：

  - 在您的组织中部署至少一个 Standard Edition server 或一个 Enterprise Edition 前端池。 
  - 为 Skype for business Server 启用内部用户帐户。 
  - 至少部署一台边缘服务器以及支持外部用户访问所需的其他组件。 有关详细信息，请参阅[管理对 Skype For Business Server 的联盟和外部访问](../managing-federation-and-external-access.md)。
  - 在您的组织中启用联盟支持并配置适当的方法来控制联合域进行的访问。 有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)和[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 为您的组织中的用户启用外部用户访问。 有关详细信息，请参阅[将外部用户访问策略分配给启用 Skype For business 的用户](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>为 Skype for Business Online 域配置联合支持

与 Skype for Business Online 客户进行联盟需要您完成以下步骤：

  - 配置对 Skype for Business Online 2010 客户的域的支持（例如，contoso.onmicrosoft.com）。 如在[与 Skype for Business Online 客户进行联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)中指定，您应该已为组织启用了联盟。 启用联盟要求指定联盟的域用于控制访问的方法。 如果将组织配置为使用发现，则可以选择将域添加到组织的允许列表。 如果未启用域发现，则必须将 Skype for Business Online 客户的域名添加到允许的域列表中。 您可以通过使用 Skype for Business Server 控制面板或通过运行**CSAllowedDomain** cmdlet 来添加域名。 有关使用 Skype for Business Server 控制面板（包括启用域发现）的详细信息，请参阅[在 Skype for Business Server 中管理组织的 SIP 联合提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 有关使用**CSAllowedDomain** cmdlet 添加域的详细信息，请参阅[CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > Skype for Business Online 客户可以有多个域。 如果要与多个域联盟，则必须为要支持联合的每个单独域配置支持，并且 Skype for Business Online 客户的管理员必须为每个域启用联合身份验证。进行联合。

  - 配置对要与之联合的 Skype for Business Online 客户域的主机提供程序的支持。 请使用本节中的步骤配置托管服务提供商支持。

    > [!NOTE]  
    > 此步骤仅适用于与 Skype for Business Online 客户的域进行联盟，而不是用于与在联合合作伙伴的位置部署在本地部署的任何域的联盟。


### <a name="to-configure-support-for-a-hosting-provider"></a>要从前端服务器

1.  从前端服务器启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business server**"，然后单击 " **skype for business server Management Shell**"。

2.  运行 **New-CsHostingProvider** cmdlet 以创建和配置托管服务提供商。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    前一个示例将设置以下参数：
    
      - **Identity** 为您创建的托管服务提供商指定唯一的字符串值标识符。请注意，如果已使用该 Identity 对现有的提供商进行配置，该命令将无法运行。
    
      - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。该值不能修改。如果托管服务提供商更改了其代理服务器，则需要为该提供商删除并重新创建项目。
    
      - **VerificationLevel** 指定如何（或是否）验证邮件是从托管服务提供商发送，以确保这些邮件是从该提供商发送。
    
      - **Enabled** 指示是否已启用您的域和托管服务提供商之间的网络连接。只有将该值设置为 **True**，才能在这两个组织之间交换邮件。
    
      - **EnabledSharedAddressSpace** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers**指示是否使用托管提供程序来承载 Skype For business Server 帐户。 如果设置为 **False**，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal**指示托管提供程序使用的代理服务器是否包含在您的 Skype For business server 拓扑中。
    
    有关使用此 cmdlet 的详细信息，请参阅[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>为具有 Skype for Business Online 客户的联盟配置用户访问权限 

您必须对组织中所有用户的用户帐户进行配置，以便其能够与联盟伙伴进行通信。 此配置适用于所有联盟伙伴，包括您支持联合的任何 Microsoft Skype for Business Online 客户域。 有关为用户帐户配置联合身份验证支持的详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)并[将外部用户访问策略分配给启用 Skype for business 的用户](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>验证与 skype for Business Server 中的 Skype for business Online 客户的通信

若要使组织中的 Skype for Business 用户能够与 Skype for business Online 客户的用户通信，您必须完成以下步骤：

  - 满足所有先决条件。 这包括部署内部和边缘服务器，为组织实现联盟支持以及设置用户帐户。 有关详细信息，请参阅[与 Skype for Business Online 客户进行联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 配置内部部署中的域访问支持。 这包括创建主机提供程序条目和配置您的部署，以允许从 Skype for Business Online 客户域访问。 有关详细信息，请参阅[Configure federation support for a Skype For Business Online domain](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - 将用户帐户配置为支持联盟。 有关详细信息，请参阅[Configure user access for federation with a Skype For Business Online 客户](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成所有这些步骤和 Skype for Business Online 客户的管理员后，即可完成其在线服务的所有配置，以支持与组织的联盟，请通过测试通信之间的通信来验证组织中的内部用户和 Skype for Business Online 客户的用户。 如果通信不成功，请使用边缘服务器中的日志记录工具捕获日志和跟踪文件，以便对问题进行故障排除。 

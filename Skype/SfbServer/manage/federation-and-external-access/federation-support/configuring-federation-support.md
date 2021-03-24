---
title: 为 Skype for Business Online 客户配置联合身份验证支持
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '如果你在组织中部署 Skype for Business，你可以与一个或多个 Skype for Business Online 客户的域联盟。 '
ms.openlocfilehash: c241af4700662c11366a71a55afad28ed3f8b7db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098948"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for Business Server 中为 Skype for Business Online 客户配置联盟支持 

可以通过以下任一方式为组织中的用户提供通信服务：

  - 在组织中部署 Skype for Business Server (称为本地服务) 在组织中设置 Skype for Business 用户帐户。
  - 使用托管提供商设置 Microsoft Skype for Business Online 客户帐户，使用托管提供商帐户设置用户帐户 (联机 *服务) 。*

如果你在组织中部署 Skype for Business，你可以与一个或多个 Skype for Business Online 客户的域联盟。 若要在本地 Skype for Business 部署的用户与 Skype for Business Online 客户的用户之间启用联盟，必须配置对域和 Skype for Business Online 客户用户的支持。

> [!NOTE]  
> 本文档仅介绍将组织配置为支持与 Skype for Business Online 客户的联盟的过程。 本文档不介绍配置 Skype for Business Online 客户以支持联盟的过程。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>与 Skype for Business Online 客户联盟的先决条件

若要与 Skype for Business Online 客户联盟，你应已完成组织中 Skype for Business Server 的初始部署和配置。 其中包括：

  - 在组织中部署至少一台 Standard Edition Server 或一个 Enterprise Edition 前端池。 
  - 为 Skype for Business Server 启用内部用户帐户。 
  - 部署至少一台边缘服务器和支持外部用户访问所需的其他组件。 有关详细信息，请参阅 [管理对 Skype for Business Server](../managing-federation-and-external-access.md)的联盟和外部访问。
  - 在您的组织中启用联盟支持并配置适当的方法来控制联合域进行的访问。 有关详细信息，请参阅为[组织启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)[和管理 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 为您的组织中的用户启用外部用户访问。 有关详细信息，请参阅 [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>配置 Skype for Business Online 域的联盟支持

与 Skype for Business Online 客户联盟需要完成以下步骤：

  - 配置对 Skype for Business Online 2010 客户域的支持 (例如，contoso.onmicrosoft.com) 。 正如 [Prerequisites for federating with a Skype for Business Online customer](#prerequisites-for-federating-with-a-skype-for-business-online-customer)中指定的，你应该已经为组织启用了联盟。 启用联盟要求指定联盟的域用于控制访问的方法。 如果将组织配置为使用发现，则可以选择将域添加到组织的允许列表。 如果未启用域发现，则必须将 Skype for Business Online 客户的域名添加到允许的域列表中。 可以使用 Skype for Business Server 控制面板或运行 **New-CSAllowedDomain** cmdlet 添加域名。 有关使用 Skype for Business Server 控制面板（包括启用域发现）的详细信息，请参阅在 Skype for Business Server 中管理组织的 [SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 有关使用 **New-CSAllowedDomain** cmdlet 添加域的详细信息，请参阅 [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > Skype for Business Online 客户可以有多个域。 如果要与多个域联盟，则必须为要支持联盟的每个单独域配置支持，并且 Skype for Business Online 客户的管理员必须为每个要联盟的域启用联盟。

  - 配置对要联盟的 Skype for Business Online 客户域的托管提供商的支持。 请使用本节中的步骤配置托管服务提供商支持。

    > [!NOTE]  
    > 只有与 Skype for Business Online 客户的域联盟才需要此步骤，与本地部署在联盟伙伴位置的任何域的联盟不需要此步骤。


### <a name="to-configure-support-for-a-hosting-provider"></a>要从前端服务器

1.  从前端服务器中，启动 Skype for Business Server 命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2.  运行 **New-CsHostingProvider** cmdlet 以创建和配置托管服务提供商。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    前一个示例将设置以下参数：
    
      - **Identity** 为您创建的托管服务提供商指定唯一的字符串值标识符。请注意，如果已使用该 Identity 对现有的提供商进行配置，该命令将无法运行。
    
      - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。该值不能修改。如果托管服务提供商更改了其代理服务器，则需要为该提供商删除并重新创建项目。
    
      - **VerificationLevel** 指定如何（或是否）验证邮件是从托管服务提供商发送，以确保这些邮件是从该提供商发送。
    
      - **Enabled** 指示是否已启用您的域和托管服务提供商之间的网络连接。只有将该值设置为 **True**，才能在这两个组织之间交换邮件。
    
      - **EnabledSharedAddressSpace** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers** 指示宿主提供商是否用于托管 Skype for Business Server 帐户。 如果设置为 **False**，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal** 指示宿主提供商使用的代理服务器是否包含在 Skype for Business Server 拓扑中。
    
    有关使用此 cmdlet 的详细信息，请参阅 [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>配置用户与 Skype for Business Online 客户的联盟访问权限 

您必须对组织中所有用户的用户帐户进行配置，以便其能够与联盟伙伴进行通信。 此配置适用于所有联盟伙伴，包括支持联盟的任何 Microsoft Skype for Business Online 客户域。 有关为用户帐户配置联盟支持的详细信息，请参阅配置策略以[](../external-access-policies/configure-policies-to-control-federated-user-access.md)控制联盟用户访问和为启用 Skype for Business 的用户分配外部[用户访问策略](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for Business Server 中验证与 Skype for Business Online 客户的通信

若要使贵组织的 Skype for Business 用户能够与 Skype for Business Online 客户的用户进行通信，必须完成以下步骤：

  - 满足所有先决条件。 这包括部署内部和边缘服务器，为组织实现联盟支持以及设置用户帐户。 有关详细信息，请参阅 [Prerequisites for federating with a Skype for Business Online customer](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 配置内部部署中的域访问支持。 这包括创建主机提供商条目和配置部署以允许从 Skype for Business Online 客户的域访问。 有关详细信息，请参阅 [配置 Skype for Business Online](#configure-federation-support-for-a-skype-for-business-online-domain)域的联盟支持。
  - 将用户帐户配置为支持联盟。 有关详细信息，请参阅 [Configure user access for federation with a Skype for Business Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成上述所有步骤后，Skype for Business Online 客户的管理员完成其在线服务的所有配置以支持与组织的联盟，通过测试组织中内部用户与 Skype for Business Online 客户的用户之间的通信来验证通信。 如果通信不成功，请使用边缘服务器的日志记录工具捕获日志和跟踪文件，以便解决问题。
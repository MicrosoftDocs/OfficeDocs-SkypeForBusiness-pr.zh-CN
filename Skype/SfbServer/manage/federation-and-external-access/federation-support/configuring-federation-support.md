---
title: 为 Skype for Business Online 客户配置联合身份验证支持
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '如果您的组织中部署 for Business 的 Skype，您可以与联盟的域的一个或多个 Skype 业务联机客户。 '
ms.openlocfilehash: 70eda58c5d01b09c9f3e00ef8f3ac0391a90ed07
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199868"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>为业务服务器 Skype 中配置业务联机客户的 Skype 联合身份验证的支持 

您可以 communications 服务向用户提供您的组织中任何通过以下方式：

  - 部署 Skype for Business Server 在您的组织 （称为*本地服务*） 和 Skype 设置为在组织中的业务用户帐户。
  - 设置业务联机客户帐户与宿主提供商 Microsoft Skype 和设置用户帐户与宿主提供商 （称为*联机服务*）。

如果您的组织中部署 for Business 的 Skype，您可以与联盟的域的一个或多个 Skype 业务联机客户。 若要启用的业务部署您的本地 Skype 的用户和业务联机客户的 Skype 的用户之间建立联盟，必须配置支持的域和业务联机客户的 Skype 的用户。

> [!NOTE]  
> 本文档介绍用于配置您的组织支持的业务联机客户与 Skype 联合身份验证的过程。 本文档不介绍了配置以支持联盟的业务联机客户的 Skype 的过程。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>与 Skype 的业务联机客户联盟的先决条件

与 Skype 的业务联机客户联盟，您应已经完成了初始部署和配置的 Skype 业务 server 在组织中。 这包括以下内容：

  - 部署至少一台 Standard Edition 服务器或在组织中的一个 Enterprise Edition 前端池。 
  - 为业务服务器启用 Skype 内部的用户帐户。 
  - 部署至少一台边缘服务器和其他组件需要支持外部用户访问。 有关详细信息，请参阅[Managing 联盟和外部访问 Skype 业务服务器](../managing-federation-and-external-access.md)。
  - 启用贵组织中的联合身份验证支持和配置用于控制联盟域访问相应的方法。 有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)和[管理 SIP 联盟提供程序为您的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 允许您组织中的用户的外部用户访问。 有关详细信息，请参阅[分配到业务启用的用户的 Skype 外部用户访问策略](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>配置对业务 Online 域 Skype 联合身份验证支持

与 Skype 的业务联机客户联盟需要完成以下步骤：

  - 配置对业务 Online 2010 客户 (例如，contoso.onmicrosoft.com) 的 Skype 的域的支持。 如指定[与 Skype 的业务联机客户联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)，您应已启用联合身份验证您的组织。 启用联盟，则需要指定用于控制访问权限的联盟域的方法。 如果您配置您的组织使用发现，将域添加到您的组织允许列表是可选的。 如果您未启用域发现，必须将业务联机客户的 Skype 的域名添加到允许的域列表。 使用适用于业务 Server Control Panel Skype 或通过运行**New-csalloweddomain** cmdlet，您可以添加域名称。 有关为业务 Server Control Panel，包括启用发现域，使用 Skype 的详细信息，请参阅[管理 SIP 联盟提供程序中的业务服务器 Skype 的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 有关使用**New-csalloweddomain** cmdlet 可添加域的详细信息，请参阅[New-csalloweddomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > 为业务 Online 客户 Skype 可以有多个域。 如果您想要使用多个域的联盟，则必须配置为每个单独的域与您想要支持联盟和业务联机客户的 Skype 的管理员必须启用联合身份验证的域到每个支持联合。

  - 配置对您想要联合的业务联机客户域 Skype 宿主提供商支持。 使用本节中的过程配置支持的宿主提供商。

    > [!NOTE]  
    > 与域联盟的 Skype 业务 Online 客户，不与本地部署的联盟的伙伴的位置的任何域联盟才需要此步骤。


### <a name="to-configure-support-for-a-hosting-provider"></a>若要配置宿主提供商支持

1.  从前端服务器，为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

2.  运行**New-cshostingprovider** cmdlet 来创建和配置托管服务提供商。 例如，运行：
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述示例设置了以下参数：
    
      - **标识**要创建的托管服务提供商指定唯一的字符串值标识符。 请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。
    
      - **ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定域名 (FQDN)。 不能修改此值。 如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。
    
      - **VerificationLevel**指定如何 （或者是否） 验证从托管服务提供商发送的邮件以确保它们已从该提供商发送。
    
      - **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 **True **，否则无法在这两个组织之间交换消息。
    
      - **EnabledSharedAddressSpace ** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。
    
      - **HostsOCSUsers**指示承载服务提供商是否用于承载 Skype Business Server 帐户。 如果设置为 **False **，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。
    
      - **IsLocal**指示承载服务提供商使用的代理服务器是否包含您 Skype 企业服务器拓扑中。
    
    有关使用此 cmdlet 的详细信息，请参阅[New-cshostingprovider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>配置与业务联机客户的 Skype 联合身份验证的用户访问 

您必须配置用户允许的顺序为其组织中的所有用户帐户与联盟伙伴通信。 为所有的联盟伙伴，包括与您支持联合身份验证的业务联机客户域任何 Microsoft Skype 应用此配置。 有关为用户帐户配置联盟支持的详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)和[分配到业务启用的用户的 Skype 外部用户访问策略](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>验证与 Skype 中的业务联机客户的 Skype 业务服务器的通信

Skype 启用您的组织中的业务用户来与业务联机客户的 Skype 的用户通信，您必须完成以下步骤：

  - 满足所有先决条件。 这包括内部部署和启用联盟的边缘服务器支持您的组织和设置用户帐户。 有关详细信息，请参阅[与 Skype 的业务联机客户联盟的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 内部部署中配置的域访问支持。 这包括创建主机提供程序条目和配置部署以允许访问来自业务联机客户的域 Skype。 有关详细信息，请参阅[配置联盟支持的业务 Online 域 Skype](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - 配置用户帐户以支持联盟。 有关详细信息，请参阅[配置与业务联机客户的 Skype 的联盟用户访问](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

在完成所有这些步骤和 Skype 的管理员的业务联机客户完成其联机服务，以支持与您的组织的联合身份验证的所有配置后，通过测试之间的通信验证的通信在您的组织和业务联机客户的 Skype 的用户的内部用户。 如果通信不成功，日志记录工具用于从边缘服务器捕获日志和跟踪文件以便解决问题。 

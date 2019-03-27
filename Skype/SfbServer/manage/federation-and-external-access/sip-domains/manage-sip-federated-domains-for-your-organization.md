---
title: 管理组织的 SIP 联盟域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何管理和配置您可以与，联盟的 SIP 域
ms.openlocfilehash: 83623b41e0d9adb1e4539958344214fd2ebe0db9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892257"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>管理您的组织中 Skype 业务服务器的 SIP 联盟域


若要管理和配置可与其进行联盟的 SIP 域，请执行以下操作：

  - 创建或编辑 SIP 联盟伙伴域的允许的域列表。

  - 创建或编辑 SIP 联盟域的阻止的域列表。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>在 Skype for Business Server 配置为允许的外部域的支持

如果已配置联盟伙伴的支持，您可以管理的特定域可以与组织联盟。 您将一个或多个特定的外部域配置为允许的联盟域。 若要执行此操作，请将每个域添加到允许域列表。 即使您的组织启用合作伙伴搜索之后，如果这样做域为联盟的伙伴，可能需要与多个 1,000 个用户进行通信，或者可能需要发送多个是每秒 20 条消息。 如果未为组织启用合作伙伴发现，只有您将添加到允许的域列表的外部域的用户可以参与 IM 和会议与您的组织中的用户。 如果您想要限制到特定服务器上运行的访问边缘服务的联盟伙伴的联盟域的访问，您可以指定运行访问边缘服务的每个域的允许域列表中的服务器的域名。

> [!NOTE]  
> 此过程介绍如何配置为特定域的支持，但还实现联盟用户的支持要求您为组织启用联盟用户的支持和配置，并将策略应用于哪些用户可以的控制与联盟用户进行协作。 有关启用联盟用户的支持的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 有关配置策略以控制联盟的详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>将外部域添加到允许域列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**联盟域**。
4.  在**联盟域**页上，单击**新建**，然后单击**允许的域**。
5.  在**新建联盟域**中，执行以下操作：
    
      - 在**域名 （或 FQDN）**，键入的联盟的伙伴域名。       

        > [!NOTE]  
        > 此名称必须是唯一的并且不能为此服务器的运行访问边缘服务不允许域已存在。 该名称不得超过 256 个字符的长度。<BR><br>联盟的伙伴域名上的搜索执行后缀匹配。 例如，如果键入**contoso.com**，则搜索也将返回域**it.contoso.com**。<BR><br>不能同时阻止并且允许联盟的伙伴域。 Skype 业务服务器阻止此发生，以便您无需同步您的列表。
    
      - 如果要将此联合域的访问限制的特定服务器中**访问边缘服务 (FQDN)**，运行访问边缘服务，用户键入运行访问边缘服务的联盟的域服务器的 FQDN。    
      - 如果您想要提供其他信息，在**注释**键入要与有关此配置其他系统管理员共享的信息。

6.  单击“**提交**”。
7.  对于您要允许每个联盟的伙伴域，重复步骤 4 至 6。

若要启用联盟的用户访问，您还必须在组织中启用对联盟的用户访问的支持。 有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您必须配置并将策略应用于您希望能够与联盟用户进行协作的用户。 有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>在 Skype for Business Server 中配置对阻止的外部域的支持 

如果已配置联盟伙伴的支持，您可以管理哪些域将阻止与您的组织建立联盟。 阻止的域列表将充当阻止列表 （将不允许的显式条目的列表），并且如果您已启用此选项将应用在联盟的域发现。 有关详细信息，请参阅[启用或禁用联盟伙伴的发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。

阻止从连接到组织的一个或多个外部域。 若要执行此操作，请将域添加到阻止的域列表。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>将外部域添加到阻止的域列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3.  在左侧的导航栏中，单击**外部用户访问**。
4.  单击**联盟域**，单击**新建**，然后单击**被阻止的域**。
5.  在**新建联盟域**中，执行以下操作：
    
      - 在**域名 （或 FQDN）** 中，键入您想要阻止的联盟的伙伴域的名称。

        > [!NOTE]  
        > 该名称不得超过 256 个字符的长度。<BR><br>联盟的伙伴域名上的搜索执行后缀匹配。 例如，如果键入**contoso.com**，则搜索也将返回域**it.contoso.com**。<BR><br>不能同时阻止并且允许联盟的伙伴域。 Skype 业务服务器阻止此发生，以便您无需同步您的列表。
   
      - （可选）在**注释**中，键入要与有关此配置其他系统管理员共享的信息。

6.  单击“**提交**”。
7.  对每个要阻止的联盟伙伴重复步骤 4 至 6。

若要启用联盟的用户访问，您还必须在组织中启用对联盟的用户访问的支持。 有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您必须配置并将策略应用于您希望能够与联盟用户进行协作的用户。 有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>另请参阅

[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[启用或禁用联盟伙伴发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  


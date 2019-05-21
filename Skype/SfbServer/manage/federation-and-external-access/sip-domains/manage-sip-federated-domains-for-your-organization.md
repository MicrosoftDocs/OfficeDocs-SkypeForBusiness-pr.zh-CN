---
title: 管理组织的 SIP 联盟域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何管理和配置可与联合的 SIP 域,
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303968"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>在 Skype for Business Server 中管理组织的 SIP 联盟域


若要管理和配置可以与联盟的 SIP 域, 可以执行以下操作:

  - 创建或编辑 SIP 联盟伙伴域的允许域列表。

  - 创建或编辑 SIP 联盟域的阻止域列表。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置对允许的外部域的支持

如果您已为联盟伙伴配置支持, 则可以管理哪些特定域可以与您的组织联盟。 将一个或多个特定外部域配置为 "允许的联盟域"。 若要执行此操作, 请将每个域添加到允许的域列表中。 即使为你的组织启用了合作伙伴发现, 如果域是联盟伙伴, 并且可能需要与超过1000的用户通信, 或者可能需要每秒发送20个以上的消息, 请执行此操作。 如果你的组织未启用合作伙伴发现, 则只有你添加到 "允许的域" 列表中的外部域用户才可以与你的组织中的用户参与 IM 和会议。 如果你想要将联盟域的访问权限限制为运行联盟伙伴的访问边缘服务的特定服务器, 你可以为允许的域列表中的每个域指定运行 "访问边缘" 服务的服务器的域名。

> [!NOTE]  
> 此过程介绍如何为特定域配置支持, 但实现对联合用户的支持还要求你为组织启用联合用户支持, 以及配置和应用策略以控制哪些用户可以协作处理联盟用户。 有关为联盟用户启用支持的详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 有关配置控制联盟的策略的详细信息, 请参阅[配置控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>将外部域添加到允许的域列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**联盟域**"。
4.  在 "**联盟域**" 页面上, 单击 "**新建**", 然后单击 "**允许的域**"。
5.  在**新的联盟域**中, 执行下列操作:
    
      - 在 "**域名 (或 FQDN)**" 中, 键入联盟伙伴域的名称。       

        > [!NOTE]  
        > 此名称必须是唯一的, 并且不能作为运行 Access Edge 服务的此服务器的允许域存在。 名称长度不能超过256个字符。<BR><br>"联盟伙伴" 域名上的搜索执行后缀匹配。 例如, 如果您键入 " **contoso.com**", 搜索也将返回域**it.contoso.com**。<BR><br>联盟伙伴域不能同时被阻止和允许。 Skype for Business 服务器阻止这种情况, 因此您不必同步您的列表。
    
      - 如果要将此联盟域的访问权限限制为运行 Access Edge 服务的特定服务器的用户, 请在 "**访问边缘服务 (FQDN)**" 中, 键入运行 access Edge 服务的联盟域服务器的 FQDN。    
      - 如果要提供其他信息, 请在 "**评论**" 中键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“**提交**”。
7.  对要允许的每个联盟伙伴域重复步骤4到步骤6。

若要启用联盟用户访问, 还必须启用组织中的联合用户访问支持。 有关详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外, 你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。 有关详细信息, 请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置对阻止的外部域的支持 

如果你已为联盟伙伴配置支持, 你可以管理阻止哪些域与你的组织进行联盟。 被阻止域的列表将充当阻止列表 (列出不允许的显式条目), 并且将在联合域发现中应用 (如果已启用此选项)。 有关详细信息, 请参阅[启用或禁用联合身份验证合作伙伴的发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。

阻止一个或多个外部域连接到你的组织。 若要执行此操作, 请将该域添加到阻止域的列表中。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>将外部域添加到阻止域的列表

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
3.  在左侧导航栏中, 单击 "**外部用户访问**"。
4.  单击 "**联盟域**", 单击 "**新建**", 然后单击 "**阻止的域**"。
5.  在**新的联盟域**中, 执行下列操作:
    
      - 在 "**域名 (或 FQDN)**" 中, 键入要阻止的联盟伙伴域的名称。

        > [!NOTE]  
        > 名称长度不能超过256个字符。<BR><br>"联盟伙伴" 域名上的搜索执行后缀匹配。 例如, 如果您键入 " **contoso.com**", 搜索也将返回域**it.contoso.com**。<BR><br>联盟伙伴域不能同时被阻止和允许。 Skype for Business 服务器阻止这种情况, 因此您不必同步您的列表。
   
      - 可选在 "**批注**" 中, 键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“**提交**”。
7.  对要阻止的每个联盟伙伴重复步骤4到步骤6。

若要启用联盟用户访问, 还必须启用组织中的联合用户访问支持。 有关详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外, 你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。 有关详细信息, 请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>另请参阅

[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[启用或禁用联盟伙伴发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  


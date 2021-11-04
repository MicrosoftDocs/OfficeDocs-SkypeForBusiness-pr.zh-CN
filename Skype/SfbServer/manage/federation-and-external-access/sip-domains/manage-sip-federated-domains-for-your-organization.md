---
title: 管理组织的 SIP 联盟域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 了解如何管理和配置可以联盟的 SIP 域，
ms.openlocfilehash: 455cac695ead7f073269fe3df0e70ea5b26ccb0e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743538"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>在组织中管理组织的 SIP 联盟Skype for Business Server


要管理和配置可与其进行联盟的 SIP 域，您可以执行以下操作：

  - 创建或编辑 SIP 联盟伙伴域的允许域列表。

  - 创建或编辑 SIP 联盟域的阻止域列表。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>配置对域中允许的外部域Skype for Business Server

如果配置了对联盟伙伴的支持，您可以管理可与组织联盟的特定域。您将一个或多个特定外部域配置为允许的联盟域。要执行此操作，请将每个域添加到允许域列表中。即使组织启用了伙伴发现，但如果域是需要与 1,000 个以上的用户通信或每秒需要发送 20 多条消息的联盟伙伴，也请执行此操作。如果组织未启用伙伴发现，则只有添加到允许域列表的外部域的用户才能与组织内的用户一起参与 IM 会话和会议。如果要将对联盟域的访问限制为运行联盟伙伴的访问边缘服务的特定服务器，可以为允许域列表中的每个域指定运行访问边缘服务的服务器的域名。

> [!NOTE]  
> 此过程描述如何配置对特定域的支持，但是实施对联盟用户的支持还需要组织启用对联盟用户的支持，并配置和应用策略以控制可与联盟用户协作的用户。 有关启用对联盟用户的支持的详细信息，请参阅启用 [或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 有关配置策略以控制联盟的详细信息，请参阅配置 [策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>将外部域添加到允许域列表中

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。
2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3.  在左侧导航栏中，单击“外部用户访问”，然后单击“联盟域”。
4.  在“联盟域”页上，单击“新建”，然后单击“允许的域”。
5.  在“新建联盟域”中，执行下列操作：
    
      - 在“域名(或 FQDN)”中，键入联盟伙伴域的名称。       

        > [!NOTE]  
        > 此名称必须是唯一的，并且不能与运行访问边缘服务的服务器的允许域的已有名称相同。该名称的长度不能超过 256 个字符。<BR><br>搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 **contoso.com**，搜索还将返回域 **it.contoso.com**。<BR><br>无法同时阻止和允许联盟合作伙伴域。 Skype for Business Server阻止这种情况发生，以便你不需要同步列表。
    
      - 如果要将对此联盟域的访问限制为运行访问边缘服务的特定服务器的用户，请在“访问边缘服务(FQDN)”中键入运行访问边缘服务的联盟域的服务器的 FQDN。    
      - 如果要提供其他信息，请在“注释”中键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“提交”。
7.  对要允许的每个联盟伙伴域，重复步骤 4 至 6。

若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。 有关详细信息，请参阅 [启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。 有关详细信息，请参阅 [配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>配置对网站中阻止的外部域Skype for Business Server 

如果您配置了对联盟伙伴的支持，则可通过与您的组织联盟来管理将阻止的域。 被阻止的域的列表将充当阻止名单（不允许使用的显式条目的列表）并将在联盟域发现中应用（如果您启用了此选项）。 有关详细信息，请参阅启用 [或禁用联盟伙伴的发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。

阻止一个或多个外部域连接到您的组织。要执行此操作，请将相应的域添加到阻止域列表中。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>将外部域添加到阻止域列表中

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。
2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3.  在左侧导航栏中，单击“外部用户访问”。
4.  单击“联盟域”，再单击“新建”，然后单击“被阻止的域”。
5.  在“新建联盟域”中，执行下列操作：
    
      - 在“域名(或 FQDN)”中，键入要阻止的联盟伙伴域的名称。

        > [!NOTE]  
        > 该名称的长度不能超过 256 个字符。<BR><br>搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 **contoso.com**，搜索还将返回域 **it.contoso.com**。<BR><br>无法同时阻止和允许联盟合作伙伴域。 Skype for Business Server阻止这种情况发生，以便你不需要同步列表。
   
      - （可选）在“注释”中，键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“提交”。
7.  对要阻止的每个联盟伙伴，重复步骤 4 至 6。

若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。 有关详细信息，请参阅 [启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。

此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。 有关详细信息，请参阅 [配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>另请参阅

[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[启用或禁用联盟伙伴发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  


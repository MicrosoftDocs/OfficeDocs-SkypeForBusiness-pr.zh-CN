---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何为用户的 SIP 联盟提供程序配置支持。
ms.openlocfilehash: 1259ae9d2dfd7d829caaa6dba714f0876b5500c4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197833"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>管理您的组织中 Skype 业务服务器的 SIP 联盟提供程序

要配置用户的 SIP 联盟提供商支持，您需要执行下列操作：

  - 配置一个或多个外部用户访问策略以支持与 SIP 联盟提供程序联系人

  - 指定要支持哪些托管提供程序

  - 指定要支持哪些公共 IM 提供程序

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>创建或编辑公共 SIP 联盟提供商 Skype 中的业务服务器

公共即时消息 (IM) 连接，您的组织中的用户，可以使用 IM 与 IM 服务提供的公共提供商的用户进行通信。

Skype 业务服务器都有公共提供商配置即时消息。 每个公共提供程序配置提供程序的边缘服务器的完全限定名称，与默认的验证级别**允许用户仅与使用此提供程序其联系人列表上的人进行通信**。

设置默认情况下，启用无公共提供商。 您应完成许可协议和资源调配前启用公共提供商的工作。 在完成的许可和资源调配工作之前，您可以启用提供程序。 用户不能与联系人进行通信在这些提供程序直到完成的系统必备的工时。 有关许可和公共提供商的设置的详细信息，请参阅[配置策略以控制公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。

使用以下过程创建或编辑公共提供商。


### <a name="to-create-or-edit-public-providers"></a>创建或编辑公共提供商

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**联盟和外部访问**，然后单击**SIP 联盟提供程序**。

4.  如果您需要创建新的公共提供程序，请单击**新建**，然后单击**公共提供商**。

5.  如果您需要编辑公共提供商的列表的一个条目，请您可以选择一个公共提供程序，单击**编辑**，然后单击**显示详细信息**。

6.  在**编辑 SIP 联盟提供程序**页上，您可以键入或编辑以下设置：
    
      - **启用与此提供程序通信**   选择此设置允许与此提供程序的用户的 IM。
    
      - **提供程序名称：**   必需的属性，类型为其提供程序的名称将反映在 SIP 联盟提供商的列表。
    
      - **访问边缘服务 (FQDN):**   必需的属性，键入您要配置的提供程序的访问边缘服务的完全限定的域名。 此信息作为默认项，提供，且如果公共提供商访问边缘服务公共提供商的 fqdn 进行了更改只应被更改。
    
      - **默认验证级别：**   默认设置，**允许用户与使用此提供程序其联系人列表上的人进行通信**将限制到的已接受和联系人列表中联系人通信。
        
        选择**允许用户与任何人使用此提供程序通信**中删除的限制，您必须已收到并接受联系人邀请。 此设置不会限制谁可以与您联系从公共提供商网络。

7.  当您完成配置设置，单击**提交**保存，，或单击**取消**以放弃更改。

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>创建或编辑业务服务器承载 Skype 中的 SIP 联盟提供程序

托管提供程序即时消息 (IM) 连接，用户在组织中可以使用 IM 与托管提供程序提供的 IM 服务的用户进行通信。

每个托管的提供程序配置提供程序的边缘服务器的完全限定名称，与默认的验证级别**允许用户仅与使用此提供程序其联系人列表上的人进行通信**。

使用以下过程可创建或编辑托管提供程序。

### <a name="to-create-or-edit-hosted-providers"></a>要创建或编辑托管提供程序

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**联盟和外部访问**，然后单击**SIP 联盟提供程序**。

4.  如果您需要创建新的托管提供程序，请单击**新建**，然后单击**托管提供程序**。

5.  如果您需要编辑托管提供程序的列表的一个条目，请选择一个托管提供程序，单击**编辑**，然后单击**显示详细信息**。

6.  在**编辑 SIP 联盟提供程序**页上，您可以键入或编辑以下设置：
    
      - **启用与此提供程序通信**   选择此设置允许与此提供程序的用户的通信。
    
      - **提供程序名称：**   必需的属性，类型为其提供程序的名称将反映在 SIP 联盟提供商的列表。
    
      - **访问边缘服务 (FQDN):**   必需的属性，键入您要配置的托管提供程序的访问边缘服务的完全限定的域名。 此信息应由托管提供程序提供，且如果宿主提供程序托管提供商访问边缘服务的 fqdn 进行了更改只应被更改。
    
      - **默认验证级别：**   默认设置，**允许用户与使用此提供程序其联系人列表上的人进行通信**将限制到的已接受和联系人列表中联系人通信。
        
        选择**允许用户与任何人使用此提供程序通信**中删除的限制，您必须已收到并接受联系人邀请。 此设置不会限制谁可以与您联系从托管提供程序的网络。

7.  当您完成配置设置，单击**提交**保存，，或单击**取消**以放弃更改。


## <a name="see-also"></a>另请参阅


[配置策略以控制公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


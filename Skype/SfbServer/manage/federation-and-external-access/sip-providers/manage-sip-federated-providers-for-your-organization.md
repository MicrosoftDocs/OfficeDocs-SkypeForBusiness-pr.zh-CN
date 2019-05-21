---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何为 SIP 联合提供商的用户配置支持。
ms.openlocfilehash: ee16ec8953a722a86838f710fdf92cb9b2ce5f36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303961"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>在 Skype for Business Server 中管理你的组织的 SIP 联合提供商

若要为 SIP 联合提供商的用户配置支持, 你需要执行以下操作:

  - 配置一个或多个外部用户访问策略以支持与 SIP 联合提供者联系人通信

  - 指定要支持的托管提供商

  - 指定要支持的公共 IM 提供商

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建或编辑公共 SIP 联合提供商

公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共提供商提供的 IM 服务的用户进行通信。

Skype for business 服务器具有用于即时消息的公共提供商配置。 每个公共提供程序均使用提供程序的边缘服务器完全限定的域名进行配置, 默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供商的人员进行通信**。

默认设置是未启用任何公共提供程序。 在启用公共提供程序之前, 应完成许可证协议和预配工作。 你可以先启用提供程序, 然后再完成授权和预配工作。 在完成先决条件工作之前, 用户将无法与这些提供商上的联系人进行通信。 有关授权和设置公共提供程序的详细信息, 请参阅[配置控制公共用户](../external-access-policies/configure-policies-to-control-public-user-access.md)访问的策略。

使用以下过程创建或编辑公共提供程序。


### <a name="to-create-or-edit-public-providers"></a>创建或编辑公共提供程序

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 " **SIP 联合提供商**"。

4.  如果需要创建新的公共提供商, 请单击 "**新建**", 然后单击 "**公共提供商**"。

5.  如果需要从公共提供商列表中编辑条目, 请选择公共提供商, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

6.  在 "**编辑 SIP 联合提供商**" 页面上, 您可以键入或编辑以下设置:
    
      - **启用与此提供商**   的通信选择此设置将启用与此提供商的用户的即时消息。
    
      - **提供程序名称:**   "必需" 属性键入提供程序的名称, 因为它将反映在 SIP 联合提供程序的列表中。
    
      - **Access edge 服务 (FQDN):**   一个必需的属性, 键入要配置的提供程序的访问边缘服务的完全限定的域名。 此信息以默认项的形式提供, 仅当公共提供程序对公共提供程序的访问边缘服务的 FQDN 进行更改时, 才应更改此信息。
    
      - **默认验证级别:**   默认设置,**允许用户与使用此提供商的联系人列表中的人员进行通信**, 将对您已接受的联系人和您的联系人列表中的联系人进行通信。
        
        选择 "**允许用户通过此提供商与所有人通信**", 将删除您必须收到并接受的联系人邀请的限制。 此设置不会限制可以通过公共提供商的网络与您联系的人员。

7.  配置设置完成后, 单击 "**提交**" 以保存, 或单击 "**取消**" 放弃更改。

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建或编辑托管 SIP 联合提供商

托管提供商即时消息 (IM) 连接使组织中的用户能够使用 IM 与托管提供商提供的 IM 服务的用户进行通信。

每个托管提供程序均使用提供程序的边缘服务器完全限定的域名进行配置, 默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供程序的人员进行通信**。

使用以下过程创建或编辑托管提供程序。

### <a name="to-create-or-edit-hosted-providers"></a>创建或编辑托管提供商

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 " **SIP 联合提供商**"。

4.  如果需要创建新的托管提供商, 请单击 "**新建**", 然后单击 "**托管提供商**"。

5.  如果需要从托管提供商列表中编辑条目, 请选择托管提供商, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

6.  在 "**编辑 SIP 联合提供商**" 页面上, 您可以键入或编辑以下设置:
    
      - **启用与此提供商**   的通信选择此设置可启用与此提供商的用户的通信。
    
      - **提供程序名称:**   "必需" 属性键入提供程序的名称, 因为它将反映在 SIP 联合提供程序的列表中。
    
      - **Access edge 服务 (FQDN):**   一个必需的属性, 键入你要配置的托管提供程序的访问边缘服务的完全限定的域名。 此信息应由托管提供程序提供, 并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时, 才应更改此信息。
    
      - **默认验证级别:**   默认设置,**允许用户与使用此提供商的联系人列表中的人员进行通信**, 将对您已接受的联系人和您的联系人列表中的联系人进行通信。
        
        选择 "**允许用户通过此提供商与所有人通信**", 将删除您必须收到并接受的联系人邀请的限制。 此设置不限制可以通过托管提供商的网络与您联系的人员。

7.  配置设置完成后, 单击 "**提交**" 以保存, 或单击 "**取消**" 放弃更改。


## <a name="see-also"></a>另请参阅


[配置控制公共用户访问的策略](../external-access-policies/configure-policies-to-control-public-user-access.md)

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


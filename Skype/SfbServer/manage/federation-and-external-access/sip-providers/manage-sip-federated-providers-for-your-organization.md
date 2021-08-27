---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 了解如何配置对 SIP 联盟提供程序用户的支持。
ms.openlocfilehash: 552f0971685dd62dd89a27e03c62d0617b6c01d7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612301"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>在组织中管理组织的 SIP 联盟Skype for Business Server

要配置对 SIP 联盟提供程序用户的支持，需要执行以下操作：

  - 配置一个或多个外部用户访问策略来支持与 SIP 联盟提供程序联系人进行通信

  - 指定要支持哪些托管提供程序

  - 指定要支持哪些公共 IM 提供程序

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>在服务中创建或编辑公共 SIP 联盟Skype for Business Server

公共即时消息 (IM) 连接使贵组织的用户能够使用 IM 与公共提供商提供的 IM 服务的用户进行通信。

Skype for Business Server具有即时消息的公共提供程序配置。 每个公共提供程序均使用提供程序的边缘服务器完全限定域名和默认验证级别“仅允许用户与其联系人列表中使用此提供程序的人员进行通信”进行配置。

作为默认设置，将不启用任何公共提供程序。 您应先完成许可协议和设置工作，然后再启用公共提供程序。 您可以先启用提供程序，然后再完成许可和设置工作。 在完成首要工作之前，用户将无法与这些提供程序的联系人进行通信。 有关公共提供商的许可和设置的详细信息，请参阅配置 [策略以控制公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。

使用以下过程可创建或编辑公共提供程序。


### <a name="to-create-or-edit-public-providers"></a>创建或编辑公共提供程序

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。

4.  如果您需要创建新的公共提供程序，请单击“新建”，然后单击“公共提供程序”。

5.  如果您需要编辑公共提供程序列表中的条目，请选择一个公共提供程序，单击“编辑”，然后单击“显示详细信息”。

6.  在“编辑 SIP 联盟提供程序”页上，可以键入或编辑以下设置：
    
      - **允许与此提供程序进行通信**   选择此设置可为此提供程序的用户启用 IM。
    
      - **提供程序名称**   必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。
    
      - **访问边缘服务 (FQDN)**    必需属性，键入您正在配置的提供程序的访问边缘服务的完全限定域名。此信息作为默认项提供，并且只应在公共提供程序更改其访问边缘服务的 FQDN 时被更改。
    
      - **默认验证级别**   默认设置“允许用户与其联系人列表中使用此提供程序的人员进行通信”将只允许与您接受的且位于您的联系人列表中的联系人进行通信。
        
        选择“允许用户与使用此提供程序的每个人通信”将去除您必须接收和接受联系人邀请的限制。此设置不会对可从公共提供程序网络与您联系的人员进行限制。

7.  配置完这些设置后，请单击“提交”以进行保存，或单击“取消”以放弃更改。

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>在网站创建或编辑托管 SIP 联盟Skype for Business Server

托管提供商即时消息 (IM) 连接使贵组织的用户能够使用 IM 与宿主提供商提供的 IM 服务的用户进行通信。

使用提供程序的边缘服务器的完全限定域名以及默认验证级别 **仅允许用户与其联系人列表上使用此提供程序的人员进行通信** 来配置每个托管提供程序。

使用以下过程可创建或编辑托管提供程序。

### <a name="to-create-or-edit-hosted-providers"></a>创建或编辑托管提供程序

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。

4.  如果您需要创建一个新的托管提供程序，请单击“新建”，然后单击“托管提供程序”。

5.  如果您需要编辑托管提供程序列表上的一个条目，请选择一个托管提供程序，单击“编辑”，然后单击“显示详细信息”。

6.  在“编辑 SIP 联盟提供程序”页面上，您可以键入或编辑下列设置：
    
      - **允许与此提供程序进行通信**   选择此设置将允许与此提供程序的用户通信。
    
      - **提供程序名称**   必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。
    
      - **访问边缘服务(FQDN):**    这是一个必需属性，键入您正在配置的托管提供程序的访问边缘服务的完全限定域名。此信息应由托管提供程序提供，并且只应在托管提供程序对托管提供程序处的访问边缘服务的 FQDN 进行了更改时才改变。
    
      - **默认验证级别:**    默认设置“允许用户与其联系人列表上使用此提供程序的人员进行通信”将通信限制在您已接受并位于您的联系人列表中的联系人。
        
        选择“允许用户与所有使用此提供程序的人员通信”可取消您必须收到并接受联系人邀请的限制。此设置不限制可从托管提供程序的网络与您联系的人。

7.  当您配置完设置后，单击“提交”进行保存，或单击“取消”放弃所做的更改。


## <a name="see-also"></a>另请参阅


[配置策略以控制公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)

[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


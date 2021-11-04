---
title: 配置策略以控制公共用户访问
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: 通过公共即时消息 (IM) 连接，您的组织中的用户可以使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户进行通信。
ms.openlocfilehash: 2482270d27843b546246e11fb1bcadcc45c900da
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774952"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>配置策略以控制公共用户访问Skype for Business Server

公共即时消息 (IM) 连接使贵组织的用户能够使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户进行通信。 您可以配置一个或多个外部用户访问策略，以控制公共用户能否与内部用户Skype for Business Server协作。 公共即时消息连接是一项新增功能，依赖于部署和用户的配置。 它还取决于在公共 IM 提供商处设置服务。 

若要控制公共用户访问，可以在全局、站点和用户级别配置策略。 Skype for Business Server一个策略级别应用的策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。

对于 IM 邀请，响应取决于客户端软件。除非外部发件人被用户配置的规则（即，用户客户端的“允许”和“阻止”列表中的设置）显式阻止，否则将接受请求。此外，如果用户选择阻止来自其“允许”列表之外的用户的所有 IM，也可以阻止 IM 邀请。



> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制公共用户访问的策略。 但是，只有为组织启用联盟后，配置的策略才会生效。 有关启用联盟的详细信息，请参阅 [启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 此外，如果指定用于控制公共用户访问的用户策略，则此策略仅适用于启用了 Skype for Business Server并配置为使用该策略的用户。 有关指定可登录到 Skype for Business Server 用户的详细信息，请参阅分配[外部用户访问策略](assign-an-external-user-access-policy.md)。


使用以下过程来配置策略，以支持一个或多个公共 IM 提供商的用户进行访问。

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>配置外部访问策略以支持公共用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”页上，执行下列操作之一：
    
      - 要将全局策略配置为支持公共用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。
    
      - 要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。
    
      - 要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnablePublicUsers** 代表启用公共用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

5.  （可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。

6.  执行以下操作之一：
    
      - 要为策略启用公共用户访问，请选中“启用与公共用户的通信”复选框。
    
      - 要为策略禁用公共用户访问，请清除“启用与公共用户的通信”复选框。

7.  单击“提交”。

要启用公共用户访问，还必须在组织中启用对联盟的支持。 有关详细信息，请参阅[Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md)。

如果这是一个用户策略，您还必须将该策略应用到您希望能与公共用户协作的公共用户。 


## <a name="see-also"></a>另请参阅

[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

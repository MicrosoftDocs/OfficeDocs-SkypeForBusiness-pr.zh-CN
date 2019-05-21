---
title: 配置策略以控制公共用户访问
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic 即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信。
ms.openlocfilehash: 230c3405a9d0a551758bee63fae8f927fdc5af19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280157"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>在 Skype for Business Server 中配置用于控制公共用户访问的策略

公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信。 配置一个或多个外部用户访问策略, 以控制公共用户是否可以与内部 Skype for Business 服务器用户进行协作。 公共即时消息连接是一种附加的功能, 可依赖于部署和用户的配置。 它还取决于在公共 IM 提供商处提供的服务。 

若要控制公共用户访问, 可以在全局、网站和用户级别配置策略。 在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。 Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

对于 IM 邀请, 响应取决于客户端软件。 除非由用户配置的规则明确阻止外部发件人 (即用户的客户端**允许**和**阻止**名单中的设置), 否则将接受该请求。 此外, 如果用户将阻止来自不在其**允许**列表中的用户的所有 IM, 则可以阻止 IM 邀请。



> [!NOTE]  
> 你可以配置策略来控制公共用户访问, 即使你没有为组织启用联盟。 但是, 仅当你的组织启用了联合身份验证时, 你配置的策略才有效。 有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 此外, 如果你指定用于控制公共用户访问的用户策略, 则该策略仅适用于已启用 Skype for business 服务器的用户, 并且配置为使用该策略。 有关指定可登录到 Skype for Business 服务器的公共用户的详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。


使用以下过程配置策略以支持一个或多个公共 IM 提供商的用户访问。

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>将外部访问策略配置为支持公共用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 页面上, 执行下列操作之一:
    
      - 若要将全局策略配置为支持公共用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。
    
      - 若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。 在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。
    
      - 若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。 在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnablePublicUsers**为公共用户启用通信的用户策略)。
    
      - 若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要为策略启用公共用户访问权限, 请选中 "**启用与公共用户的通信**" 复选框。
    
      - 若要禁用该策略的公共用户访问权限, 请清除 "**启用与公共用户的通信**" 复选框。

7.  单击“**提交**”。

若要启用公共用户访问, 还必须在组织中启用联盟支持。 有关详细信息, 请参阅[在 Skype For Business 服务器中配置用于控制联盟用户访问的策略](configure-policies-to-control-federated-user-access.md)。

如果这是用户策略, 你还必须将策略应用于你希望能够与公共用户协作的公共用户。 


## <a name="see-also"></a>另请参阅

[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

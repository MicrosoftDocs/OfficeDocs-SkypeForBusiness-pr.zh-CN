---
title: 配置策略以控制公共用户访问
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ublic 即时消息 (IM) 连接，您的组织中的用户，可以使用 IM 与 IM 服务提供的公共 IM 服务提供商的用户进行通信。
ms.openlocfilehash: 8ad406957d50f44bd8cee9465549ff86af9a3e6b
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222868"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>配置策略以控制公共用户访问中 Skype 业务服务器

公共即时消息 (IM) 连接，您的组织中的用户，可以使用 IM 与 IM 服务提供的公共 IM 服务提供商的用户进行通信。 您配置一个或多个外部用户访问策略以控制公共用户可以与内部 Skype 业务 Server 用户进行协作。 公共即时消息连接是一个新增了的功能，依赖于您部署和用户的配置。 它还取决于在公共 IM 提供商的服务的设置。 

若要控制公共用户访问，可以配置策略在全局、 站点和用户级别。 Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

对于 IM 邀请，响应取决于客户端软件。 除非外部发件人被明确阻止用户配置的规则 （即，设置在用户的客户端**允许**和**阻止**名单），请求将被接受。 此外，如果用户选择阻止来自未在他/她**允许**名单的用户的所有 IM，则可以阻止 IM 邀请。



> [!NOTE]  
> 即使您没有为组织启用联盟，您可以配置策略以控制公共用户访问。 但是，您配置的策略实际上是将仅当已为组织启用联盟。 有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。 此外，如果您指定的用户策略以控制公共用户访问，该策略仅适用于 Skype 业务服务器启用和配置为使用该策略的用户。 有关指定可以登录到 Skype 业务服务器的公共用户的详细信息，请参阅[外部用户访问策略分配](assign-an-external-user-access-policy.md)。


使用以下过程来配置策略以支持一个或多个公共 IM 提供商的用户访问。

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>若要配置外部访问策略以支持公共用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**外部访问策略**。

4.  在**外部访问策略**页上，执行以下任一操作：
    
      - 要配置全局策略以支持公共用户访问，请单击该全局策略，单击**编辑**，然后单击**显示详细信息**。
    
      - 若要创建新的站点策略，单击**新建**，然后单击**站点策略**。 在**选择站点**单击列表中的相应站点，然后单击**确定**。
    
      - 若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。 在**新外部访问策略**中，创建一个唯一的名称，在**名称**字段，该值指示哪些用户策略介绍 (例如， **EnablePublicUsers**用户策略启用的公共用户的通信的)。
    
      - 若要更改现有策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。

5.  （可选）如果您想要添加或编辑说明，请在**说明**指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要启用公共用户访问的策略，请选中**启用与公共用户的通信**复选框。
    
      - 若要禁用公共用户访问的策略，请清除**启用与公共用户的通信**复选框。

7.  单击“**提交**”。

要启用公共用户访问，您还必须在组织中启用联合身份验证的支持。 有关详细信息，请参阅[配置策略以控制联盟用户访问中的业务服务器 Skype](configure-policies-to-control-federated-user-access.md)。

如果这是用户策略，您必须向您希望能够与公共用户进行协作的公共用户应用策略。 


## <a name="see-also"></a>另请参阅

[管理您的组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

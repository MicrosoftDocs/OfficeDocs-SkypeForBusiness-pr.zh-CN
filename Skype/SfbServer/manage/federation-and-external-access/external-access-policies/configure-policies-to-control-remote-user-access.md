---
title: 配置策略以控制远程用户访问
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以配置一个或多个外部用户访问策略以控制是否远程用户可以与内部 Skype 业务 Server 用户进行协作。 若要控制远程用户访问，可以配置策略在全局、 站点和用户级别。
ms.openlocfilehash: 3355ee979bdf0e5be954aea69f365084271223fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920451"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>配置策略以控制远程用户访问在 Skype 业务服务器

您可以配置一个或多个外部用户访问策略以控制是否远程用户可以与内部 Skype 业务 Server 用户进行协作。 若要控制远程用户访问，可以配置策略在全局、 站点和用户级别。 网站策略将覆盖全局策略和用户策略将覆盖站点和全局策略。 有关您可以配置的策略的类型的详细信息，请参阅[Managing 联盟和外部访问 Skype 业务服务器](../managing-federation-and-external-access.md)。 Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

> [!NOTE]  
> 即使您没有为组织启用远程用户访问，您可以配置策略以控制远程用户访问。 但是，您配置的策略实际上是将仅当已为组织启用远程用户访问。 此外，如果您指定一个用户策略控制远程用户访问，该策略仅适用于 Skype 业务服务器启用和配置为使用该策略的用户。 有关指定可以登录到 Skype 业务服务器从远程位置的用户详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。

使用以下过程配置要用于控制远程用户访问的每个外部访问策略。


> [!NOTE]  
> 此过程介绍如何配置策略仅以启用与远程用户的通信，但您配置为支持远程用户访问的每个策略还可以配置联盟的用户访问和公共用户访问。 有关配置策略以支持联盟的用户的详细信息，请参阅[配置策略以控制联盟用户访问中的业务服务器 Skype](configure-policies-to-control-federated-user-access.md)。 有关配置策略以支持公共用户的详细信息，请参阅[管理 SIP 联盟提供程序中的业务服务器 Skype 的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>若要配置外部访问策略以支持远程用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**外部访问策略**。

4.  在**外部访问策略**页上，执行以下任一操作：
    
      - 要配置全局策略以支持远程用户访问，请单击该全局策略，单击**编辑**，然后单击**显示详细信息**。
    
      - 若要创建新的站点策略，单击**新建**，然后单击**站点策略**。 在**选择站点**单击列表中的相应站点，然后单击**确定**。
    
      - 若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。 在**新外部访问策略**中，创建一个唯一的名称，在**名称**字段，该值指示哪些用户策略介绍 (例如， **EnableRemoteUsers**用户策略启用的远程用户的通信的)。
    
      - 若要更改现有策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。

5.  （可选）如果您想要添加或编辑说明，请在**说明**指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要启用远程用户访问的策略，请选中**启用与远程用户的通信**复选框。
    
      - 若要禁用远程用户访问的策略，请清除**启用与远程用户的通信**复选框。

7.  单击“**提交**”。

若要启用远程用户访问，您还必须在组织中启用对远程用户访问的支持。 有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是用户策略，您必须向您想要能够远程连接的用户应用策略。 有关详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。

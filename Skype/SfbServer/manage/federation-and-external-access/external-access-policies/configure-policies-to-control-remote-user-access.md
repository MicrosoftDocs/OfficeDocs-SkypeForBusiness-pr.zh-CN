---
title: 配置策略以控制远程用户访问
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 配置一个或多个外部用户访问策略，以控制远程用户能否与内部用户Skype for Business Server协作。 若要控制远程用户访问，可以在全局、站点和用户级别配置策略。
ms.openlocfilehash: 205ff2cf39a28630677390d5ee39e4dfe4beffad8be3155dd686d50fede40865
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309371"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>配置策略以控制远程用户访问Skype for Business Server

配置一个或多个外部用户访问策略，以控制远程用户能否与内部用户Skype for Business Server协作。 若要控制远程用户访问，可以在全局、站点和用户级别配置策略。 站点策略将覆盖全局策略，而用户策略将覆盖站点策略和全局策略。 有关可以配置的策略类型的详细信息，请参阅 Managing federation [and external access to Skype for Business Server](../managing-federation-and-external-access.md)。 Skype for Business Server一个策略级别应用的策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。

> [!NOTE]  
> 即使没有为组织启用远程用户访问，也可以配置策略来控制远程用户访问。 但是，只有为组织启用远程用户访问后，配置的策略才会生效。 此外，如果指定用户策略来控制远程用户访问，则此策略仅适用于启用了远程Skype for Business Server配置为使用该策略的用户。 有关指定可以从远程位置登录Skype for Business Server的详细信息，请参阅分配[外部用户访问策略](assign-an-external-user-access-policy.md)。

按照以下过程配置要用于控制远程用户访问的每个外部访问策略。


> [!NOTE]  
> 此过程描述如何配置策略以便仅启用与远程用户的通信，但配置为支持远程用户访问的每个策略也可以配置联盟用户访问和公共用户访问。 有关配置策略以支持联盟用户的详细信息，请参阅 Configure [policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md)。 有关配置策略以支持公共用户的详细信息，请参阅管理组织中组织的 SIP 联盟[Skype for Business Server。](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>配置外部访问策略以支持远程用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”页上，执行下列操作之一：
    
      - 要将全局策略配置为支持远程用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。
    
      - 要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。
    
      - 要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableRemoteUsers** 代表启用远程用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

5.  （可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用远程用户访问，请选中“启用与远程用户的通信”复选框。
    
      - 要为策略禁用远程用户访问，请清除“启用与远程用户的通信”复选框。

7.  单击“提交”。

要启用远程用户访问，还必须在组织中启用对远程用户访问的支持。 有关详细信息，请参阅启用 [或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是一个用户策略，则还必须将此策略应用于希望其可以进行远程连接的用户。 有关详细信息，请参阅 [分配外部用户访问策略](assign-an-external-user-access-policy.md)。

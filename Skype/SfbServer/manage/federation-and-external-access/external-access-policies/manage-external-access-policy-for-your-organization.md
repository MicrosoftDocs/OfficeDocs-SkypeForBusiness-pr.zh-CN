---
title: 管理组织的外部访问策略
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一个或多个边缘服务器后，必须启用组织支持的外部访问类型。
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818273"
---
# <a name="manage-external-access-policy-for-your-organization"></a>管理组织的外部访问策略

部署一个或多个边缘服务器后，必须启用组织支持的外部访问类型。

默认情况下，没有配置任何可支持外部用户访问的策略，包括远程用户访问权限、联盟用户访问权限，即使你已启用组织的外部用户访问支持。 若要控制外部用户访问的使用，必须配置一个或多个策略，指定每个策略支持的外部用户访问类型。 以下策略作用域可用于创建和配置。 默认情况下，创建全局策略，但不能删除。

  - **全局策略**   当你部署 Edge 服务器时，将创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。 全局策略适用于组织中的所有用户，但网站策略和用户策略替代全局策略。 如果您删除全局策略，则不会将其删除。 而是将其重置为默认设置。

  - **网站策略**   您可以创建和配置一个或多个网站策略，以限制对特定网站的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如，如果在全局策略中启用 "远程用户访问"，则可以指定一个网站策略，该策略可禁用特定网站的远程用户访问。 默认情况下，网站策略应用于该网站的所有用户，但你可以将用户策略分配给用户以替代网站策略设置。

  - **用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。 用户策略中的配置替代全局和网站策略，但仅适用于为其分配用户策略的特定用户。 例如，如果在全局策略和网站策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建用户策略，则必须将其应用于一个或多个用户，然后它才会生效。


> [!IMPORTANT]  
> 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


这些选项包括以下类型的外部访问：

  - ****   如果你希望支持用户对联盟伙伴域的访问权限，请启用与联盟用户的通信。 此设置将用户配置为与其他 SIP 联盟域以及托管提供商（如 Microsoft Office 365）进行通信的能力。 


  - **启用与远程用户**   的通信如果你希望你的组织中的用户（如出差的远程办公和用户）能够通过 Internet 连接到 Skype for business 服务器，请启用此选项。

  - ****   如果希望内部用户能够与公共 IM 提供商联系人通信，请启用与公共用户的通信。
   

> [!NOTE]  
> 除了启用外部用户访问支持外，你还必须配置策略，以控制在你的组织中使用外部用户访问，然后再向用户提供任何类型的外部用户访问权限。 有关创建、配置和应用外部用户访问策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。



**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 你可以使用 Skype for Business Server Management Shell 和**CsExternalAccessPolicy** cmdlet 查看外部访问策略。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 
    
    若要查看有关所有外部访问策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
    `Get-CsExternalAccessPolicy`
    
    此命令会返回类似下列信息：
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```

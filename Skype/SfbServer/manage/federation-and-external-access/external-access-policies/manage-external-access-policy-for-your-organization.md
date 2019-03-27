---
title: 管理组织的外部访问策略
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 后部署一个或多个边缘服务器，必须启用将为您的组织支持的外部访问的类型。
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892876"
---
# <a name="manage-external-access-policy-for-your-organization"></a>管理组织的外部访问策略

后部署一个或多个边缘服务器，必须启用将为您的组织支持的外部访问的类型。

默认情况下，没有配置为支持外部用户访问，即使您已为您的组织已启用外部用户访问支持包括远程用户访问、 联盟的用户访问的策略。 若要控制外部用户访问的使用，必须配置一个或多个策略，指定类型的外部用户访问支持的每个策略。 为创建和配置提供了以下策略作用域。 默认情况下，全局策略创建后，但不能删除。

  - **全局策略**   部署边缘服务器时创建的全局策略。 默认情况下，没有外部用户访问选项被启用在全局策略。 若要支持外部用户访问，在全局级别，您可以配置全局策略以支持一个或多个类型的外部用户访问选项。 全局策略应用于组织中的所有用户，但网站策略和用户策略将覆盖全局策略。 如果您删除全局策略，则不要删除它。 相反，您其重置为默认设置。

  - **站点策略**   可以创建并配置一个或多个站点策略，以限制到特定站点的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如，如果您启用远程用户访问，在全局策略，您可能指定禁用特定站点的远程用户访问的站点策略。 默认情况下的站点策略应用于所有用户的网站，但可以将用户策略分配给用户将会覆盖站点策略设置。

  - **用户策略**   可以创建并配置一个或多个用户策略，以限制为特定用户的远程用户访问的支持。 在用户策略重写全局和站点策略，但仅限于为其分配的用户策略的特定用户的配置。 例如，如果您启用远程用户访问中的全局策略和站点策略，您可能指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果您创建的用户策略，您必须将它应用于一个或多个用户才能生效。


> [!IMPORTANT]  
> 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


这些选项包括以下类型的外部访问：

  - **启用与联盟用户的通信**   启用此项如果您想要支持联盟的伙伴域用户访问。 此设置可配置的用户进行通信，与其他 SIP 联盟域，以及托管提供程序，如 Microsoft Office 365 的功能。 


  - **启用与远程用户的通信**   启用此选项，如果您希望您的组织防火墙，如远程办公和用户在旅行，以便能够通过 Internet 业务服务器连接到 Skype 之外的用户。

  - **启用与公共用户的通信**   启用此选项，如果您希望内部用户可以与公共 IM 提供程序联系人进行通信。
   

> [!NOTE]  
> 除了启用外部用户访问支持，您还必须配置策略以控制您的组织中的外部用户访问使用任何类型的外部用户访问之前对用户可用。 有关创建、 配置和外部用户访问的应用策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。



**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 您可以通过使用 Skype 业务 Server 命令行管理程序和**Get-csexternalaccesspolicy** cmdlet 查看外部访问策略。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 
    
    若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 ENTER:
    
    `Get-CsExternalAccessPolicy`
    
    此命令会返回类似下列信息：
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```

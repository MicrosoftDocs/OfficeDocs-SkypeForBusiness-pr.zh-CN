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
description: 部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221656"
---
# <a name="manage-external-access-policy-for-your-organization"></a>管理组织的外部访问策略

部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。

默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，并指定每个策略支持的外部用户访问类型。可创建和配置以下策略范围。默认情况下，将创建全局策略且无法被删除。

  - **全局策略**   在部署 Edge 服务器时创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 要支持全局级别的外部用户访问，请将全局策略配置为支持一种或多种外部用户访问选项。 全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。 如果删除全局策略，则不要将其移除。 相反，将其重置为默认设置。

  - **站点策略**   可创建和配置一个或多个站点策略，以将外部用户访问限制到指定站点。 站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。 例如，如果在全局策略中启用远程用户访问，则可以指定禁用特定站点的远程用户访问的站点策略。 默认情况下，站点策略应用于该站点的所有用户，但可以将用户策略分配给用户以覆盖站点策略设置。

  - **用户策略**   可以创建和配置一个或多个用户策略，以将远程用户访问支持限制到指定用户。 用户策略中的配置将覆盖全局和站点策略，但仅适用于为其分配策略的特定用户。 例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。


> [!IMPORTANT]  
> 在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。


这些选项包括以下类型的外部访问：

  - **启用与联盟用户的通信**   如果要支持用户对联合伙伴域的访问，则启用此选项。 此设置配置用户与其他 SIP 联盟域进行通信的能力，以及 Microsoft 365 或 Office 365 等托管提供商。 


  - **启用与远程用户的通信**   如果您希望组织中位于防火墙之外的用户（如远程工作者和正在旅行的用户）能够通过 Internet 连接到 Skype for Business，请启用此选项。

  -  **启用与公共用户的通信**   如果您希望内部用户能够与公共 IM 提供程序联系人进行通信，请启用此选项。
   

> [!NOTE]  
> 除了启用外部用户访问支持外，还必须在用户可以使用任何类型的外部用户访问之前，配置策略以控制组织中外部用户访问的使用。 有关为外部用户访问创建、配置和应用策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。



**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 可以使用 Skype for Business Server Management Shell 和 **CsExternalAccessPolicy** cmdlet 查看外部访问策略。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 
    
    若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 Enter：
    
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

---
title: 验证域中的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要验证在步骤1：准备架构中完成的域准备的复制，必须从 Skype for Business Server Management Shell Lync Server Management Shell 运行 cmdlet。 若要运行 Windows PowerShell cmdlet，请登录到属于你已准备的域成员的计算机，以及作为域管理员组的成员。 请执行下列操作：
ms.openlocfilehash: fffe6a227ad8a0dd0214080b21d743382845478b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794761"
---
# <a name="verify-replication-in-the-domain"></a>验证域中的复制
 
若要验证在**步骤1：准备架构**中完成的域准备的复制，必须从 Skype For Business Server Management Shell Lync Server management shell 运行 cmdlet。 若要运行 Windows PowerShell cmdlet，请登录到属于你已准备的域成员的计算机，以及作为域管理员组的成员。 请执行下列操作：
  
1. 启动 Skype for Business 服务器命令行管理程序：单击 "**开始**"，单击 "**所有程序**"，单击 " **skype**for Business"，然后单击 " **skype for business 服务器管理外壳**"。
    
2. 在 Windows PowerShell 中，键入以下内容：
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例如：
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > 参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。 如果你的设置存储在系统容器中（这与未将全局设置迁移到配置容器的升级部署的典型设置），请在 Active Directory 域服务林的根中定义域控制器。 如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。 如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。 
  
    如果不指定 Domain 参数，则将该值设置为本地域。 如果域准备已成功，则此 cmdlet 将返回 **LC_DOMAIN_SETTINGS_STATE_READY** 的值。
    


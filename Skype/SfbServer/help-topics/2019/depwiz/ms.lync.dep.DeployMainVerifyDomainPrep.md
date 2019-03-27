---
title: 验证域中的复制
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 要验证复制在步骤 1 中完成的域准备： 准备架构，它所需从 Skype 的业务服务器管理命令行管理程序 Lync Server Management Shell 中运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到成员已经准备好的域的 Domain Admins 组的成员以及的计算机。 请执行下列操作：
ms.openlocfilehash: 8adec80d9f0874e395150941cada02f58099bce9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884517"
---
# <a name="verify-replication-in-the-domain"></a>验证域中的复制
 
若要验证中完成域准备的复制**步骤 1： 准备架构**，需从 Skype 的业务服务器管理命令行管理程序 Lync Server Management Shell 中运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到成员已经准备好的域的 Domain Admins 组的成员以及的计算机。 请执行下列操作：
  
1. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。
    
2. 在 Windows PowerShell 中，键入以下命令：
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例如：
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > 参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。 如果您的设置存储在系统容器 （这是不过全局设置迁移到配置容器的升级部署典型） 中，您的 Active Directory 域服务林根中定义的域控制器。 如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。 如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。 
  
    如果不指定 Domain 参数，则将该值设置为本地域。 如果域准备已成功，则此 cmdlet 将返回 **LC_DOMAIN_SETTINGS_STATE_READY** 的值。
    


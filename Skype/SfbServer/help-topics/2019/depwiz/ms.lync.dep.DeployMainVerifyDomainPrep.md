---
title: 验证域中的复制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 若要验证复制步骤 1 中完成的域准备：准备架构，需要从 Skype for Business Server 命令行管理程序 Lync Server 命令行管理程序 运行 cmdlet。 要运行 Windows PowerShell cmdlet，请以 Domain Admins 组成员的身份登录到作为已准备的域成员的计算机。 请执行以下操作：
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801652"
---
# <a name="verify-replication-in-the-domain"></a>验证域中的复制
 
若要验证复制步骤 **1** 中完成的域准备：准备架构，需要从 Skype for Business Server 命令行管理程序 Lync Server 命令行管理程序 运行 cmdlet。 要运行 Windows PowerShell cmdlet，请以 Domain Admins 组成员的身份登录到作为已准备的域成员的计算机。 请执行以下操作：
  
1. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 在Windows PowerShell中，键入以下内容：
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例如：
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > 参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。 如果您的设置存储在系统容器 (这一点在尚未将全局设置迁移到配置容器) 的升级部署中是典型的，则定义 Active Directory 域服务林的根目录中的域控制器。 如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。 如果不指定此参数，此 cmdlet 将假定设置存储在"配置"容器中，并引用 Active Directory 中的任意域控制器。 
  
    如果不指定 Domain 参数，则将该值设置为本地域。 如果域准备已成功，则此 cmdlet 将返回 **LC_DOMAIN_SETTINGS_STATE_READY** 的值。
    


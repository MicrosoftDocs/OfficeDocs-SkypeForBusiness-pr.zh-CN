---
title: 验证域中的复制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 要验证复制的在第 1 步中完成域准备工作： 准备架构，有必要从 Skype 业务服务器管理外壳 Lync 服务器管理外壳程序运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到计算机所属的域已做好了准备，并作为域管理员组的成员。 请执行下列操作：
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a>验证域中的复制
 
要验证复制中完成域准备工作的**第 1 步： 准备架构**，有必要从 Skype 业务服务器管理外壳 Lync 服务器管理外壳程序运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到计算机所属的域已做好了准备，并作为域管理员组的成员。 请执行下列操作：
  
1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在 Windows PowerShell，键入以下命令：
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    例如：
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > 参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。 如果您的设置存储在系统容器 （此为典型与升级部署尚未迁移到配置容器的全局设置） 中，域控制器定义 Active Directory 域服务林的根目录中。 如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。 如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。 
  
    如果不指定 Domain 参数，则将该值设置为本地域。 此 cmdlet 返回值为**LC_DOMAIN_SETTINGS_STATE_READY** ，如果域准备成功。
    


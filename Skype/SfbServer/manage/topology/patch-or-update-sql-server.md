---
title: 在 Skype for Business Server 2015 中修补或更新 AlwaysOn 可用性组中的 SQL Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 摘要： 了解所需的其他步骤后您的修补程序或升级后端服务器中业务服务器的 Skype 的 AlwaysOn 可用性组的一部分。
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中修补或更新 AlwaysOn 可用性组中的 SQL Server
 
**摘要：**找出有关所需的其他步骤后的修补程序或升级后端服务器中业务服务器的 Skype 的 AlwaysOn 可用性组的一部分。
  
修补后端服务器的 AlwaysOn 可用性组的一部分后, 则必须重新发布拓扑结构。
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>修补或更新属于 AlwaysOn 可用性组的 SQL Server

1. 在你的一台或多台 Skype for Business 服务器上安装更新。
    
2. 在 Skype for Business 命令行管理程序中运行以下 PowerShell 命令（用被授予适当权限可向 SQL AlwaysOn 数据库应用更改的帐户登录），如下所述：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中，[sqlpool.contoso.com] 被替换为 AlwaysOn 可用性组的完全限定域名 (FQDN)。
    


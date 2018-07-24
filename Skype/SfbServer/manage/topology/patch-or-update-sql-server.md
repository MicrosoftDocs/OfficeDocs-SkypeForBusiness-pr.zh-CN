---
title: 修补程序或业务服务器更新 SQL Server 中 Skype AlwaysOn 可用性组
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 摘要： 了解有关所需的其他步骤后您修补程序或升级后端服务器 Skype 业务服务器中的 AlwaysOn 可用性组的一部分。
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982984"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="2dbc1-103">修补程序或业务服务器更新 SQL Server 中 Skype AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="2dbc1-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="2dbc1-104">**摘要：** 修补程序或升级后端服务器属于 Skype 业务服务器中的 AlwaysOn 可用性组后，请了解所需的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="2dbc1-105">修补后端服务器 AlwaysOn 可用性组的一部分后, 必须重新发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="2dbc1-106">修补或更新属于 AlwaysOn 可用性组的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2dbc1-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="2dbc1-107">在你的一台或多台 Skype for Business 服务器上安装更新。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="2dbc1-108">在 Skype for Business 命令行管理程序中运行以下 PowerShell 命令（用被授予适当权限可向 SQL AlwaysOn 数据库应用更改的帐户登录），如下所述：</span><span class="sxs-lookup"><span data-stu-id="2dbc1-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="2dbc1-109">其中，[sqlpool.contoso.com] 被替换为 AlwaysOn 可用性组的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2dbc1-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    


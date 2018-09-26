---
title: 迁移响应组
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 对于业务服务器 2019年池用户移动到 Skype 后，您可以迁移响应组。 迁移响应组包括复制代理组、 队列、 工作流、 音频文件，并将从旧部署的响应组联系人对象移动到业务服务器 2019年池 Skype。 迁移旧版响应组后，对响应组呼叫处理中为 Business Server 2019 池 Skype 的响应组应用程序。 由旧池不再处理响应组呼叫。
ms.openlocfilehash: bdff9b96b73e925fb68b4a2f9bebb9b23edb4b56
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028017"
---
# <a name="migrate-response-groups"></a>迁移响应组

对于业务服务器 2019年池用户移动到 Skype 后，您可以迁移响应组。 迁移响应组包括复制代理组、 队列、 工作流、 音频文件，并将从旧部署的响应组联系人对象移动到业务服务器 2019年池 Skype。 迁移旧版响应组后，对响应组呼叫处理中为 Business Server 2019 池 Skype 的响应组应用程序。 由旧池不再处理响应组呼叫。
  
> [!NOTE]
> 将所有用户都移动到业务服务器 2019年池 Skype 之前，您可以迁移响应组，尽管我们建议您先都移动所有用户。 具体而言，响应组代理的用户将不具有新功能完整的功能，直到他们会移动到 Skype 业务服务器 2019年池。 
  
迁移响应组之前，必须部署包括响应组应用程序的业务服务器 2019年池 Skype。 安装和部署企业语音时，默认情况下激活响应组应用程序。 您可以确保通过运行**Get-csservice ApplicationServer** cmdlet 安装了响应组应用程序。 
  
> [!NOTE]
> 在迁移旧版响应组之前，您可以在业务服务器 2019年池 Skype 创建新的 Skype 业务服务器 2019年响应组。 
  
若要迁移响应组从旧池中到 Skype 业务服务器 2019年，您可以运行**Move-csrgsconfiguration** cmdlet。 
  
> [!IMPORTANT]
> 响应组迁移 cmdlet 移动整个池的响应组配置。 不能选择要迁移的特定组、 队列或工作流。 
  
迁移响应组后，您需要使用 Skype 业务 Server Control Panel 或 Skype 业务 Server Management Shell cmdlet 验证所有代理组、 队列和工作流都已成功。 
  
迁移响应组时，不会删除旧版响应组。 在迁移后管理响应组时使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序，您可以看到旧版响应组和 Skype 业务服务器 2019年响应组。 您应更新仅适用于业务服务器 2019年响应组 Skype。 只是为了回滚保留旧的响应组。 
  
> [!CAUTION]
> 业务 Server Control Panel Skype 和业务 Server 命令行管理程序 Skype 迁移已完成并已经创建了新的响应组后，将显示旧和 Skype 业务服务器 2019年版本的每个响应组。 不要使用 Skype 业务 Server Control Panel 或 Skype 的业务 Server 命令行管理程序删除旧版响应组。 如果您删除一个，迁移过程中创建相应的响应组将停止工作。 停用旧池时，将删除旧版响应组。 
  
> [!IMPORTANT]
> 我们建议您执行操作不删除任何数据从以前部署之前停用池。 此外，我们强烈建议您在迁移后立即导出响应组。 如果应获取删除旧的响应组，您可以从要获得再次运行业务服务器 2019年响应组的 Skype 的备份中还原您的响应组。 
  
Skype 的业务服务器 2019年引入了一个称为**工作流类型**的新响应组功能。 **工作流类型**可以是**托管**或**非托管**。 所有响应组会都迁移与**工作流类型**设置为**非托管**和一个空的管理器列表。 
  
运行**Move-csrgsconfiguration** cmdlet 时，代理组、 队列、 工作流和音频文件将保留在旧池回滚为了中。 如果需要回滚到旧池中，但是，您需要运行**Move-csapplicationendpoint** cmdlet 以将联系对象移回旧池。 
  
迁移响应组配置下面的过程假定您具有旧池与业务服务器 2019年池的 Skype 之间一对一关系。 如果您计划合并或拆分池迁移和部署期间，您需要哪些旧池映射到业务服务器 2019年池的 Skype 的计划。
  
## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1. 登录到使用具有 RTCUniversalServerAdmins 组的成员或具有等效管理员权限的帐户的计算机上。
    
2. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。
    
3. 运行：
    
  ```
  Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
  ```

    例如：
    
  ```
  Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
  ```

4. 向业务服务器 2019年池 Skype 迁移响应组和代理后，代理用于登录和注销 URL 是业务服务器 2019 URL Skype，可从**工具**菜单。 提醒代理更新为新的 URL 的任何引用，如书签。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 验证响应组迁移

1. 登录到计算机 RTCUniversalReadOnlyAdmins 组的成员或是至少具有 CsViewOnlyAdministrator 角色成员的帐户。
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[打开 Skype 业务服务器 2019年管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左侧的导航窗格中，单击**响应组**。
    
4. 在**工作流**选项卡中，确认列表中包含旧环境中的所有工作流。 
    
5. 单击**队列**选项卡，并确认旧环境中的所有队列都包含在列表。 
    
6. 单击**组**选项卡，并确认旧环境中的所有代理组都包含在列表。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>若要使用 Skype 业务 Server 命令行管理程序验证响应组迁移

1. 登录到计算机 RTCUniversalReadOnlyAdmins 组的成员或是至少具有 CsViewOnlyAdministrator 角色成员的帐户。
    
2. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。
    
    有关以下 cmdlet 的详细信息，请运行：
    
  ```
  Get-Help <cmdlet name> -Detailed
  ```

3. 运行：
    
  ```
  Get-CsRgsAgentGroup
  ```

4. 确认旧环境中的所有代理组都包含在列表中。
    
5. 运行：
    
  ```
  Get-CsRgsQueue
  ```

6. 确认旧环境中的所有队列都包含在列表中。
    
7. 运行：
    
  ```
  Get-CsRgsWorkflow
  ```

8. 确认旧环境中的所有工作流都包含在列表中。
    


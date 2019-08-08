---
title: 迁移响应组
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 将用户移动到 Skype for business Server 2019 池后, 您可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后, 对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 不再通过旧版池处理对响应组的调用。
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237968"
---
# <a name="migrate-response-groups"></a>迁移响应组

将用户移动到 Skype for business Server 2019 池后, 您可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后, 对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 不再通过旧版池处理对响应组的调用。
  
> [!NOTE]
> 虽然你可以在将所有用户移动到 Skype for Business Server 2019 池之前迁移响应组, 但我们建议先移动所有用户。 特别是, 响应组代理的用户在移动到 Skype for business Server 2019 池之前不具有新功能的完整功能。 
  
在迁移响应组之前, 必须已部署包含响应组应用程序的 Skype for business Server 2019 池。 部署企业语音时, 将默认安装并激活 "响应组" 应用程序。 你可以通过运行**CsService-ApplicationServer** cmdlet 来确保响应组应用程序已安装。 
  
> [!NOTE]
> 在迁移传统的响应组之前, 您可以在 Skype for business Server 2019 池中创建新的 Skype for business Server 2019 响应组。 
  
若要将响应组从旧版池迁移到 Skype for business Server 2019, 请运行**CsRgsConfiguration** cmdlet。 
  
> [!IMPORTANT]
> 响应组迁移 cmdlet 移动整个池的响应组配置。 您不能选择要迁移的特定组、队列或工作流。 
  
迁移响应组后, 你需要使用 Skype for business 服务器控制面板或 Skype for Business Server Management Shell cmdlet 验证是否成功移动了所有代理组、队列和工作流。 
  
当您迁移响应组时, 不会删除旧的响应组。 通过使用 Skype for business Server 控制面板或 Skype for business Server Management Shell 管理迁移后的响应组, 你可以同时看到旧式响应组和 Skype for business Server 2019 响应组。 你应该仅将更新应用到 Skype for Business Server 2019 响应组。 旧的响应组仅保留用于回退用途。 
  
> [!CAUTION]
> 完成迁移并创建新的响应组后, Skype for business Server 控制面板和 Skype for business Server Management Shell 将显示每个响应的旧版和 Skype for business Server 2019 版本。团队. 请勿使用 Skype for Business 服务器控制面板或 Skype for business Server Management Shell 删除旧式响应组。 如果确实删除了一个, 则迁移期间创建的相应响应组将停止工作。 当您停止旧版的池时, 旧的响应组将被删除。 
  
> [!IMPORTANT]
> 我们建议您不要从以前的部署中删除任何数据, 直到解除池。 此外, 我们强烈建议您在迁移后立即导出响应组。 如果传统响应组应被删除, 则可以从备份还原响应组, 以使 Skype for business Server 2019 响应组再次运行。 
  
Skype for Business Server 2019 引入了名为 "**工作流类型**" 的新响应组功能。 **工作流类型**可以是**托管**或**非托管**。 将使用**工作流类型**设置为**非托管**并使用空管理器列表迁移所有响应组。 
  
当你运行**CsRgsConfiguration** cmdlet 时, 代理组、队列、工作流和音频文件将保留在旧版池中, 以便进行回退。 但是, 如果确实需要回退到旧版池, 则需要运行**CsApplicationEndpoint** cmdlet 以将联系人对象移回旧版池。 
  
用于迁移响应组配置的以下过程假定你的旧池和 Skype for business Server 2019 池之间具有一对一关系。 如果你计划在迁移和部署期间合并或拆分池, 你需要规划哪些旧式池映射到哪些 Skype for business Server 2019 池。
  
## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1. 使用属于 RTCUniversalServerAdmins 组的成员的帐户登录到计算机, 或具有等效的管理员权利和权限。
    
2. 启动 Skype for Business Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳**"。
    
3. 运行：
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 将响应组和代理迁移到 Skype for Business Server 2019 池后, 代理用于登录和注销的 URL 是 Skype for business Server 2019 URL, 可从 "**工具**" 菜单中获取。 提醒代理将任何引用 (如书签) 更新到新 URL。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板验证响应组迁移

1. 使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息, 请参阅[打开 skype for Business server 2019 管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左侧导航窗格中, 单击 "**响应组**"。
    
4. 在 "**工作流**" 选项卡上, 验证您的旧环境中的所有工作流是否都包含在列表中。 
    
5. 单击 "**队列**" 选项卡, 然后验证您的旧环境中的所有队列是否都包含在列表中。 
    
6. 单击 "**组**" 选项卡, 然后验证您的旧环境中的所有代理组是否都包含在列表中。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序验证响应组迁移

1. 使用属于 RTCUniversalReadOnlyAdmins 组成员的帐户登录到计算机, 或者将该帐户的成员最少 CsViewOnlyAdministrator 角色的成员。
    
2. 启动 Skype for Business Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳**"。
    
    有关以下 cmdlet 的详细信息, 请运行:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. 运行：
    
   ```
   Get-CsRgsAgentGroup
   ```

4. 验证你的旧环境中的所有代理组是否都包含在列表中。
    
5. 运行：
    
   ```
   Get-CsRgsQueue
   ```

6. 验证您的旧环境中的所有队列是否都包含在列表中。
    
7. 运行：
    
   ```
   Get-CsRgsWorkflow
   ```

8. 验证您的旧环境中的所有工作流是否都包含在列表中。
    


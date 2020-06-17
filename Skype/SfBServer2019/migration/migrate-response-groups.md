---
title: 迁移响应组
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将用户移动到 Skype for business Server 2019 池之后，可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧版部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 旧版池不再处理对响应组的调用。
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752674"
---
# <a name="migrate-response-groups"></a>迁移响应组

将用户移动到 Skype for business Server 2019 池之后，可以迁移响应组。 迁移响应组包括将代理组、队列、工作流、音频文件和移动响应组联系人对象从旧版部署复制到 Skype for business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫由 Skype for Business Server 2019 池中的响应组应用程序处理。 旧版池不再处理对响应组的调用。
  
> [!NOTE]
> 虽然您可以在将所有用户移动到 Skype for Business Server 2019 池之前迁移响应组，但我们建议您首先移动所有用户。 特别是，响应组代理的用户在移动到 Skype for Business Server 2019 池之前，不会具有新功能的完整功能。 
  
在迁移响应组之前，必须已部署包含响应组应用程序的 Skype for Business Server 2019 池。 默认情况下，在部署企业语音时，会安装并激活响应组应用程序。 您可以通过运行**get-csservice-ApplicationServer** cmdlet 来确保响应组应用程序已安装。 
  
> [!NOTE]
> 您可以先在 Skype for business Server 2019 池中创建新的 Skype for Business Server 2019 响应组，然后再迁移您的旧版响应组。 
  
若要将响应组从旧版池迁移到 Skype for Business Server 2019，请运行**CsRgsConfiguration** cmdlet。 
  
> [!IMPORTANT]
> 响应组迁移 cmdlet 将移动整个池的响应组配置。 您不能选择特定组、队列或工作流进行迁移。 
  
迁移响应组之后，需要使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 cmdlet 来验证是否成功移动了所有代理组、队列和工作流。 
  
迁移响应组时，不会删除旧响应组。 在迁移后使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序管理响应组时，您可以看到旧版响应组和 Skype for Business Server 2019 响应组。 您应该仅将更新应用到 Skype for Business Server 2019 响应组。 旧响应组仅为回滚而保留。 
  
> [!CAUTION]
> 在完成迁移并创建新的响应组之后，Skype for Business Server 控制面板和 Skype for Business Server 命令行管理程序将显示每个响应组的旧版和 Skype for business Server 2019 版本。 请勿使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除旧版响应组。 如果确实删除了一个，则在迁移过程中创建的相应响应组将停止工作。 停用旧版池时，将删除旧版响应组。 
  
> [!IMPORTANT]
> 建议在停用池之前不要删除之前的部署中的任何数据。 此外，强烈建议在迁移后立即导出响应组。 如果应删除旧响应组，则可以从备份中还原响应组，以获取 Skype for business Server 2019 响应组再次运行。 
  
Skype for Business Server 2019 引入了名为 "**工作流类型**" 的新响应组功能。 “工作流类型”**** 可以是“托管”**** 的，也可以是“非托管”**** 的。 所有响应组都是使用设置为“非托管”**** 的“工作流类型”**** 和空管理员列表进行迁移的。 
  
在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。 但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。 
  
下面的迁移响应组配置的过程假设您的旧版池和 Skype for Business Server 2019 池之间具有一对一关系。 如果您计划在迁移和部署期间合并或拆分池，则需要规划哪些旧版池映射到哪个 Skype for business Server 2019 池。
  
## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1. 使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。
    
3. 以
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 将响应组和代理迁移到 Skype for Business Server 2019 池之后，代理用于登录和注销的 URL 是 Skype for Business Server 2019 URL，可从 "**工具**" 菜单中获取。 提醒代理更新对新 URL 的所有引用（例如书签）。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板验证响应组迁移的具体方法

1. 使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅[Open Skype For Business server 2019 管理工具](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左侧导航窗格中，单击“响应组”****。
    
4. 在 "**工作流**" 选项卡上，验证您的旧环境中的所有工作流是否都包含在列表中。 
    
5. 单击 "**队列**" 选项卡，并验证您的旧环境中的所有队列是否都包含在该列表中。 
    
6. 单击 "**组**" 选项卡，并验证您的旧环境中的所有代理组是否都包含在该列表中。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序验证响应组迁移

1. 使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 以
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 确认您的旧环境中的所有代理组都包含在该列表中。
    
5. 以
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 验证您的旧环境中的所有队列是否都包含在该列表中。
    
7. 以
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 验证您的旧环境中的所有工作流是否都包含在列表中。
    


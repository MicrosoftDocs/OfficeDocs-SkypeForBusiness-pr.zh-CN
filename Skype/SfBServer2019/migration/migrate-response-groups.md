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
description: 将用户移至 Skype for Business Server 2019 池后，可以迁移响应组。 迁移响应组包括复制代理组、队列、工作流、音频文件，以及将响应组联系人对象从旧部署移动到 Skype for Business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫将由 Skype for Business Server 2019 池中的响应组应用程序处理。 对响应组的呼叫不再由旧池处理。
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113268"
---
# <a name="migrate-response-groups"></a>迁移响应组

将用户移至 Skype for Business Server 2019 池后，可以迁移响应组。 迁移响应组包括复制代理组、队列、工作流、音频文件，以及将响应组联系人对象从旧部署移动到 Skype for Business Server 2019 池。 迁移旧版响应组后，对响应组的呼叫将由 Skype for Business Server 2019 池中的响应组应用程序处理。 对响应组的呼叫不再由旧池处理。
  
> [!NOTE]
> 尽管您可以在将所有用户移动到 Skype for Business Server 2019 池之前迁移响应组，但我们建议您先移动所有用户。 特别是，作为响应组代理的用户在被移动到 Skype for Business Server 2019 池之前，将没有新功能的全部功能。 
  
迁移响应组之前，必须已部署包含响应组应用程序的 Skype for Business Server 2019 池。 默认情况下，当您部署响应组应用程序时，将安装并激活企业语音。 您可以通过运行 **Get-CsService -ApplicationServer** cmdlet 来确保安装了响应组应用程序。 
  
> [!NOTE]
> 在迁移旧版响应组之前，可以在 Skype for Business Server 2019 池中创建新的 Skype for Business Server 2019 响应组。 
  
若要将响应组从旧池迁移到 Skype for Business Server 2019，请运行 **Move-CsRgsConfiguration** cmdlet。 
  
> [!IMPORTANT]
> 响应组迁移 cmdlet 移动整个池的响应组配置。 您不能选择特定组、队列或工作流进行迁移。 
  
迁移响应组后，你需要使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 cmdlet 验证所有代理组、队列和工作流是否都已成功移动。 
  
迁移响应组时，不会删除旧的响应组。 当你使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 在迁移后管理响应组时，你可以看到旧版响应组和 Skype for Business Server 2019 响应组。 应仅对 Skype for Business Server 2019 响应组应用更新。 旧响应组仅为回滚而保留。 
  
> [!CAUTION]
> 完成迁移并创建新的响应组后，Skype for Business Server 控制面板和 Skype for Business Server 命令行管理程序将显示每个响应组的旧版和 Skype for Business Server 2019 版本。 请勿使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除旧版响应组。 如果删除一个响应组，则迁移期间创建的相应响应组将停止工作。 停用旧池时，将删除旧响应组。 
  
> [!IMPORTANT]
> 建议在停用池之前不要删除之前的部署中的任何数据。 此外，强烈建议在迁移后立即导出响应组。 如果应删除旧版响应组，可以从备份还原响应组，让 Skype for Business Server 2019 响应组再次运行。 
  
Skype for Business Server 2019 引入了名为"工作流类型"的新响应 **组功能**。 “工作流类型”可以是“托管”的，也可以是“非托管”的。 所有响应组都是使用设置为“非托管”的“工作流类型”和空管理员列表进行迁移的。 
  
在运行 **Move-CsRgsConfiguration** cmdlet 时，代理组、队列、工作流和音频文件保留在旧版池中以用于回滚。 但如果您确实需要回滚到旧版池，则需要运行 **Move-CsApplicationEndpoint** cmdlet 将联系对象移回旧版池。 
  
以下迁移响应组配置的过程假定旧版池和 Skype for Business Server 2019 池之间具有一对一关系。 如果你计划在迁移和部署期间合并或拆分池，则需要规划哪个旧版池映射到哪个 Skype for Business Server 2019 池。
  
## <a name="to-migrate-response-group-configurations"></a>迁移响应组配置

1. 使用具有 RTCUniversalServerAdmins 组成员身份或同等管理员权限的帐户登录到计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：**单击"开始**"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 运行：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 将响应组和代理迁移到 Skype for Business Server 2019 池后，代理用于登录和注销的 URL 是 Skype for Business Server 2019  URL，可从"工具"菜单访问。 提醒代理更新对新 URL 的所有引用（例如书签）。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板验证响应组迁移

1. 使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅 [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左侧导航窗格中，单击“响应组”。
    
4. 在 **"工作流** "选项卡上，验证旧环境中的所有工作流是否都包含在列表中。 
    
5. 单击 **"队列** "选项卡，并验证旧环境中的所有队列是否都包含在列表中。 
    
6. 单击 **"组** "选项卡，并验证旧环境中的所有代理组是否都包含在列表中。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序验证响应组迁移

1. 使用 RTCUniversalReadOnlyAdmins 组成员帐户，或至少使用 CsViewOnlyAdministrator 角色成员帐户登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：**单击"开始**"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
    若要了解有关以下 cmdlet 的详细信息，请运行：
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 运行：
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 验证旧环境中的所有代理组是否都包含在列表中。
    
5. 运行：
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 验证旧环境中的所有队列是否都包含在列表中。
    
7. 运行：
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 验证旧环境中的所有工作流是否都包含在列表中。

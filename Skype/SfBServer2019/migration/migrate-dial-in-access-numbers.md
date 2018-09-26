---
title: 迁移拨入访问号码
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移拨入访问号码到业务服务器 2019年的 Skype 需要运行 Move-csapplicationendpoint cmdlet 迁移的联系对象。 在旧的安装和 Skype 业务服务器 2019年共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码行为类似旧安装中创建的拨入访问号码中所述部分。
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027723"
---
# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

迁移拨入访问号码到业务服务器 2019年的 Skype 需要运行**Move-csapplicationendpoint** cmdlet 迁移的联系对象。 在旧的安装和 Skype 业务服务器 2019年共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码行为类似旧安装中创建的拨入访问号码中所述部分。 
  
您在旧中创建的拨入访问号码安装，但移动到 Skype 业务服务器 2019，或您在 Skype for Business Server 2019 之前，创建期间或迁移后，具有以下特征：
  
- 不显示在 Office Communications Server 2007 R2 会议邀请和拨入访问号码页。
    
- 显示在旧安装会议邀请和拨入访问号码页。
    
- 业务服务器 2019年会议邀请和拨入访问号码页上显示在 Skype 上。
    
- 无法查看或修改 Office Communications Server 2007 R2 管理工具中。
    
- 可以查看和修改旧安装控制面板和旧安装命令行管理程序中。
    
- 可以查看和修改业务 Server 2019 控制面板的 Skype 和 Skype 的业务服务器 2019年命令行管理程序中。
    
- 可以在区域内重新排序使用带有 Priority 参数的 Set-csdialinconferencingaccessnumber cmdlet。
    
您必须完成迁移拨入访问号码指向旧的安装池之前停用旧安装池。 如果您未完成电话拨入访问号码迁移以下过程中所述，将失败传入呼叫的访问号码。
  
> [!IMPORTANT]
> 您必须执行此过程之前在停用旧安装池。 
  
> [!NOTE]
> 我们建议您没有的服务中断期间较短的情况下，网络使用率较低时, 移动拨入访问号码。 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a>确认和移动电话拨入访问号码

1. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。
    
2. 若要将每个拨入访问号码移动到的业务服务器 2019 Skype 上承载的池，从命令行运行： 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. 打开 Skype 业务 Server Control Panel。
    
4. 在左侧导航栏中，单击“**会议**”。
    
5. 单击**电话拨入访问号码**选项卡。 
    
6. 确认要从中迁移的旧安装池没有保留任何拨入访问号码。
    
    > [!NOTE]
    > 当所有拨入访问号码都指向业务服务器 2019年池 Skype 时，然后可以停用旧安装池。 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>确认用于业务 Server Control Panel Skype 拨入访问号码迁移

1. 使用分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”。
    
4. 单击**电话拨入访问号码**选项卡。 
    
5. 确认所有拨入访问号码均已都迁移到的业务服务器 2019 Skype 上承载的池。
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>确认电话拨入访问号码迁移 Skype 用于业务 Server 命令行管理程序

1. 打开 Skype 业务 Server 命令行管理程序。
    
2. 若要返回所有的电话拨入式会议访问号码迁移，从命令行运行：
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. 确认所有拨入访问号码均已都迁移到的业务服务器 2019 Skype 上承载的池。
    


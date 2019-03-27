---
title: 在 Skype 业务服务器安装管理工具
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要： 了解如何安装 Business Server Skype 安装所需的管理工具。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 48c6234b04f3c594f8cc50bda82ffca8cb256552
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884006"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 Skype 业务服务器安装管理工具
 
**摘要：** 了解如何安装所需的 Skype 安装 Business Server 管理工具。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
管理工具包括拓扑生成器和控制面板。 必须在拓扑或 64 位管理工作站上运行的是业务服务器 Skype 支持的 Windows 操作系统版本中的至少一台服务器上安装管理工具。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 安装管理工具是 8 个步骤中的第 3 步。
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安装 Business Server 管理工具的 Skype

Skype 业务服务器的安装媒体提供了灵活的体验。 当您首次运行 Setup.exe 时，安装的唯一工具是业务 Server 部署向导的 Skype 和业务 Server 命令行管理程序 Skype。 使用这两种工具，称为核心组件，您可以继续安装过程中，但它们不提供总体 Skype 业务服务器环境的主要功能。 在您安装核心组件后，部署向导将自动启动。 名为**安装管理工具**部署向导的一部分的业务 Server Control Panel 安装 Business Server 拓扑生成器和 Skype 的 Skype。
  
> [!IMPORTANT]
> 每个业务服务器环境的 Skype 必须至少一台服务器安装了管理工具。 
  
观看视频，了解**安装管理工具**的步骤：
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>为业务 Server 管理工具从部署向导安装 Skype

1. 插入业务 Server 安装介质的 Skype。 如果安装未自动开始，请双击“**安装**”。
    
2. 安装媒体需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。
    
3. 使用智能的安装程序，Skype 业务服务器中的新功能可以连接到 Internet 安装过程中更新的检查。 这能确保您在安装时获得最新产品更新，从而提供更好的体验。 单击“**安装**”开始安装。
    
4. 仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。
    
5. 将在服务器上安装的业务 Server 核心组件 Skype。 
    
    核心组件包含以下内容，如图所示。
    
    ![“应用程序中的核心组件”屏幕。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype 的业务 Server 部署向导**为业务服务器安装 Skype 的各种组件提供启动拨号盘部署计划。
    
   - **Skype 的业务 Server 命令行管理程序**预配置的 PowerShell 程序，允许 Skype 的业务服务器的管理。
    
     核心组件安装完成后，将自动启动 Business Server 部署向导的 Skype，如下图所示。 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件，您需要 Skype 业务 Server 拓扑生成器和 Skype 上安装 for Business Server Control Panel 环境中的至少一台服务器。 单击部署向导上的“**安装管理工具**”。
    
7. 单击“**下一步**”开始安装。
    
8. 完成安装后，请单击“**完成**”。管理工具现已添加到服务器中，如图所示。
    
    ![Skype 业务服务器管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype 的业务 Server 拓扑生成器**用于构建、 部署和管理拓扑的程序。
    
   - **Skype 的业务 Server Control Panel**用于管理安装程序。
    


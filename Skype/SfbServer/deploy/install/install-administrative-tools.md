---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要：了解如何安装安装 Skype for Business Server 所需的管理工具。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812102"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 Skype for Business Server 中安装管理工具
 
**摘要：** 了解如何安装安装 Skype for Business Server 所需的管理工具。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 位置为：
  
管理工具包括拓扑生成器和控制面板。 管理工具必须安装在拓扑中的至少一台服务器上，或安装在运行受 Skype for Business Server 支持的 Windows OS 版本的 64 位管理工作站上。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。 安装管理工具是步骤 3/8。
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安装 Skype for Business Server 管理工具

Skype for Business Server 的安装媒体提供了灵活的体验。 首次运行 Setup.exe时，唯一安装的工具是 Skype for Business Server 部署向导和 Skype for Business Server 命令行管理程序。 通过使用这两种工具（称为核心组件）可以继续安装过程，但它们不会为整个 Skype for Business Server 环境提供主要功能。 安装核心组件后，部署向导将自动启动。 部署向导中标题为"安装管理工具"的部分将安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。
  
> [!IMPORTANT]
> 每个 Skype for Business Server 环境都必须至少有一台安装了管理工具的服务器。 
  
观看安装管理工具 **的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>从部署向导安装 Skype for Business Server 管理工具

1. 插入 Skype for Business Server 安装媒体。 如果安装程序不会自动开始，请双击"设置 **"。**
    
2. 安装媒体需要 Microsoft Visual C++ 来运行。 将弹出一个对话框，询问是否要安装它。 单击“是”。
    
3. 通过使用智能安装（Skype for Business Server 中的一项新功能）可以连接到 Internet 以在安装过程中检查更新。 这通过确保在安装时获得产品的最新更新，从而提供更好的体验。 单击 **“安装”**，开始安装。
    
4. 仔细阅读许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"**确定"。**
    
5. Skype for Business Server 核心组件将安装在服务器上。 
    
    核心组件由以下内容组成，如图所示。
    
    !["应用"屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server 部署向导** 提供用于安装 Skype for Business Server 各种组件的启动板的部署计划。
    
   - **Skype for Business Server 命令行管理程序** 允许管理 Skype for Business Server 的预配置 PowerShell 程序。
    
     核心组件的安装完成后，Skype for Business Server 部署向导将自动启动，如图所示。 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件之外，你还需要在环境中至少一台服务器上安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。 单击 **部署向导上的** "安装管理工具"。
    
7. 单击“下一步”开始安装。
    
8. 安装完成后，单击"完成 **"。** 管理工具现已添加到服务器，如图所示。
    
    ![Skype for Business Server 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server 拓扑生成器** 用于构建、部署和管理拓扑的程序。
    
   - **Skype for Business Server 控制面板** 用于管理安装的程序。
    


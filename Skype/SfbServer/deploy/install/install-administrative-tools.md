---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何安装 Skype for Business Server 安装所需的管理工具。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018263"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 Skype for Business Server 中安装管理工具
 
**摘要：** 了解如何安装 Skype for business Server 安装所需的管理工具。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。
  
管理工具包括拓扑生成器和 "控制面板"。 必须在拓扑中至少一台服务器上或运行 Skype for Business Server 支持的 Windows OS 版本的64位管理工作站上安装管理工具。 您可以按任意顺序执行步骤1至5。 但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 安装管理工具是第3步（共8步）。
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安装 Skype for Business Server 管理工具

Skype for business Server 的安装媒体提供了灵活的体验。 当您首次运行 setup.exe 时，安装的唯一工具是 Skype for Business Server 部署向导和 Skype for Business Server 命令行管理程序。 通过使用这两个工具（称为核心组件），可以继续安装过程，但不提供整个 Skype for Business Server 环境的主要功能。 安装核心组件后，将自动启动部署向导。 "部署向导" 中的 "**安装管理工具**" 一节安装了 Skype For Business Server 拓扑生成器和 skype For Business server 控制面板。
  
> [!IMPORTANT]
> 每个 Skype for Business Server 环境都必须至少有一台安装了管理工具的服务器。 
  
观看**安装管理工具**的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>从部署向导安装 Skype for Business Server 管理工具

1. 插入 Skype for Business Server 安装媒体。 如果安装程序未自动开始，请双击 "**设置**"。
    
2. 安装介质需要 Microsoft Visual c + + 才能运行。 将弹出一个对话框，询问您是否要安装此对话框。 单击“是”****。
    
3. 通过使用 "智能安装" （Skype for Business Server 中的一项新功能），您可以连接到 Internet 以在安装过程中检查是否有更新。 这样可以确保在安装时有最新的产品更新，从而提供更好的体验。 单击 **“安装”**，开始安装。
    
4. 仔细阅读许可协议，如果您同意，请选择 "**我接受许可协议中的条款**"，然后单击 **"确定"**。
    
5. Skype for Business Server 核心组件将安装在服务器上。 
    
    核心组件由以下部分组成，如下图所示。
    
    ![应用程序屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype For Business Server 部署向导**提供用于安装 Skype for Business Server 的各种组件的启动板的部署程序。
    
   - **Skype For Business Server 命令行管理程序**允许管理 Skype for Business Server 的预配置 PowerShell 程序。
    
     核心组件的安装完成后，Skype for Business Server 部署向导将自动启动，如图中所示。 
    
     ![Skype for Business Server 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件之外，还需要在环境中的至少一台服务器上安装 Skype for Business Server 拓扑生成器和 Skype for Business Server 控制面板。 单击 "部署向导" 上的 "**安装管理工具**"。
    
7. 单击“下一步”**** 开始安装。
    
8. 安装完成后，单击 "**完成**"。 管理工具现已添加到服务器中，如图所示。
    
    ![Skype for Business Server 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype For Business Server 拓扑生成器**用于生成、部署和管理拓扑的程序。
    
   - **Skype For Business Server 控制面板**用于管理安装的程序。
    


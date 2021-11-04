---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: Summary： Learn how to install the administrative tools required for an installation of Skype for Business Server. 从 Microsoft 评估Skype for Business Server下载免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：。
ms.openlocfilehash: d2f80627aceee47559a06ab604e1cc8827d310b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753245"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 Skype for Business Server 中安装管理工具
 
**摘要：** 了解如何安装安装应用程序所需的Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) ：。
  
管理工具包括拓扑生成器和控制面板。 管理工具必须安装在拓扑中的至少一台服务器或运行 Windows 操作系统版本的 64 位管理工作站上，Skype for Business Server。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按照图中的概述顺序执行步骤 6、7 和 8 以及步骤 1 到步骤 5 之后。 安装管理工具是步骤 3/8。
  
![概述图表。](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安装Skype for Business Server管理工具

适用于 Skype for Business Server 的安装媒体提供了灵活的体验。 首次运行 Setup.exe时，唯一安装的工具是 Skype for Business Server 部署向导和 Skype for Business Server 命令行管理程序。 通过使用这两种工具（称为核心组件）可以继续执行安装过程，但它们不会为整个 Skype for Business Server 环境。 安装核心组件后，部署向导将自动启动。 部署向导中名为"**安装管理工具"** 的一节Skype for Business Server拓扑生成器Skype for Business Server控制面板。
  
> [!IMPORTANT]
> 每个Skype for Business Server环境都必须至少有一台安装了管理工具的服务器。 
  
观看安装管理工具 **的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>从Skype for Business Server向导安装管理工具

1. 插入Skype for Business Server媒体。 如果安装程序未自动开始，请双击"设置 **"。**
    
2. 安装媒体需要Microsoft Visual C++运行。 将弹出一个对话框，询问您是否要安装它。 单击“是”。
    
3. 通过使用智能设置（Skype for Business Server一项新功能，您可以连接到 Internet 以在安装过程中检查更新。 这通过确保你在安装时具有产品的最新更新提供了更好的体验。 单击 **“安装”**，开始安装。
    
4. 仔细阅读许可协议，如果同意，请选择"**我接受许可协议** 中的条款"，然后单击"确定 **"。**
    
5. Skype for Business Server核心组件将安装在服务器上。 
    
    核心组件由以下内容组成，如图所示。
    
    !["应用"屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server部署向导** 一个部署程序，提供用于安装 Skype for Business Server 的各种组件的启动Skype for Business Server。
    
   - **Skype for Business Server命令行管理程序** 一个预配置的 PowerShell 程序，用于管理Skype for Business Server。
    
     核心组件的安装完成后，Skype for Business Server向导将自动启动，如图所示。 
    
     ![Skype for Business Server部署向导。](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件，您还需要在Skype for Business Server至少一台服务器Skype for Business Server拓扑生成器和控制面板。 单击 **部署向导上的** "安装管理工具"。
    
7. 单击“下一步”开始安装。
    
8. 安装完成后，单击"完成 **"。** 管理工具现已添加到服务器，如图所示。
    
    ![Skype for Business Server管理工具。](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server拓扑生成器** 用于构建、部署和管理拓扑的程序。
    
   - **Skype for Business Server控制面板** 用于管理安装的程序。
    


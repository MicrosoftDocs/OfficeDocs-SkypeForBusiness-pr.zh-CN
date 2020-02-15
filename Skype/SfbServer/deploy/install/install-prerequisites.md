---
title: 为 Skype for Business Server 安装必备组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要：了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018253"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>为 Skype for Business Server 安装必备组件
 
**摘要：** 了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business Server 的免费试用版。
  
安装先决条件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。 这些要求基于服务器将在拓扑中实现的角色。 您可以按任意顺序执行步骤1至5。 但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 安装先决条件是第1步（共8步）。
  
![概述图表-安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>设置 Windows Server

Skype for Business Server 要求先安装 Windows Server 操作系统和一些先决条件，然后才能安装。 有关规划先决条件的详细信息，请参阅[Skype For Business server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。 如果使用的是其他版本的 Windows Server，则过程可能略有不同。 
  
> [!IMPORTANT]
> 在开始之前，请使用 Windows Update 确保 Windows Server 处于最新状态。 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看**安装必备组件**的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装必需的角色和功能

可以使用服务器管理器安装必需的角色和功能。 
    
1. 安装[Skype For Business server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)中列出的必备软件功能。 必需的软件必须位于将运行 Skype for Business Server 的服务器上。
    
    > [!CAUTION]
    > 默认情况下，Windows Server 2012 R2 不会为所需功能安装所有源文件。 如果服务器未连接到 Internet，则需要插入 Windows Server 2012 R2 介质，并选择 "**指定备用源路径**" 以安装所需的功能。 源文件位于 sources\sxs 目录中。 例如，如果 Windows Server 2012 R2 媒体位于驱动器 D 中，则应将路径设置为`d:\sources\sxs`。 必须具有 Windows Update 中的最新更新，这一点很重要。 如果未连接到 Internet，则需要手动安装所有相关更新以及所需更新的所有先决条件。 
  
1. 当对话框指示安装已完成时，您需要重新启动服务器以完成此过程。
    
1. 再次运行**Windows Update**以检查是否存在已安装的角色和服务的任何更新。
    
1. 如果要在此服务器上使用 Skype for Business Server 控制面板，则还必须安装 Silverlight。 若要安装 Silverlight，请参阅[Microsoft silverlight](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> 执行除前端服务器之外的角色的服务器的先决条件（如控制器、持久聊天或边缘的角色）具有自己的先决条件。 有关每种服务器类型所需的具体先决条件的详细信息，请参阅[Skype For Business server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  


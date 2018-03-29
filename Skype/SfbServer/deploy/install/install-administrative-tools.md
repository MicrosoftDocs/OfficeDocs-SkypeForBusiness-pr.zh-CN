---
title: 在 Skype for Business Server 2015 中安装管理工具
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '摘要： 了解如何安装业务服务器 2015 Skype 安装所需的管理工具。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中安装管理工具
 
**摘要：**了解如何安装业务服务器 2015 Skype 安装所需的管理工具。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
管理工具包括拓扑生成器和控制面板。 管理工具必须安装在至少一台服务器拓扑中运行业务服务器为 Skype 支持的 Windows 操作系统版本的 64 位管理工作站上。 您可以按照任意顺序完成第 1 步至第 5 步。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 安装管理工具是 8 个步骤中的第 3 步。
  
![概述图表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>为业务服务器 2015年管理工具安装 Skype

Skype 的业务服务器 2015年的安装媒体提供了灵活的体验。 第一次运行 Setup.exe 时，安装的唯一工具是 Skype 业务服务器部署向导和 Skype 的业务服务器管理程序。 通过使用这两种工具，称为核心组件，您可以继续安装过程中，但它们不提供业务服务器环境总体 Skype 的主要功能。 在您安装核心组件后，部署向导将自动启动。 部署向导**安装管理工具**的标题为的一节安装 Skype 业务服务器控件面板业务服务器拓扑生成器和 Skype。
  
> [!IMPORTANT]
> 每一个 Skype 业务服务器环境必须有至少一台服务器安装管理工具。 
  
观看视频，了解**安装管理工具**的步骤：
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>安装 Skype 业务服务器 2015年从部署向导的管理工具

1. 插入 Skype 业务服务器 2015年安装媒体。 如果安装未自动开始，请双击“**安装**”。
    
2. 安装媒体需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。
    
3. 通过使用智能安装程序中的业务服务器 2015，Skype 的新增功能您可以连接到互联网，以在安装过程中检查有更新。 这能确保您在安装时获得最新产品更新，从而提供更好的体验。 单击“**安装**”开始安装。
    
4. 仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。
    
5. 将在服务器上安装 Skype 业务服务器 2015年核心组件。 
    
    核心组件包含以下内容，如图所示。
    
    ![“应用程序中的核心组件”屏幕。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype 业务服务器 2015年部署向导**部署程序的业务服务器 2015年安装 Skype 的各种组件提供启动键盘。
    
  - **Skype 的业务服务器 2015年管理外壳程序**允许管理业务服务器 2015年的 Skype 的预配置的 PowerShell 程序。
    
    核心组件安装完成后，Skype 业务服务器 2015年部署向导将自动启动，如图中所示。 
    
    ![Skype for Business Server 2015 部署向导](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件，也需要安装 Skype 业务服务器 2015年拓扑生成器和 Skype 业务服务器 2015年控制面板在环境中的至少一台服务器上。 单击部署向导上的“**安装管理工具**”。
    
7. 单击“**下一步**”开始安装。
    
8. 完成安装后，请单击“**完成**”。管理工具现已添加到服务器中，如图所示。
    
    ![Skype for Business Server 2015 管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype 业务服务器 2015年拓扑生成器**一种程序，用于生成、 部署和管理拓扑。
    
   - **Skype 的业务服务器 2015年控制面板**用来管理安装程序。
    


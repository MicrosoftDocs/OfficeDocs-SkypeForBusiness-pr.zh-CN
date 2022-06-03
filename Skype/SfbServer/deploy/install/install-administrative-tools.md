---
title: 在 Skype for Business Server 中安装管理工具
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: 摘要：了解如何安装安装Skype for Business Server所需的管理工具。
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860523"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 Skype for Business Server 中安装管理工具
 
**总结：** 了解如何安装安装Skype for Business Server所需的管理工具。
  
管理工具包括拓扑生成器和控制面板。 管理工具必须安装在拓扑中的至少一台服务器或运行支持Skype for Business Server的Windows OS 版本的 64 位管理工作站上。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 安装管理工具是第 8 步中的步骤 3。
  
![概述图。](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安装Skype for Business Server管理工具

Skype for Business Server的安装介质提供了灵活的体验。 首次运行Setup.exe时，安装的唯一工具是Skype for Business Server部署向导和 Skype for Business Server Management Shell。 通过使用这两个工具（称为核心组件），可以继续执行安装过程，但它们不为整个Skype for Business Server环境提供主要功能。 安装核心组件后，部署向导会自动启动。 名为 **“安装管理工具”** 的部署向导部分安装Skype for Business Server拓扑生成器和Skype for Business Server 控制面板。
  
> [!IMPORTANT]
> 每个Skype for Business Server环境必须至少有一个安装了管理工具的服务器。 
  
观看 **安装管理工具** 的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>从部署向导安装Skype for Business Server管理工具

1. 插入Skype for Business Server安装介质。 如果安装程序未自动开始，请双击 **“安装程序**”。
    
2. 安装介质需要Microsoft Visual C++才能运行。 将弹出一个对话框，询问是否要安装它。 单击“是”。
    
3. 使用智能安装程序（Skype for Business Server中的一项新功能）可以连接到 Internet，以在安装过程中检查更新。 这可以通过确保安装时对产品进行最新更新来提供更好的体验。 单击 **“安装”**，开始安装。
    
4. 仔细查看许可协议，如果同意，请选择 **我接受许可协议中的条款**，然后单击 **“确定**”。
    
5. Skype for Business Server核心组件将安装在服务器上。 
    
    核心组件包括以下内容，如图所示。
    
    ![“应用”屏幕中的核心组件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server部署向导** A 部署程序，它提供用于安装Skype for Business Server的各种组件的启动板。
    
   - **Skype for Business Server管理 Shell** A 预配置的 PowerShell 程序，用于管理Skype for Business Server。
    
     核心组件安装完成后，Skype for Business Server部署向导将自动启动，如图所示。 
    
     ![Skype for Business Server部署向导。](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心组件，还需要在环境中至少一台服务器上安装Skype for Business Server拓扑生成器和Skype for Business Server 控制面板。 单击部署向导上的 **“安装管理工具** ”。
    
7. 单击“下一步”开始安装。
    
8. 安装完成后，单击 **“完成**”。 管理工具现在已添加到服务器，如图所示。
    
    ![Skype for Business Server管理工具。](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server拓扑生成器** A 程序，用于生成、部署和管理拓扑。
    
   - **Skype for Business Server 控制面板** 用于管理安装的程序。
    


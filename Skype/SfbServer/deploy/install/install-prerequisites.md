---
title: 安装用于安装Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要：了解在安装之前必须配置的服务器和Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费试用版 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ：。
ms.openlocfilehash: 8b646ea95b13454d1b025cfbfdae186c927859e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751151"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安装用于安装Skype for Business Server
 
**摘要：** 了解在安装之前必须配置的服务器和Skype for Business Server。 从 Microsoft 评估中心Skype for Business Server[免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
安装必备组件包括Windows拓扑中的每台服务器上安装所需的角色和功能来设置服务器。 这些要求基于服务器将在拓扑中履行的角色。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按照图中的概述顺序执行步骤 6、7 和 8 以及步骤 1 到步骤 5 之后。 安装必备组件是步骤 1/8。
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Setup Windows Server

Skype for Business Server安装Windows服务器操作系统和许多必备组件。 有关规划先决条件的详细信息，请参阅 Server [requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。 如果使用的是其他版本的 Windows Server，则过程可能略有不同。 
  
> [!IMPORTANT]
> 在开始之前，使用 Windows Update 确保 Windows 服务器是最新的。 
  
![Windows服务器最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看安装必备 **组件的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装所需的角色和功能

可以使用服务器管理器安装所需的角色和功能。 
    
1. 安装 Server requirements for Skype for Business Server 中列出的[必备软件功能](../../../SfBServer2019/plan/system-requirements.md)。 必需的软件必须位于将运行 Skype for Business Server。
    
    > [!CAUTION]
    > Windows Server 2012R2 在默认情况下不会为所需功能安装所有源文件。 如果服务器未连接到 Internet，则需要插入 R2 Windows Server 2012并选择"指定备用源路径"以安装所需功能。 源文件位于 sources\sxs 目录中。 例如，如果Windows Server 2012 R2 媒体位于驱动器 D 中，则你将路径设置为 `d:\sources\sxs` 。 更新中提供最新更新Windows很重要。 如果未连接到 Internet，则需要手动安装所有相关更新以及所需更新的任何必备组件。 
  
1. 当对话框指示安装已完成时，您需要重新启动服务器才能完成此过程。
    
1. 再次 **Windows"** 更新"，检查是否对已安装的角色和服务进行了任何更新。
    
1. 如果要在此服务器上Skype for Business Server控制面板，则还必须安装 Silverlight。 若要安装 Silverlight，请参阅[Microsoft Silverlight。](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> 执行前端服务器角色（如控制器、持久聊天或边缘角色）的服务器的先决条件具有自己的先决条件。 有关每种服务器类型所需的确切先决条件的详细信息，请参阅 Server [requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)。 
  


---
title: 安装 Skype for business 服务器的先决条件
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
description: 摘要：了解在安装 Skype for Business 服务器之前必须配置的服务器和服务器角色。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: f8ecb50525a9bb312975bf71b55a5f71c19db205
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791760"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安装 Skype for business 服务器的先决条件
 
**摘要：** 了解在安装 Skype for Business 服务器之前必须配置的服务器和服务器角色。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。
  
安装必备软件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。 这些要求基于服务器将在拓扑中承担的角色。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 安装必备软件是 8 个步骤中的第 1 步。
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>设置 Windows Server

Skype for business 服务器要求先安装 Windows Server 操作系统和若干先决条件，然后才能安装。 有关规划先决条件的详细信息，请参阅[Skype for Business 服务器的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。 如果您要使用其他版本的 Windows Server，该过程可能略有不同。 
  
> [!IMPORTANT]
> 开始之前，请确保 Windows Server 使用 Windows 更新保持最新状态。 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看视频，了解**安装必备组件**的步骤：
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装必要的角色和功能

你可以使用服务器管理器安装所需的角色和功能。 
    
1. 安装[Skype for Business server 的 "服务器要求](../../../SfBServer2019/plan/system-requirements.md)" 中列出的必备软件功能。 所需软件必须位于将运行 Skype for Business 服务器的服务器上。
    
    > [!CAUTION]
    > Windows Server 2012 R2 不会默认安装必要功能的所有源文件。 如果服务器未连接 Internet，您需要插入 Windows Server 2012 R2 媒体并选择“**指定备用源路径**”以安装必要功能。 源文件位于 sources\sxs 目录中。 例如，如果 Windows Server 2012 R2 媒体位于驱动器 D 中，则应将路径设置为`d:\sources\sxs`。 请务必通过 Windows Update 获取最新更新。 如果您没有连接到 Internet，您需要手动安装所有相关更新以及更新所需的必备软件。 
  
1. 当出现对话框表示已完成安装时，您需要重新启动服务器以完成该流程。
    
1. 再次运行 **Windows Update** 以检查安装的角色和服务是否存在可用更新。
    
1. 如果你将在此服务器上使用 Skype for Business Server 控制面板，则你还必须安装 Silverlight。 若要安装 Silverlight，请参阅[Microsoft Silverlight](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> 执行前端服务器以外的角色（例如控制器、持久聊天或边缘角色）的服务器具备自己的先决条件。 有关每种服务器类型所需的确切先决条件的详细信息，请参阅[Skype for Business 服务器的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  


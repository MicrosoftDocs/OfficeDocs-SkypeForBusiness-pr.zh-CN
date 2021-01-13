---
title: 安装 Skype for Business Server 的先决条件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801712"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安装 Skype for Business Server 的先决条件
 
**摘要：** 了解在安装 Skype for Business Server 之前必须配置的服务器和服务器角色。 从 Microsoft 评估中心下载 Skype for Business Server [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
安装必备组件包括设置 Windows Server，方法为在拓扑中的每台服务器上安装所需的角色和功能。 要求基于服务器在拓扑中将担任的角色。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。 安装必备组件是步骤 1/8。
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>设置 Windows Server

Skype for Business Server 需要 Windows Server 操作系统和许多必备组件才能安装。 有关规划先决条件的详细信息，请参阅 Skype [for Business Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。 如果使用的是不同版本的 Windows Server，此过程可能略有不同。 
  
> [!IMPORTANT]
> 开始之前，使用 Windows 更新确保 Windows Server 是最新的。 
  
![Windows Server 最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看安装必备组件 **的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装所需的角色和功能

可以使用服务器管理器安装所需的角色和功能。 
    
1. 安装 Skype [for Business Server 的服务器要求中列出的必备软件功能](../../../SfBServer2019/plan/system-requirements.md)。 必需的软件必须位于将运行 Skype for Business Server 的服务器上。
    
    > [!CAUTION]
    > Windows Server 2012 R2 不会为所需的功能安装所有源文件。 如果服务器未连接到 Internet，则需要插入 Windows Server 2012 R2 媒体，然后选择"指定备用源路径"以安装所需的功能。 源文件位于 sources\sxs 目录中。 例如，如果 Windows Server 2012 R2 媒体位于驱动器 D 中，则您将路径设置为 `d:\sources\sxs` 。 从 Windows 更新获取最新更新非常重要。 如果未连接到 Internet，则需要手动安装所有相关更新以及所需更新的任何必备组件。 
  
1. 当对话框指示安装已完成时，需要重新启动服务器才能完成该过程。
    
1. 再次 **运行 Windows** 更新，检查是否对已安装的角色和服务进行了任何更新。
    
1. 如果你将在此服务器上使用 Skype for Business Server 控制面板，则还必须安装 Silverlight。 若要安装 Silverlight，请参阅[Microsoft Silverlight。](https://www.microsoft.com/silverlight/)


> [!IMPORTANT]
> 执行前端服务器角色（如控制器、持久聊天或边缘角色）的服务器的先决条件有其自己的先决条件。 有关每种服务器类型所需的确切先决条件的详细信息，请参阅 [Skype for Business Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  


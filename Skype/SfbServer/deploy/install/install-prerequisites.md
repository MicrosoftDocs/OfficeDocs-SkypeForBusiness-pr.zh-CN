---
title: 安装Skype for Business Server的先决条件
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: 摘要：了解安装Skype for Business Server之前必须配置的服务器和服务器角色。
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860733"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安装Skype for Business Server的先决条件
 
**总结：** 在安装Skype for Business Server之前，了解必须配置的服务器和服务器角色。
  
安装先决条件包括通过在拓扑中的每个服务器上安装所需的角色和功能来设置Windows服务器。 这些要求基于服务器在拓扑中将履行的角色。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 安装先决条件是步骤 8 中的步骤 1。
  
![概述图 - 安装先决条件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>安装Windows服务器

Skype for Business Server需要安装Windows服务器操作系统和一些先决条件。 有关规划先决条件的详细信息，请参阅[Skype for Business Server的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。 如果使用的是不同版本的Windows服务器，则过程可能略有不同。 
  
> [!IMPORTANT]
> 在开始之前，请确保Windows服务器使用Windows 更新是最新的。 
  
![Windows服务器最新。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看有关 **安装先决条件** 的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装所需的角色和功能

可以使用服务器管理器安装所需的角色和功能。 
    
1. 安装服务器要求中列出[的Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md)必备软件功能。 所需的软件必须位于将运行Skype for Business Server的服务器上。
    
    > [!CAUTION]
    > 默认情况下，Windows Server 2012 R2 不会为所需的功能安装所有源文件。 如果服务器未连接到 Internet，则需要插入Windows Server 2012 R2 媒体，然后选择 **“指定备用源路径**”以安装所需的功能。 源文件位于 source\sxs 目录中。 例如，如果Windows Server 2012 R2 介质位于驱动器 D 中，则会将路径设置为 `d:\sources\sxs`。 请务必从Windows 更新获取最新更新。 如果未连接到 Internet，则需要手动安装所有相关更新以及所需的更新的任何先决条件。 
  
1. 当对话框指示安装已完成时，需要重新启动服务器以完成该过程。
    
1. 再次运行 **Windows 更新**，检查是否已安装角色和服务有任何更新。
    
1. 如果要在此服务器上使用Skype for Business Server 控制面板，则还必须安装 Silverlight。 若要安装 Silverlight，请参阅 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> 执行前端服务器以外的角色（如 Director、Persistent Chat 或 Edge 角色）的服务器的先决条件具有其自己的先决条件。 有关每个服务器类型所需的确切先决条件的详细信息，请参阅[服务器Skype for Business Server要求](../../../SfBServer2019/plan/system-requirements.md)。 
  


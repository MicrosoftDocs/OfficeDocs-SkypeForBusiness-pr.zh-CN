---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 用于验证与旧版池共存的引导池的过程。
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751654"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

 **本文内容：**
  
[验证 Skype for Business Server 2019 服务是否已启动](#sectionSection0)
  
[打开 "Skype for Business Server 2019 控制面板"](#sectionSection1)
  
[不要尝试在旧版拓扑生成器中打开拓扑](#sectionSection2)
  
部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。 对于 Skype for business Server 2019 池和旧版池，您必须使用 Skype for Business Server 2019 控制面板和拓扑生成器工具。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>验证 Skype for Business Server 2019 服务是否已启动
<a name="sectionSection0"> </a>

1. 在 Skype for Business Server 2019 前端服务器中，导航到 "管理" Tools\Services 小程序。
    
2. 确认以下服务正在前端服务器上运行：

    - 集中日志记录服务代理
    - 应用程序共享
    - 音频测试服务
    - 音频/视频会议
    - Call Park － 呼叫寄存
    - 会议通知
    - 会议助理
    - 前端
    - IM 会议
    - 中介
    - 副本复制器代理
    - Response Group － 响应组
    - Web 会议
    - XMPP 转换网关

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>打开 "Skype for Business Server 2019 控制面板"
<a name="sectionSection1"> </a>

在 Skype for business Server 2019 部署的前端服务器中，打开 Skype for Business Server 2019 控制面板，然后选择旧版池。 重复此过程以打开 Skype for Business Server 2019 池。
  
> [!IMPORTANT]
> 在 Skype for business Server 2019 上，在使用 Skype for Business Server 控制面板之前，必须将 Silverlight 升级到 Silverlight 版本5。 
  
此拓扑现在包括旧版和 Skype for business Server 2019 服务器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>不要尝试在旧版拓扑生成器中打开拓扑
<a name="sectionSection2"> </a>

仅可以使用 Skype for Business Server 2019 拓扑生成器查看拓扑。 Skype for Business Server 2019 拓扑生成器必须用于为 Skype for business Server 2019 和旧安装创建池。

  


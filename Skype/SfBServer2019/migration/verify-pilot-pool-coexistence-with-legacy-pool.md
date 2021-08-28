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
ms.localizationpriority: medium
description: 验证试点池与旧池共存的过程。
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606811"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

 **本文内容：**
  
[确认Skype for Business Server 2019 服务已启动](#sectionSection0)
  
[打开 Skype for Business Server 2019 控制面板](#sectionSection1)
  
[不要尝试在旧拓扑生成器中打开拓扑](#sectionSection2)
  
部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。 对于 Skype for Business Server 2019 池和旧池，必须使用 Skype for Business Server 控制面板和拓扑生成器工具。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>确认Skype for Business Server 2019 服务已启动
<a name="sectionSection0"> </a>

1. 从 Skype for Business Server 2019 前端服务器中，导航到"管理工具\服务"小程序。
    
2. 确认以下服务正在前端服务器上运行：

    - 集中日志记录服务代理
    - 应用程序共享
    - 音频测试服务
    - 音频/视频会议
    - 呼叫寄存
    - 会议公告
    - 会议助理
    - 前端
    - IM 会议
    - 中介
    - 副本复制程序代理
    - 响应组
    - Web 会议
    - XMPP 转换网关

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>打开 Skype for Business Server 2019 控制面板
<a name="sectionSection1"> </a>

从 Skype for Business Server 2019 部署中的前端服务器，打开 Skype for Business Server 2019 控制面板并选择旧池。 重复此过程以打开 Skype for Business Server 2019 池。
  
> [!IMPORTANT]
> 在 Skype for Business Server 2019 上，必须先将 Silverlight 升级到 Silverlight 版本 5，然后Skype for Business Server控制面板。 
  
此拓扑现在包括旧版和 Skype for Business Server 2019 服务器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>不要尝试在旧拓扑生成器中打开拓扑
<a name="sectionSection2"> </a>

只能使用 2019 拓扑生成器Skype for Business Server拓扑。 必须使用 Skype for Business Server 2019 拓扑生成器为 2019 和旧安装Skype for Business Server池。

  


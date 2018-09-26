---
title: 验证试点池与旧池的共存情况
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要验证试点池与旧池的共存情况的过程。
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028689"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

 **本文中**
  
[确认 Skype 业务服务器 2019年服务已启动](#sectionSection0)
  
[打开 Skype 业务 Server 2019 Control Panel](#sectionSection1)
  
[请勿尝试在旧拓扑生成器中打开拓扑](#sectionSection2)
  
部署试点池后，您需要验证通过使用管理工具来查看池信息的两个池的共存情况。 对于业务服务器 2019年池和旧池 Skype，您必须使用业务 Server 2019 控制面板和拓扑生成器工具 Skype。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>确认 Skype 业务服务器 2019年服务已启动
<a name="sectionSection0"> </a>

1. 从业务 Server 2019 前端服务器的 Skype，导航到管理工具 \ 服务小程序。
    
2. 确认以下服务都在前端服务器上运行：

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

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>打开 Skype 业务 Server 2019 Control Panel
<a name="sectionSection1"> </a>

从业务服务器 2019年部署您 Skype 前端服务器，打开 Skype 业务 Server 2019 控制面板，然后选择旧池。 重复打开业务服务器 2019年池 Skype 的过程。
  
> [!IMPORTANT]
> 上的业务服务器 2019 Skype，必须将 Silverlight 升级到 Silverlight 版本 5 之前 Skype 用于业务 Server Control Panel。 
  
此拓扑现在包含旧和 Skype 业务服务器 2019年服务器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>请勿尝试在旧拓扑生成器中打开拓扑
<a name="sectionSection2"> </a>

如果您尝试打开使用旧拓扑生成器的拓扑，则会收到以下错误消息。 只能使用 Skype 业务 Server 2019 拓扑生成器查看拓扑。 业务 Server 2019 拓扑生成器的 Skype 必须用于业务服务器 2019年的 Skype 和旧安装创建池。

  


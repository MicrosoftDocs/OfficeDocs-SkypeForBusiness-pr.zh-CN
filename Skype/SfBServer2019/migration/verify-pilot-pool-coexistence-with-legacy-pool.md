---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 用于验证与旧版池共存的引导池的过程。
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243748"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>验证试点池与旧池的共存情况

 **在本文中**
  
[验证 Skype for business Server 2019 服务是否已启动](#sectionSection0)
  
[打开 "Skype for Business 服务器2019控制面板"](#sectionSection1)
  
[不要尝试在旧版拓扑生成器中打开拓扑](#sectionSection2)
  
部署试验池后, 您需要通过使用管理工具查看池信息来验证两个池的共存。 对于 Skype for business Server 2019 池和旧版池, 必须使用 Skype for Business Server 2019 控制面板和拓扑生成器工具。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>验证 Skype for business Server 2019 服务是否已启动
<a name="sectionSection0"> </a>

1. 从 Skype for Business 服务器2019前端服务器, 导航到 "管理 Tools\Services" 小程序。
    
2. 验证以下服务是否在前端服务器上运行:

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
    - 复制副本复制器代理
    - 响应组
    - Web 会议
    - XMPP 翻译网关

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>打开 "Skype for Business 服务器2019控制面板"
<a name="sectionSection1"> </a>

在 Skype for business Server 2019 部署的前端服务器中, 打开 Skype for business Server 2019 控制面板, 然后选择 "旧版" 池。 重复该过程以打开 Skype for Business Server 2019 池。
  
> [!IMPORTANT]
> 在 Skype for business Server 2019 上, 在使用 Skype for Business 服务器控制面板之前, 必须将 Silverlight 升级到 Silverlight 版本5。 
  
此拓扑现在包括旧版和 Skype for business Server 2019 服务器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>不要尝试在旧版拓扑生成器中打开拓扑
<a name="sectionSection2"> </a>

拓扑仅可使用 Skype for Business Server 2019 拓扑生成器查看。 必须使用 Skype for business Server 2019 拓扑生成器为 Skype for business Server 2019 和旧式安装创建池。

  


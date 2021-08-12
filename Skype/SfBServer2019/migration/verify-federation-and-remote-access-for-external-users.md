---
title: 验证联盟和外部用户的远程访问
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
description: 将联盟路由转换到 Skype for Business Server 2019 边缘服务器后，应执行一些功能测试来验证联盟是否按预期运行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。
ms.openlocfilehash: 80a7e5042fb9473e3bbd07438c1f0a57026b1bc5454784973870a695946c0cd7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303326"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>验证联盟和外部用户的远程访问

将联盟路由转换到 Skype for Business Server 2019 边缘服务器后，应执行一些功能测试来验证联盟是否按预期运行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接性

- 来自至少一个联盟域的用户、Skype for Business Server 2019 的内部用户和旧版安装的用户。 测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。
    
- 组织支持 (且其设置已完成的每个公共 IM 服务提供商的用户) 与 Skype for Business Server 2019 上的用户和旧版安装中的用户通信。 
    
- 验证匿名用户是否能够加入会议。
    
- 使用远程用户访问 (日志记录 i nto Lync Server/Skype for Business 从 Intranet 外部但在没有 VPN) 的情况下，使用旧版安装托管的用户与 Skype for Business Server 2019 上的用户和旧版安装的用户。 测试 IM、状态、A/V 和桌面共享。
    
- 在 Skype for Business Server 2019 上使用远程用户访问 (从 Intranet 外部登录到 Skype for Business Server 2019，但没有 VPN) 的用户与 Skype for Business Server 2019 上的用户和旧版安装的用户。 测试 IM、状态、A/V 和桌面共享。
    


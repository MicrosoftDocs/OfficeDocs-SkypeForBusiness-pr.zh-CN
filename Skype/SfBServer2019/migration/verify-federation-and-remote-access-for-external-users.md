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
description: 将联合身份验证路由转换为 Skype for business Server 2019 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751664"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>验证联盟和外部用户的远程访问

将联合身份验证路由转换为 Skype for business Server 2019 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接

- 至少一个联盟域中的用户、Skype for business Server 2019 上的内部用户以及旧安装中的用户。 测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。
    
- 您的组织支持的每个公共 IM 服务提供商的用户（以及已完成的设置）与 Skype for Business Server 2019 上的用户以及旧安装中的用户进行通信。 
    
- 验证匿名用户是否能够加入会议。
    
- 在旧版安装中使用远程用户访问（通过远程用户访问而不是 VPN 登录到 intranet 上的 Lync Server/Skype for Business）与 Skype for Business Server 2019 上的用户以及旧版安装中的用户进行了托管。 测试 IM、状态、A/V 和桌面共享。
    
- 在 Skype for business Server 2019 上托管的用户使用远程用户访问（从 intranet 外部（但不使用 VPN 登录到 Skype for Business Server 2019）与 Skype for business Server 2019 上的用户以及旧安装中的用户。 测试 IM、状态、A/V 和桌面共享。
    


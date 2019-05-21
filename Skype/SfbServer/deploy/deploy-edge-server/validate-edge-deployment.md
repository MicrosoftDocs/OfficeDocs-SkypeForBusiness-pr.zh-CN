---
title: 在 Skype for Business 服务器中验证 Edge 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '摘要: 了解如何验证 Edge 服务器或 Edge 服务器池的部署是否在 Skype for Business 服务器中工作。'
ms.openlocfilehash: 0c432cba78e97add71bb7c4e21e155f92c9fe66a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306886"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>在 Skype for Business 服务器中验证 Edge 部署
 
**摘要:** 了解如何验证 Edge 服务器或 Edge 服务器池的部署是否在 Skype for Business 服务器中工作。
  
部署 Edge 服务器或边缘服务器池后, 您需要知道它是否正常工作。 下面是一些可帮助确保你的边缘环境已连接到内部服务器, 并且你的外部用户可以通过你的边缘连接到 Skype for Business 服务器环境的一些内容。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>验证内部服务器与边缘服务器之间的连接

在安装边缘服务器时自动在边缘服务器或边缘服务器池中完成连接验证时, 你仍然可以通过 Windows PowerShell 确认此操作。 在具有中央管理存储的内部服务器上运行 CsManagementStoreReplicationStatus cmdlet, 或在已安装 Skype for business Server Core 组件 (OcsCore) 的任何加入域的计算机上运行。
  
初次运行此命令的结果可能给出复制状态为 False，而不是 True。如果发生这种情况，请运行 Invoke-CsManagementStoreReplication cmdlet。留些时间让其完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>验证外部用户连接

我们确实有一个很好的工具可用于确认你的 Edge 服务器配置, 并且能够为 Edge 服务器方案连接、发送和接收正确的消息。 这是[远程连接 Anaylzer 网站](https://testconnectivity.microsoft.com/)。 这是由 Microsoft 管理和维护的站点。 若要使用此工具，请通过浏览找到该网站，然后按照指示选择适合你的正确方案。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>测试外部用户连接时应考虑的事项

任何外部用户访问测试应包括贵组织支持的每种类型的内部用户，这可能包括下列任意部分或全部用户：
  
- 来自至少一个联盟域的用户（尽管我们建议测试所有这些域）。
    
- 匿名用户。
    
- 您的组织中远程登录到 Skype for Business 但没有使用 VPN 的用户。
    
这些测试将确定你的边缘服务器是否:
  
- 使用 Telnet 客户端从网络外侦听所需端口。
    
  - 例如：telnet sip.contoso.com 443
    
  - 你应该针对你在 Edge 服务器或 Edge 服务器池中使用的端口执行上述测试, 具体取决于你的部署。
    
- 执行准确的外部 DNS 解析。
    
  - 从您的网络外部, ping 一下 Edge 服务器或边缘服务器池中的每个外部 Fqdn。 即使 ping 失败, 您也可以看到 IP 地址, 您可以比较以前分配的 IP 地址。
    


---
title: 在 Skype for Business Server 2015 中验证边缘部署
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要： 了解如何验证您的部署边缘服务器或边缘服务器池的业务服务器 2015年为工作在 Skype。
ms.openlocfilehash: 02f909310e6b491ae97e31b7013b1307c7688ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中验证边缘部署
 
**摘要：**了解如何验证您的部署边缘服务器或边缘服务器池的业务服务器 2015年为工作在 Skype。
  
一旦部署边缘服务器或边缘服务器池，您需要知道它可以正确工作。 以下是一些可以帮助您完成确认连接边缘环境的操作您的内部服务器，而且还需要的外部用户可以连接到您 Skype 业务服务器 2015年环境通过您的边。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>验证内部服务器与边缘服务器之间的连接

同时连接的验证在边缘服务器或边缘服务器池自动完成的安装边缘服务器时，您可以仍确认为自己与 Windows PowerShell。 它具有集中管理存储，或者安装任何域联接的计算机上的 Skype 业务服务器 2015年核心组件 (OcsCore.msi) 内部的服务器上运行获取 CsManagementStoreReplicationStatus cmdlet。
  
初次运行此命令的结果可能给出复制状态为 False，而不是 True。如果发生这种情况，请运行 Invoke-CsManagementStoreReplication cmdlet。留些时间让其完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>验证外部用户连接

我们有很好的工具确认您的边缘服务器配置和连接、 发送和接收边缘服务器情况的正确消息的能力。 它是[远程连接 Anaylzer 站点](https://testconnectivity.microsoft.com/)。 这是由 Microsoft 管理和维护的站点。 若要使用此工具，请通过浏览找到该网站，然后按照指示选择适合你的正确方案。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>测试外部用户连接时应考虑的事项

任何外部用户访问测试应包括贵组织支持的每种类型的内部用户，这可能包括下列任意部分或全部用户：
  
- 来自至少一个联盟域的用户（尽管我们建议测试所有这些域）。
    
- 匿名用户。
    
- 您组织中的用户，远程登录到 Skype 的业务，但不使用 VPN。
    
这些测试将确定是否边缘服务器：
  
- 使用 Telnet 客户端从网络外侦听所需端口。
    
  - 例如：telnet sip.contoso.com 443
    
  - 应您根据您的部署使用边缘服务器池或边缘服务器的端口上执行上述测试。
    
- 执行准确的外部 DNS 解析。
    
  - 从您的网络之外 ping 每个外部边缘服务器或边缘服务器池的 Fqdn。 即使 ping 操作失败，您将看到 IP 地址，可以将以前已分配的 IP 地址进行比较。
    


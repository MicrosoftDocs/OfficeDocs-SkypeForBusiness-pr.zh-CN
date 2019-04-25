---
title: 验证边缘部署中 Skype 业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要： 了解如何验证边缘服务器或边缘服务器池的部署中 Skype 工作业务服务器。
ms.openlocfilehash: 63c4cb1af599da191d0e0f4b95cfdaa775a64ba4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223787"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>验证边缘部署中 Skype 业务服务器
 
**摘要：** 了解如何验证边缘服务器或边缘服务器池的部署中 Skype 工作业务服务器。
  
一旦您已经部署了边缘服务器或边缘服务器池，您需要知道正常运行。 下面是一些可帮助进行确认连接边缘环境的操作的内部服务器，而且还需要的外部用户可以连接到业务服务器环境您 Skype 通过您的边缘。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>验证内部服务器与边缘服务器之间的连接

时的连接验证自动完成边缘服务器或边缘服务器池中安装边缘服务器时，您可以仍确认为自己使用 Windows PowerShell。 安装任何域联接的计算机上的业务 Server 核心组件 (OcsCore.msi) 的 Skype 或包含中央管理存储、 的内部服务器上运行 Get-csmanagementstorereplicationstatus cmdlet。
  
初次运行此命令的结果可能给出复制状态为 False，而不是 True。如果发生这种情况，请运行 Invoke-CsManagementStoreReplication cmdlet。留些时间让其完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>验证外部用户连接

我们用于确认您的边缘服务器配置，并能够连接、 发送和接收的边缘服务器方案的正确消息的绝佳工具。 它是[远程连接 Anaylzer 网站](https://testconnectivity.microsoft.com/)。 这是由 Microsoft 管理和维护的站点。 若要使用此工具，请通过浏览找到该网站，然后按照指示选择适合你的正确方案。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>测试外部用户连接时应考虑的事项

任何外部用户访问测试应包括贵组织支持的每种类型的内部用户，这可能包括下列任意部分或全部用户：
  
- 来自至少一个联盟域的用户（尽管我们建议测试所有这些域）。
    
- 匿名用户。
    
- 组织中的用户，在远程登录到 for Business 的 Skype 但不使用 VPN。
    
这些测试将确定是否边缘服务器：
  
- 使用 Telnet 客户端从网络外侦听所需端口。
    
  - 例如：telnet sip.contoso.com 443
    
  - 您应在您将在边缘服务器或边缘服务器池，具体取决于您的部署的端口执行上述测试。
    
- 执行准确的外部 DNS 解析。
    
  - 从在网络外部 ping 每个边缘服务器或边缘服务器池的外部 Fqdn。 即使 ping 失败，您将看到的 IP 地址，它可以比较之前已分配的 IP 地址。
    


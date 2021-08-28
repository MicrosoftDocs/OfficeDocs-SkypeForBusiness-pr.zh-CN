---
title: 在部署中验证Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要：了解如何验证边缘服务器或边缘服务器池的部署是否Skype for Business Server。
ms.openlocfilehash: 175baab9770e6013820e0e632712bf75b7669a57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583236"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>在部署中验证Skype for Business Server
 
**摘要：** 了解如何验证边缘服务器或边缘服务器池的部署是否正在Skype for Business Server。
  
部署边缘服务器或边缘服务器池后，需要知道其是否正常工作。 以下是一些有助于确认边缘环境已连接到内部服务器，以及外部用户是否可以通过边缘连接到 Skype for Business Server 环境。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>验证内部服务器和边缘服务器之间的连接

虽然安装边缘服务器后，连接验证会在边缘服务器或边缘服务器池中自动完成，但您仍可使用 Windows PowerShell。 在Get-CsManagementStoreReplicationStatus中央管理存储的内部服务器上或安装了核心组件的任何加入域Skype for Business Server运行 (OcsCore.msi) cmdlet。
  
运行此命令的初始结果可能会为复制提供 False 状态，而不是 True。 如果发生这种情况，运行 Invoke-CsManagementStoreReplication cmdlet。 请给它一些时间来完成复制，然后再次Get-CsManagementStoreReplicationStatus cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>验证外部用户的连接性

我们提供了一个出色的工具，用于确认边缘服务器配置，以及连接、发送和接收边缘服务器方案的正确消息的能力。 它是远程 [连接分析分析站点](https://testconnectivity.microsoft.com/)。 这是由 Microsoft 支持管理和维护的网站。 若要使用此工具，请浏览到网站并按照说明选择适合你的方案。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>测试外部用户连接时要考虑的问题

任何外部用户访问测试都需要包括组织支持的每种类型的内部用户，其中可能包括以下任意或全部：
  
- 来自至少一个联盟域的用户 (我们建议你通过联合域测试) 。
    
- 匿名用户。
    
- 组织中已登录的用户Skype for Business，但没有使用 VPN。
    
这些测试将确定边缘服务器是否：
  
- 使用 Telnet 客户端从网络外侦听所需端口。
    
  - 例如：telnet sip.contoso.com 443
    
  - 您应对边缘服务器或边缘服务器池上使用的端口执行上述测试，具体取决于您的部署。
    
- 执行准确的外部 DNS 解析。
    
  - 从网络外部 ping 边缘服务器或边缘服务器池的每个外部 FQDN。 即使 ping 失败，您也会看到 IP 地址，可以比较之前分配的 IP 地址。
    


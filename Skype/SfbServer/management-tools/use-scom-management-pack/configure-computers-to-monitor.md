---
title: 配置将受视的 Skype for Business Server 计算机
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要： 安装上业务服务器 2015年计算机要监视，Skype 的运营经理代理文件和配置作为系统中心代理的计算机。
ms.openlocfilehash: bbf2abfe2617b8bc03dd56d3ecdafc25643ba17e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>配置将受视的 Skype for Business Server 计算机
 
**摘要：**安装业务服务器 2015年计算机要监视，Skype 的运营经理代理文件和配置作为系统中心代理的计算机。
  
每个 Skype 为想要监视的业务服务器 2015年计算机必须能够自我报告其存在到管理服务器。 为了启用此过程，必须在每台要受监视的计算机上安装 Operations Manager 代理文件。 安装代理文件后，必须将计算机配置为作为 System Center 代理。 请确保您首次安装和 Skype 业务服务器上配置这些计算机在执行这些过程之前。
  
## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>在位于外围网络外的观察程序节点上安装证书
<a name="watcher_node_outside"> </a>

系统中心操作管理器代理运行在外围网络 （如业务服务器边缘服务器 Skype) 外企业 （如外部综合事务观察程序节点中），或需要通过 Active Directory 信任边界，系统中心操作管理器网关服务器的配置。 此服务器角色可使与根管理服务器没有信任关系的代理发出警报。 有关详细信息，请参阅[管理运营经理 2012年中的网关服务器](https://technet.microsoft.com/en-us/library/hh212823.aspx)。
  
如果部署代理程序在两个位置之一时，将需要请求并配置证书，使观察者节点向系统中心操作管理器发送警报。 若要简化这一过程，运营经理团队已创建一组实用程序，您可以请求并观察程序节点计算机上安装正确的证书类型。 有关详细信息，以及要下载这些实用工具，请参阅[为非域加入代理进行简单与证书生成向导获取证书](http://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。
  
### <a name="installing-the-operation-manager-agent-files"></a>安装 Operation Manager 代理文件

1. 在 System Center 安装介质上，双击“Setup.exe****”。
    
2. 在系统中心操作管理器安装向导中，单击**安装操作管理器代理**，请从安装在可选安装的代理
    
3. 在系统中心安装向导中，在欢迎系统中心操作管理器安装向导页中，单击**下一步**。
    
4. 在目标文件夹页中，选择的文件夹的操作管理器代理文件将被安装，单击**下一步**。
    
5. 在“管理组配置”页面上选择“指定管理组信息”****。然后单击“下一步”****。
    
6. 在管理组配置页上，请在**管理组名称**框中，键入操作管理器管理组的名称，然后键入您的操作管理器服务器的主机名 (例如，atl-scom-001) 在**管理服务器**框。 如果更改操作管理器使用的端口号，请在**管理服务器端口**框中输入新的端口号。 否则为保留 5723，默认值的端口，然后单击**下一步**。
    
7. 在“代理操作帐户”页面上，选择“本地系统”****，然后单击“下一步”****。
    
8. 在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”****，然后单击“下一步”****。
    
9. 在“安装准备就绪”页面上，单击“安装”****。
    
10. 在完成系统中心操作管理器安装向导页上，单击**完成**。
    
11. 单击“退出”****。
    
对于 System Center 2012，您可以验证已通过单击**「 开始 」**，然后单击**所有程序**、**系统中心操作管理器 2012**年，**操作管理器外壳 2012年**创建了代理。 在操作管理器外壳中，键入下面的 Windows PowerShell 命令，然后按 enter 键：
```
Get-SCOMAgent
```

所有 Operations Manager 代理的列表将出现在屏幕上。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>将 Skype for Business Server 计算机配置为参加 System Center Discovery
<a name="watcher_node_outside"> </a>

若要确保该业务服务器代理为您新 Skype 参与发现过程系统中心操作管理器，您必须完成系统中心操作管理器控制台安装位置的每台计算机上的以下过程：
  
1. 在“管理”选项卡上，单击“代理托管”****。
    
2. 单击“发现向导”****，然后完成向导，以使计算机能被发现。
    
3. 重新启动健康代理服务。 重新启动该服务将强制发现新计算机。 如果不重新启动该服务，它可能需要最长为 4 个小时前发现新计算机系统中心操作管理器。 
    
4. 验证 Operations Manager 事件日志中是否未记录任何错误事件。
    
5. 其中成功推送代理的计算机将显示在"代理托管"列表下，代理手动安装的计算机将显示在"挂起管理"下，单击计算机名称和批准。
    
6. 右键单击计算机的名称，然后单击“属性”****。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。
    


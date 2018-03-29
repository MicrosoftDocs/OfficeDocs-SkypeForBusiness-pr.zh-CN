---
title: 配置主管理服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 摘要： 配置您的主管理服务器、 安装系统中心操作管理器，并为 Skype 的管理包导入的业务服务器 2015年。
ms.openlocfilehash: 6554ddc3fbe99ba70663b72794eb59dfc5d0d3e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-primary-management-server"></a>配置主管理服务器
 
**摘要：**配置主管理服务器、 安装系统中心操作管理器，并为 Skype 的管理包导入的业务服务器 2015年。
  
要充分利用新的运行状况监视包含在 Skype 业务服务器 2015年能力，必须先指定要用作您的主管理服务器的计算机。 然后必须在该计算机上安装 SP1 系统中心操作管理器 2012 R2 或系统中心操作管理器 2007 R2。 此外，您必须首先安装受支持的版本的 SQL Server 为操作管理员后端数据库的功能。
  
在安装系统中心操作管理器时，您需要安装该产品，所有的组件包括：
  
- 操作数据库
    
- 服务器
    
- 控制台
    
- Windows PowerShell cmdlet
    
- Web 控制台
    
- 报告
    
- 数据仓库
    
> [!IMPORTANT]
> 需要安装系统中心操作管理器 2012年之前安装"[Microsoft 报表查看器 2010年可再发行组件包](https://www.microsoft.com/en-us/download/details.aspx?id=6442)"。 
  
有关这些产品及其安装方法的详细信息，请参阅以下链接：
  
- [系统中心操作管理器 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)
    
- [系统中心操作管理器 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)
    
请记住您可以让每 Skype 的只有一根管理服务器业务服务器部署。
  
## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>导入 Skype for Business Server 2015 管理包

通过安装管理包，可以扩展系统中心操作管理器的功能 — — 规定这项系统中心操作管理器可以监视的软件，如何应监视的项目，并应触发警报的方式，报告。 Skype 的业务服务器 2015年包括两个系统中心操作管理器管理包中提供了以下功能：
  
- **组件和用户管理包**(Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 跟踪 Skype 业务服务器问题记录在事件日志、 性能计数器注册或呼叫详细记录 (Cdr) 或体验质量 (QoE) 数据库中的记录。 关键的问题，系统中心操作管理器可以配置为立即通知通过电子邮件、 即时消息或消息 SMS 管理员。 （SMS，即短消息服务，是一种用来将文本消息从一个移动设备发送到另一个移动设备的技术）。
    
    > [!NOTE]
    >  有关配置运营经理通知的详细信息，请参阅[配置通知](http://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。 
  
- **活动监视管理包**(Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 主动测试的密钥 Skype 业务服务器组件，例如，登录到系统，交换即时消息，或打电话到位于公用交换的电话网 (PSTN 电话). 这些测试是使用 Skype for Business Server 综合事务 cmdlet 来执行的。 例如，**Test-CsIM** cmdlet 用来模拟一对测试用户之间的即时消息对话。 如果这种模拟的对话失败，就会生成警报。
    
导入管理包是关键的一步。如果未导入管理包，就不能使用 Operations Manager 来监视 Skype for Business Server 事件，也不能运行 Skype for Business Server 综合事务。 
  
组件和用户管理包仅用于监视 Skype for Business Server 2015。如果是在共存情况下，也就是同时安装了 Skype for Business Server 2015 和 Lync Server 2013，那么 Lync Server 2013 计算机应继续使用 Lync Server 2013 管理包。
  
> [!NOTE]
> Skype for Business Server 2015 的管理包中包含 Business Server 2015 组件和用户管理包，以及 Skype for Business Server 2015 主动监控管理包。 
  
可使用下列任一工具导入管理包：
  
- **系统中心操作管理器**使用此方法，您可以使用运营经理将 Skype 业务服务器的监控。
    
- **操作管理器外壳**可以使用操作管理器外壳程序直接导入，或通过系统中心操作管理器控制台导入管理包时遇到的任何问题进行故障排除。
    
### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 导入管理包

1. 从 Microsoft Web 下载网站下载 SkypeForBusiness2015ManagementPacks.msi，然后安装该 msi。
    
2. 在系统中心操作管理器中，单击**管理**。
    
3. 在管理窗格中，右键单击**管理包**，，然后单击**导入管理包**。
    
4. 在“选择管理包”****对话框中，单击“添加”****，然后单击“从磁盘中添加”****。
    
5. 在“联机目录连接”****对话框中，单击“否”****。
    
6. 在“选择要导入的管理包”****对话框中，查找并选择文件“Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp”和“Microsoft.LS.2015.Monitoring.ComponentAndUser.mp”，然后单击“打开”****。若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击后续文件。
    
7. 在“选择管理包”****对话框中，单击“安装”****。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。
    
8. 在“选择管理包”****对话框中，单击“关闭”****。导入和安装过程可能需要几分钟时间才能完成。
    
## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager Shell 导入管理包

一般来说，使用 Operations Manager 控制台导入管理包要更容易。但是，如果发生错误并且导入失败，则控制台不会总是提供足够的错误报告。相比之下，Operations Manager Shell 提供了详细信息。如果您使用的是 Operations Manager 并且导入管理包时遇到问题，请使用 Operations Manager Shell 导入包。Operations Manager Shell 提供了可帮助您确定导入失败原因的信息。
  
1. 依次单击“开始”****、“所有程序”****、“Microsoft System Center 2012”****、“Operations Manager”****和“Operations Manager Shell”****。
    
2. 在 Operations Manager Shell 中，在命令提示符处键入以下命令，使用文件 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 的副本的实际路径，然后按 Enter：
    
  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
  ```

3. 导入第一个管理包之后，使用至文件 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：
    
  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
  ```



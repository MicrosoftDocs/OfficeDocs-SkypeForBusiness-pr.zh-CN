---
标题:"准备架构"ms.author: jambirk 作者： jambirk 管理器： serdars ms.date: 2/8/2018 ms.audience: ms.topic it 专业人员： 文章 f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep ms.prod: Skype-的-业务-it 专业人员 localization_priority： 正常 ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c 描述:"要准备 Active Directory 域服务架构，运行准备架构在 Skype 的步骤为业务服务器部署向导。 单击运行开始架构的准备工作。 “准备架构”步骤会在运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中读取提供的架构定义文件。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已完成，并成功"。
---

# <a name="prepare-schema"></a>准备架构
 
要准备 Active Directory 域服务的架构，准备架构步骤中运行 Skype 业务服务器部署向导。 单击“**运行**”可开始准备架构。 “准备架构”步骤会在运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中读取提供的架构定义文件。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
  
> [!IMPORTANT]
> 要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。 
  
添加类和属性来扩展 Active Directory 域服务架构以支持 Skype 业务服务器 2015年服务器、 服务和用户对象。 在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。 有关 sp1 的 Windows Server 2008 R2 的备份过程的详细信息，请参阅[https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)。 Windows Server 2003 和 Windows Server 2003 R2，请参阅[https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)。
  
> [!CAUTION]
> 扩展架构是不可逆的。 应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。 在通信中断或服务器上出现任何其他故障的情况下，这一点尤为重要。 您应该执行架构主机的域控制器的备份和完整备份的活动目录。 
  
若要执行的备份架构主机的域控制器和活动目录的完整备份：
  
1. 断开担当架构主机角色的域控制器与网络的连接。
    
2. 对担当架构主机角色的域控制器执行系统状态备份。
    
3. 扩展架构。
    
4. 架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。
    
5. 架构扩展故障的意外，使用前面花费在系统状态备份还原 Active Directory 和域控制器的系统状态。
    
> [!NOTE]
> 如果您需要查看由 Skype 业务服务器部署向导创建的日志文件，您可以找到计算机上部署向导已运行，请运行步骤的 Active Directory 用户的用户目录中的文件。 例如，如果用户作为 Contoso.net 域中的域管理员登录，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


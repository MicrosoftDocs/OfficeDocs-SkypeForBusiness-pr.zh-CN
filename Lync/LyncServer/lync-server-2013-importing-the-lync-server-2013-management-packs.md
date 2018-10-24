---
title: 导入 Lync Server 2013 管理包
TOCTitle: 导入 Lync Server 2013 管理包
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205052(v=OCS.15)
ms:contentKeyID: 49313480
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 导入 Lync Server 2013 管理包

 

_**上一次修改主题：** 2016-12-08_

您可通过安装管理包（指示 System Center Operations Manager 可监视的项目和警报的触发以及报告方式的软件）来扩展 System Center Operations Manager 的功能。Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供了下列功能：

  - 组件和用户管理包 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 跟踪事件日志中记录的、性能计数器登记的、或呼叫详细信息记录 (CDR) 或用户质量体验 (QoE) 数据库中记录的 Lync Server 问题。对于严重的问题，可将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或短信服务 (SMS) 消息通知管理员。（SMS 是将文本消息从一台移动设备发送到另一台所使用的技术。）
    
    > [!NOTE]  
    > 有关配置 Operations Manager 通知的详细信息，请参阅 TechNet 库中的“配置通知”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x804</a>。
    


  - 主动监控管理包 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主动测试主要 Lync Server 组件，如登录系统、交换即时消息或者向公用电话交换网 (PSTN) 中的电话发出呼叫。这些测试是使用 Lync Server 综合事务 cmdlet 执行的。例如，您可使用 **Test-CsIM** cmdlet 在一对测试用户之间模拟即时消息 (IM) 对话。如果此命令模拟消息对话失败，则将生成警报。

您需要导入管理包。如果您未导入管理包，则无法使用 Operations Manager 监控 Lync Server 服务器或运行 Lync Server 综合事务。

组件和用户管理包仅用于监控 Lync Server 2013。如果您处于安装了 Lync Server 2013 和 Lync Server 2010 的共存方案中，则应继续使用 Lync Server 2010 计算机的 Lync Server 2010 管理包。

> [!NOTE]  
> Lync Server 2010 的管理包包含 Lync Server 2010 监控管理包和 Lync Server 2010 群聊监控管理包。



可使用下列任一工具导入管理包：

  - **System Center Operations Manager**   通过此方法，您可使用 Operations Manager 添加对 Lync Server 的监控。

  - **Operations Manager Shell**   您可使用 Operations Manager Shell 直接导入或解决使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。

## 使用 System Center Operations Manager 导入管理包

1.  下载文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。

2.  在 System Center Operations Manager 中，单击“管理”。

3.  在“管理”窗格中，右键单击“管理包”，然后单击“导入管理包”。

4.  在“选择管理包”对话框中，单击“添加”，然后单击“从磁盘中添加”。

5.  在“联机目录连接”对话框中，单击“取消”以阻止 Operations Manager 联机查看 Lync Server 管理包是否存在任何依赖关系。如果您使用的是 System Center Operations Manager 2012，则单击“否”。

6.  在“选择要导入的管理包”对话框中，查找并选择“Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp”和“Microsoft.LS.2013.Monitoring.ComponentAndUser.mp”，然后单击“打开”。若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击第二个文件。

7.  在“选择管理包”对话框中，单击“安装”。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。

8.  在“选择管理包”对话框中，单击“关闭”。请注意，导入和安装过程可能需要几分钟时间才能完成。

## 使用 Operations Manager Shell 导入管理包

一般来说，使用 Operations Manager 导入管理包要更容易。但是，如果发生错误并且导入失败，则控制台不会始终提供足够的错误报告。相比之下，Operations Manager Shell 提供了详细信息。如果您使用的是 Operations Manager 并且导入管理包时遇到问题，请使用 Operations Manager Shell 导入包。Operations Manager Shell 提供了可能帮助您确定导入失败原因的详细信息。

如果您使用的是 System Center Operations Manager 2007 R2，请完成以下过程：

1.  依次单击“开始”、“所有程序”、“System Center Operations Manager 2007 R2”和“Operations Manager Shell”。

2.  在 Operations Manager Shell 中，在命令提示符处键入以下命令，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径，然后按 Enter：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  关闭 Operations Manager Shell。

如果您使用的是 System Center Operations Manager 2012，请完成以下过程：

1.  依次单击“开始”、“所有程序”、“Microsoft System Center 2012”、“Operations Manager”和“Operations Manager Shell”。

2.  在 Operations Manager Shell 中，在命令提示符处键入以下命令，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径，然后按 Enter：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"


---
title: Lync Server 2013：针对灾难恢复部署配对的前端池
TOCTitle: 针对灾难恢复部署配对的前端池
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204773(v=OCS.15)
ms:contentKeyID: 49312391
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中针对灾难恢复部署配对的前端池

 

_**上一次修改主题：** 2013-02-21_

您可以使用 拓扑生成器轻松部署已配对 前端池的灾难恢复拓扑。

## 部署配对前端池

1.  如果是新池并且尚未定义，请使用 拓扑生成器创建这些池。

2.  在拓扑生成器中，右键单击两个池之一，然后单击“编辑属性”。

3.  在左侧窗格中单击“复原”，然后在右侧窗格中选择“关联的备份池”。

4.  在“关联的备份池”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。
    
    ![“复原”对话框](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "“复原”对话框")  

5.  选择“语音的自动故障转移和故障回复”，然后单击“确定”。
    
    当您查看该池的详细信息时，关联的池现在显示在“复原”下的右窗格中。

6.  使用 拓扑生成器发布拓扑。

7.  如果尚未部署两个池，请立即部署它们，配置随即完成。您可以跳至此过程的最后两步。
    
    但是，如果在定义配对关系之前已部署池，那么必须完成以下两个最终步骤。

8.  在两个池的每个前端服务器上，运行以下命令：
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    这将配置确保备份配对正常运行所需的其他服务。

9.  从 Lync Server 命令行管理程序 命令提示符处，运行以下命令：
    
        Start-CsWindowsService -Name LYNCBACKUP

10. 使用以下 cmdlet 强制两个池的用户和会议数据相互同步：
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>

       &nbsp;
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    
    同步数据可能需要一些时间。您可以使用以下 cmdlet 检查同步状态。确保两个方向的状态均保持稳定。
    
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>

       &nbsp;
    
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>

> [!NOTE]  
> 拓扑生成器 中的“语音的自动故障转移和故障回复”选项和关联的时间间隔仅适用于 Lync Server 2010 中引入的语音复原功能。选择此选项并不意味着本文档中讨论的池故障转移将自动执行。池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。



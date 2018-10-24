---
title: 配置 SCOM 监控
TOCTitle: 配置 SCOM 监控
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49888389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 SCOM 监控

 

_**上一次修改主题：** 2012-10-04_

迁移到 Microsoft Lync Server 2013 之后，您必须完成几项任务才能将 Lync Server 2013 配置为使用 System Center Operations Manager。

  - 对选择用来管理中央发现逻辑的服务器应用 Lync Server 2010 更新。

  - 更新中央发现候选服务器注册表项。

  - 将主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。

下面提供了有关执行所有这些任务的说明。

**对选择用来管理中央发现逻辑的服务器应用 Lync Server 2010 更新。**

1.  选择安装了 System Center Operations Manager 代理文件且配置为候选发现节点的服务器。

2.  对此服务器应用 Lync Server 2010 更新。请参阅主题 [应用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)。

**更新中央发现候选服务器注册表项。**

1.  在选择用来管理中央发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。

2.  在命令行中键入：
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"

       &nbsp;
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
    
    > [!NOTE]  
    > 在您编辑注册表时，如果已存在注册表项，则您可能会遇到一个指示命令失败的错误。如果遇到此错误，可以安全地将其忽略。
    


**将主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。**

1.  在已安装 System Center Operations Manager 控制台的计算机上，展开“管理包对象”，然后选择“对象发现”。

2.  单击“更改范围”。

3.  从“范围管理包对象”页中，选择“LS 发现候选”。

4.  将“LS 发现候选有效值”覆盖为在之前的过程中选定的候选服务器的名称。

最后，若要最终完成您的更改，请重新启动 System Center Operations Manager Root Management Server 上的运行状况服务。


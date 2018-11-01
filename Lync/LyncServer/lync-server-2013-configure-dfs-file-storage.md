---
title: Lync Server 2013：配置文件存储
TOCTitle: 配置文件存储
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205150(v=OCS.15)
ms:contentKeyID: 49313869
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 配置文件存储

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持在分布式文件系统 (DFS) 上使用文件共享。有关 Windows Server 2008 的 DFS 的详细信息，请参阅“Windows Server 2008 的 DFS 分步指南”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。若要使用 DFS，Lync Server 2013 需要遵循以下要求：

  - 命名空间基于域

  - 所有命名空间服务器都至少运行 Windows 2008

Lync Server 2013 安装要求共享文件夹上的权限允许管理员完全访问。 Lync Server 2013 随后会使用对 ACL 文件夹的 NTFS 文件权限。继承的 DFS 共享权限不会用于限制访问。

有关文件共享要求的更多详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。

以下过程介绍如何使用 DFS 命名空间向导（如 DFS 安装指南中所述）正确配置共享文件夹权限。

## 配置共享文件夹权限

1.  单击“开始”，指向“所有程序”，指向“管理工具”，然后单击“DFS 管理”。

2.  在“DFS 管理”管理单元的控制台树中，右键单击命名空间服务器（如 filesrv1.contoso.com），然后单击“编辑设置”。

3.  选择“共享文件夹权限”。

4.  选择“使用自定义权限”。

5.  对于 Administrator 组，在“允许”下选择以下选项：
    
      - “完全控制”
    
      - “更改”
    
      - “读取”

6.  单击“应用”，然后单击“确定”。


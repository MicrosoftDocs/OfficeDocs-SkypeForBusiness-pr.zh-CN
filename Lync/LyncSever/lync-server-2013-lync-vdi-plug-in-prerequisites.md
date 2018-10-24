---
title: Lync Server 2013：Lync VDI 插件先决条件
TOCTitle: Lync VDI 插件先决条件
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205304(v=OCS.15)
ms:contentKeyID: 49314439
ms.date: 03/08/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Lync VDI 插件先决条件

 

_**上一次修改主题：** 2017-03-07_

在虚拟桌面基础结构 (VDI) 环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。

> [!NOTE]  
> 有关如何安装和部署虚拟化环境的详细信息，请咨询虚拟化解决方案提供商。有关基于 Hyper-V 和远程桌面服务部署虚拟化环境的信息，请参阅 Microsoft TechNet 库中的以下文章：
<ul>
<li><p>Hyper-V（网址为 <a href="http://go.microsoft.com/fwlink/?linkid=247514" class="uri">http://go.microsoft.com/fwlink/?linkid=247514</a>）</p></li>
<li><p>Windows Server 2008 R2 的远程桌面服务（网址为 <a href="http://go.microsoft.com/fwlink/?linkid=247513" class="uri">http://go.microsoft.com/fwlink/?linkid=247513</a>）</p></li>
</ul>



以下是对数据中心计算机上运行的虚拟机的要求：

  - 虚拟机必须配置有 Windows 8、 Windows 7 或安装了最新 Service Pack 的 Windows Server 2008 R2。

以下是对用户和用户的本地计算机的要求：

  - 用户必须驻留在 Lync Server 2013 上。

  - 本地计算机必须运行 Windows Embedded Standard 7 SP1、 Windows 7 SP1 或 Windows 8。

  - 如果使用远程桌面服务， Lync VDI 插件位元（即，应用程序是 32 位还是 64 位）必须与本地计算机的操作系统的位元匹配。本地计算机的操作系统的位元和虚拟机的操作系统的位元无需匹配。如果使用其他虚拟化解决方案或平台，请参阅该虚拟化解决方案提供商关于位元要求的指南。

  - 本地计算机必须运行最新版的远程桌面客户端。可以从 Microsoft 获得远程桌面服务客户端的最新更新并安装，或从虚拟化解决方案提供商获得最新的远程桌面客户端。有关最新的远程桌面服务更新，请参阅 <http://go.microsoft.com/fwlink/?linkid=268032>。

  - 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。若要在 Windows 中配置远程桌面连接的这些设置，请参阅下一节“配置远程桌面连接设置”。

## 配置远程桌面连接设置

要在 Windows 中为 Lync VDI 插件准备远程桌面连接，请执行以下步骤。

1.  如果本地计算机正在运行 Windows 8，请跳过此步骤。如果本地计算机正在运行 Windows 7 SP1，请安装最新 Windows 8 版本的远程桌面服务客户端，网址为 <http://go.microsoft.com/fwlink/?linkid=268032>。

2.  通过单击“开始”，然后单击“远程桌面连接”，启动远程桌面服务客户端。

3.  单击“选项”。

4.  单击“本地资源”选项卡。在“远程音频”下，单击“设置”，然后执行以下操作：
    
      - 在“远程音频播放”下，选择“在此计算机上播放”。
    
      - 在“远程音频录制”下，选择“不录制”。
    
      - 单击“确定”。

5.  单击“体验”选项卡。在“性能”下，清除“持久位图缓存”复选框。

6.  单击“常规”选项卡。在“计算机”中，键入虚拟机的名称，然后单击“连接”。


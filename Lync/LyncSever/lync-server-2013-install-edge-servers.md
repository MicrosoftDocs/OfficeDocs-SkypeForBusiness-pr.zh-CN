---
title: Lync Server 2013：安装边缘服务器
TOCTitle: 安装边缘服务器
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398230(v=OCS.15)
ms:contentKeyID: 49312111
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装适用于 Lync Server 2013 的边缘服务器

 

_**上一次修改主题：** 2012-09-08_

使用 Lync Server 部署向导在边缘服务器上安装 Lync Server 2013。通过在每台边缘服务器上运行部署向导，可以完成设置边缘服务器所需的大部分任务。要在边缘服务器上部署 Lync Server 2013，必须已运行 拓扑生成器定义和发布边缘服务器拓扑，并且已将拓扑导出到可从边缘服务器进行访问的媒体。有关详细信息，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)和 [导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

使用部署向导安装每台边缘服务器、安装并分配所需证书以及启动所需服务后，通过使用 [在 Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)中的信息启用和配置外部用户访问，并使用 [在 Lync Server 2013 中验证边缘部署](lync-server-2013-verifying-your-edge-deployment.md)中的信息验证安装（包括服务器和客户端连接），即可完成安装。

## 安装边缘服务器

1.  以本地 Administrators 组成员的身份或使用具有等效用户权限的帐户登录到要安装边缘服务器的计算机。

2.  请确保使用 拓扑生成器创建、然后导出并复制到外部媒体的拓扑配置文件在边缘服务器上可用（例如，访问拓扑配置文件复制到的 USB 驱动器，或验证能否访问文件复制到的网络共享）。

3.  启动部署向导。
    
    > [!NOTE]  
    > 如果收到需要安装 Microsoft Visual C++ 可再发行软件包的消息，请单击“是”。在下一个对话框中，接受默认的“安装位置”或单击“浏览”选择备用位置，然后单击“安装”。在下一个对话框中，选中“我接受许可协议中的条款”复选框，然后单击“确定”。
    


4.  在部署向导中，单击“安装或更新 Lync Server 系统”。

5.  向导确定部署状态后，对于“步骤 1. 安装本地配置存储”，单击“运行”，然后执行以下操作：
    
      - 在“配置中央管理存储的本地副本”对话框中，单击“从文件导入(建议用于边缘服务器)”，转到拓扑配置文件导出到的位置，选择 .zip 文件，单击“打开”，然后单击“下一步”。
    
      - 部署向导从配置文件读取配置信息，并将 XML 配置文件写入本地计算机。
    
      - “正在执行命令”过程完成后，单击“完成”。

6.  在部署向导中，单击“步骤 2: 安装或删除 Lync Server 组件”安装本地计算机上存储的 XML 配置文件中指定的 Lync Server 2013 边缘组件。

7.  安装完成后，在启动服务前使用[为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)中的信息安装并分配所需证书。


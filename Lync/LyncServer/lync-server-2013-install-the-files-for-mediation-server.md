---
title: Lync Server 2013：安装中介服务器的文件
TOCTitle: 安装中介服务器的文件
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412998(v=OCS.15)
ms:contentKeyID: 49314694
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中安装中介服务器的文件

 

_**上一次修改主题：** 2012-08-06_

要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。

使用本主题中的步骤运行 Lync Server 2013 部署向导，以在使用拓扑生成器定义和发布池时添加到 中介服务器池的计算机上为 中介服务器安装文件。为 中介服务器安装文件时，还会安装和分配 中介服务器池中的每台计算机所需的证书。

在此站点上，如果已部署 前端池或 Standard Edition Server 上并置的 中介服务器，可跳过本主题，而继续执行 [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。

> [!NOTE]  
> 本主题假设您已按部署文档的 <a href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">在 Lync Server 2013 拓扑生成器中定义中介服务器</a>和 <a href="lync-server-2013-publish-the-topology.md">在 Lync Server 2013 中发布拓扑</a>中所述定义和发布独立的 中介服务器池，且已确定 中介服务器池中的计算机满足 <a href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync Server 2013 中企业语音的软件先决条件</a>和 <a href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync Server 2013 中企业语音的安全性和配置先决条件</a>中所述的先决条件。



## 为独立的中介服务器池安装文件

1.  在安装介质中，右键单击 *\<installation media\>***\\Setup\\amd64\\Setup.exe**，然后单击“以管理员身份运行”。

2.  在“安装位置”页上，单击“确定”。

3.  在“最终用户许可协议”页上，单击“我接受”，然后单击“确定”。（必须单击该按钮才能继续。）

4.  在“Lync Server 2010 部署向导”页上，单击“安装或更新 Lync Server 系统”。

5.  单击“步骤 1: 安装本地配置存储”旁边的“运行”，然后按照屏幕上的说明进行操作。

6.  在“配置中央管理存储的本地副本”页上，接受默认的“直接从中央管理存储检索”，然后单击“下一步”。

7.  在“正在执行命令”页上，当任务状态显示为“已完成”时，单击“完成”。

8.  单击“步骤 2: 安装或删除 Lync Server 组件”旁边的“运行”，然后单击“下一步”。

9.  在“正在执行命令”页上，当任务状态显示为“已完成”时，单击“完成”。

10. 单击“步骤 3: 请求、安装或分配证书”旁边的“运行”。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”两次：第一次是颁发所需证书，第二次是分配该证书。

11. 正确颁发并分配证书后，在“步骤 4: 启动服务”旁边，单击“运行”，然后按照屏幕上的说明进行操作。

12. 成功完成“步骤 4”后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。

13. 在运行 Lync Server 控制面板的计算机上，在 Lync Server 控制面板的“拓扑”页上验证中介服务器的服务状态是否显示为绿色复选标记。如果显示红色 X，请选择相应的中介服务器。在“操作”菜单上，单击“启动所有服务”。

如果在中介服务器池中添加了多台计算机，请在 中介服务器池中的其他所有计算机上执行此过程中的步骤。如果不需要在其他任何计算机上为 中介服务器安装文件，请执行 [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)中的过程，为此 中介服务器池（或某个站点上的所有中介服务器）与其对等方之间的中继连接配置设置。

## 另请参阅

#### 概念

[Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)


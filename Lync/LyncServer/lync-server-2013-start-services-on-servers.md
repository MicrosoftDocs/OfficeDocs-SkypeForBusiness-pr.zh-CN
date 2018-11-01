---
title: Lync Server 2013：启动服务器上的服务
TOCTitle: 启动服务器上的服务
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413059(v=OCS.15)
ms:contentKeyID: 49314806
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 启动服务器上的服务

 

_**上一次修改主题：** 2014-09-03_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员或委派了正确权限的用户身份登录。有关委派权限的详细信息，请参阅主题[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

在服务器上安装本地配置存储、在 前端服务器或 前端服务器上安装 Lync Server 2013 组件和配置证书后，必须启动服务器上的 Lync Server 2013 服务。使用以下过程来启动部署中每台 前端服务器上的服务。

## 启动 Standard Edition Server 或前端服务器上的服务

1.  在 Lync Server 部署向导中的“Lync Server 2013”页上，单击“步骤 4: 启动服务”旁边的“运行”。

2.  在“启动服务”页上，单击“下一步”以启动服务器上的 Lync Server 服务。

3.  在“正在执行命令”页上，成功启动所有服务后，单击“完成”。
    
    > [!IMPORTANT]
    > 用于启动服务器上的服务的命令是报告实际上已启动服务的最佳方法。该命令可能无法反映服务的实际状态。建议使用紧随“启动服务”之后的步骤“服务状态(可选)”来打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动。如果未启动任何 Lync Server 服务，则可在 MMC 中右键单击该服务，然后单击“启动”。


---
title: Lync Server 2013：对用于 Lync Server 联盟的边缘池进行故障转移
TOCTitle: 对用于 Lync Server 联盟的边缘池进行故障转移
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49888437
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移

 

_**上一次修改主题：** 2012-09-17_

如果配置了 Lync Server 联盟的边缘池不可用，则必须将联盟更改为使用其他边缘池，联盟才能正常运行。

## 故障转移用于 Lync Server 联盟的边缘池

1.  在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。单击“确定”。

3.  展开“边缘池”，然后右键单击现在要用于联盟的边缘服务器或边缘服务器池。选择“编辑属性”。

4.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。单击“确定”。

5.  单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。

6.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

7.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。
    
    如果包含故障边缘池的站点包含仍在运行的前端服务器，则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务才能在仍在运行的远程站点中使用边缘池。有关详细信息，请参阅 [在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

## 另请参阅

#### 任务

[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  

#### 概念

[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)


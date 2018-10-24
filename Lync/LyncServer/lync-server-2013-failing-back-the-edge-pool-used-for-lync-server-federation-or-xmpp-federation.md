---
title: Lync Server 2013：对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复
TOCTitle: 对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49888629
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复

 

_**上一次修改主题：** 2012-11-01_

在出故障的用于承载联盟的边缘池重新联机后，使用此过程对 Lync Server 联盟路由和/或 XMPP 联盟路由进行故障回复以再次使用这一恢复的边缘池。

## 将联盟故障回复到恢复的边缘池

1.  在此时再次可用的边缘池上，启动边缘服务。

2.  如果想要对 Lync Server 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：
    
      - 在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。选择“编辑属性”。
    
      - 在“编辑属性”中的“常规”下，清除“为此边缘池启用联盟（端口 5061）”。单击“确定”。
    
      - 展开“边缘池”，然后右键单击您想再次用于联盟的原始边缘服务器或边缘服务器池。选择“编辑属性”。
    
      - 在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。单击“确定”。
    
      - 单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。
    
      - 在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。
    
      - 在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

3.  如果想要对 XMPP 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：
    
      - 运行以下 cmdlet 以将 XMPP 联盟路由重新指向此时将承载 XMPP 联盟的服务器（在此示例中为 EdgeServer1）：
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在此示例中，Site1 是包含此时将承载 XMPP 联盟路由的边缘池的站点，EdgeServer1.contoso.com 是该池中边缘服务器的 FQDN。
    
      - 如果您尚未拥有解析到此时将承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加该记录，如下例所示。该 SRV 记录的端口值必须为 5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。
    
      - 确认此时将承载 XMPP 联盟的边缘池已将端口 5269 向外部开放。

4.  如果前端池在含有出过故障并且已恢复的边缘池的站点中持续运行，则应该更新这些前端池上的 Web 会议服务和 A/V 会议服务，以在其本地站点上再次使用边缘池。有关详细信息，请参阅 [在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

5.  如果在出现了故障边缘池的同一站点上的前端池也出现故障，则现在可以使用 Invoke–CsPoolFailback 对前端池进行故障回复。

## 另请参阅

#### 任务

[在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  

#### 概念

[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)


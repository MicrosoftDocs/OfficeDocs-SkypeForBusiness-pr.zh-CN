---
title: 呼叫允许控制部署检查表
TOCTitle: 呼叫允许控制部署检查表
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398928(v=OCS.15)
ms:contentKeyID: 49314374
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 呼叫允许控制部署检查表

 

_**上一次修改主题：** 2012-10-22_

使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。

  - 如果已部署一台或多台边缘服务器，则必须将每个外部接口 IP 地址添加到网络配置设置中的子网列表，其中位掩码为 32。还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]  
    > 边缘服务器无需实现 CAC。
    


  - 确保已启用 CAC，方法是通过 Lync Server 控制面板或运行[启用呼叫允许控制](lync-server-2013-enable-call-admission-control.md)中所指定的 cmdlet。

  - 确保已在所有中央站点启用 CAC。可通过拓扑生成器来执行此操作。如果发布时生成警告，*请勿* 忽略该警告。

  - 确保已在网络配置设置中配置在企业网络中管理的所有子网。应该将每个子网与网络站点关联，如[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)中所述，这一点也非常重要。

  - 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。


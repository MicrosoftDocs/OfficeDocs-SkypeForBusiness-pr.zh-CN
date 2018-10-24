---
title: Lync Server 2013：SIP 中继上的呼叫允许控制
TOCTitle: SIP 中继上的呼叫允许控制
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398632(v=OCS.15)
ms:contentKeyID: 49313388
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 SIP 中继上的呼叫允许控制

 

_**上一次修改主题：** 2012-09-22_

要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。

下图显示 SIP 中继上的 CAC 部署示例。

**SIP 中继上的 CAC 配置**

![呼叫允许控制 SIP 中继图](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "呼叫允许控制 SIP 中继图")

要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：

1.  创建一个网络站点，代表 ITSP。将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中为 CAC 配置网络站点](lync-server-2013-configure-network-sites-for-cac.md)。
    
    > [!NOTE]  
    > 对于 ITSP，该网络站点配置不起作用。带宽策略值实际是在步骤 2 中应用。
    


2.  使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)。有关 New-CsNetworkInterSitePolicy cmdlet，另请参阅 Lync Server 命令行管理程序文档。

3.  从 ITSP 获取会话边界控制器 (SCB) 的媒体端点的 IP 地址。将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。有关详细信息，请参阅 [在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。


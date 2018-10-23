---
title: 全局媒体绕过选项
TOCTitle: 全局媒体绕过选项
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398255(v=OCS.15)
ms:contentKeyID: 49312170
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 全局媒体绕过选项

 

_**上一次修改主题：** 2016-12-08_

> [!NOTE]  
> 本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为连接到对等方（Internet 电话服务提供商的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器 (SBC)）的所有中继配置了媒体旁路。



除了为与对等方关联的各个中继连接启用媒体旁路功能外，还必须在全局范围内启用媒体旁路功能。全局媒体旁路设置可以指定始终为对 PSTN 的呼叫尝试媒体旁路，或者指定通过将子网映射到网络站点和网络区域来使用媒体旁路，这与呼叫允许控制（另一高级语音功能）所执行的操作类似。同时启用媒体旁路和呼叫允许控制后，在确定是否使用媒体旁路时，会自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。这意味着，启用呼叫允许控制后无法指定始终为对 PSTN 的呼叫尝试媒体旁路。

本主题介绍如何配合使用 Lync Server 控制面板和 Lync Server 命令行管理程序来配置全局媒体旁路设置。

> [!NOTE]  
> 使用这些步骤配置媒体旁路时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。如果链接上有任何带宽限制，则媒体旁路无法应用于呼叫。媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。媒体旁路仅支持 <a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x804</a> 上的“统一通信开放式互操作性程序 – Lync Server”中列出的产品和版本。



## 后续步骤：选择全局媒体旁路设置

在任何到特定站点或特定服务的对等方的中继连接上启用媒体旁路后，请使用以下内容：

  - 始终启用媒体旁路，如[配置媒体绕过以始终绕过中介服务器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)中所述。

  - 或者，配置媒体旁路以使用站点和区域信息，如[配置媒体绕过全局设置以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)  

#### 概念

[在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)


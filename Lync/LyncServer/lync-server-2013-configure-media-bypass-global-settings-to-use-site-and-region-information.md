---
title: 配置媒体绕过全局设置以使用站点和区域信息
TOCTitle: 配置媒体绕过全局设置以使用站点和区域信息
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398150(v=OCS.15)
ms:contentKeyID: 49311945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置媒体绕过全局设置以使用站点和区域信息

 

_**上一次修改主题：** 2012-09-21_

> [!NOTE]  
> 本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为从中介服务器到对等方（Internet 电话服务提供商的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器）的所有中继连接配置媒体旁路。<br />
本主题还假定，您已采用与您根据<a href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</a>、<a href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</a>和<a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点相关联</a>中的步骤进行的网络区域、网络站点和子站点配置相匹配的方式，定义了拓扑生成器中的所有中央站点和分支站点。如果它们不匹配，则媒体旁路将会失败。



除了为与对等方关联的各个中继连接启用媒体旁路外，还必须配置全局设置。如果使用本主题中的步骤为媒体旁路配置全局设置，则假定以下一种或两种情况将影响您的配置：

  - Lync Server 终结点和任何已在中继连接上为其配置媒体旁路的对等方之间*没有* 很好的连接。

  - 已启用用于带宽管理的呼叫允许控制 (CAC)。
    
    > [!NOTE]  
    > 有关呼叫允许控制和媒体旁路的注意事项的详细信息，请参阅规划文档中<a href="lync-server-2013-media-bypass-and-mediation-server.md">Lync Server 2013 中的媒体绕过和中介服务器</a>的“PSTN 连接的呼叫允许控制”部分。
    


启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。

或者，如果要使用站点和区域信息来作出旁路决定，但不想启用呼叫允许控制，则请按照这些步骤进行操作。在这种情况下，带宽受限的链接仍需要通过网络站点间策略进行显示，如[在 Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)中所述。实际带宽限制并不像本示例中那么重要，因为尚未启用呼叫允许控制。相反，这些链接可用于对子网进行分区，以指定没有带宽限制的链接，从而使用媒体旁路。请注意，这也适用于呼叫允许控制和媒体旁路都启用的情况。

此外，如果要让旁路正常工作，在拓扑生成器中定义的站点必须与配置网络区域和网络站点时定义的站点一致。例如，如果您有一个在拓扑生成器中定义的仅部署了一个 PSTN 网关的分支站点，则必须使用企业语音策略配置该分支站点，借助该语音策略，分支站点用户可通过分支站点上的 PSTN 网关路由其 PSTN 呼叫。

## 为媒体旁路配置站点和区域信息

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  双击表中的“全局”配置。

4.  在“编辑全局设置”页上，选中“启用媒体旁路”复选框。

5.  单击“使用站点和区域配置”。

6.  如有必要，请选中“为非映射站点启用旁路”复选框。
    
    > [!NOTE]  
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。
    


7.  单击“提交”。

接着，将子网添加到网络站点中，如[将子网与网络站点相关联以启用媒体绕过](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)中所述（将子网与网络站点相关联的实际过程会在[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)中进行介绍）。将所有子网与网络站点相关联后，媒体旁路即部署完成。

> [!IMPORTANT]  
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。有关详细信息，请参阅<a href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</a>和<a href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</a>。


## 另请参阅

#### 概念

[将子网与网络站点相关联以启用媒体绕过](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)


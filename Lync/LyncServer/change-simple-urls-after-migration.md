---
title: 迁移后更改单个 URL
TOCTitle: 迁移后更改单个 URL
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49888557
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移后更改单个 URL

 

_**上一次修改主题：** 2012-09-22_

Lync Server 支持三种简单 URL：

  - **会议** 用作站点或组织中所有会议的基 URL。通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。

  - **拨入** 允许访问“电话拨入式会议设置”网页。拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。

  - **管理** 允许快速访问 Lync Server 控制面板。管理简单 URL 是组织内部的。

在迁移到 Lync Server 2013 之后，您必须注意更改对简单 URL 的 DNS 记录和证书有何影响。如果旧的 Lync Server 2010 控制器继续在拓扑中使用，则不需要对您的简单 URL 进行任何更改。如果在迁移后将 Lync Server 2010 Director 从拓扑中删除，则必须更新简单 URL DNS 记录，以指向其中一个 Lync Server 2013 池。但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，才能注册该更改。

## 迁移后更改简单 URL

**更新会议简单 URL**

1.  在 拓扑生成器中，右键单击顶层节点 **Lync Server**，然后单击“编辑属性”。

2.  在左侧窗格中选择“简单 URL”，然后在“会议 URL:”下选择“会议 URL”，然后单击“编辑 URL”。

3.  将 URL 更新为所需的值，然后单击“确定”保存已编辑的 URL。

**更新管理简单 URL**

1.  在 拓扑生成器中，右键单击顶层节点 **Lync Server**，然后单击“编辑属性”。

2.  在左侧窗格中选择“简单 URL”，然后在“管理访问 URL”框下，输入要用于对 Lync Server 2013 控制面板进行管理访问的简单 URL，然后单击“确定”。
    
    > [!TIP]
    > 建议尽可能使用最简单的 URL 作为管理 URL。最简单的选项是 <strong>https://admin.</strong><em>&lt;domain&gt;</em>。


## 另请参阅

#### 概念

[在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)


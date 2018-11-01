---
title: Lync Server 2013：定义和配置拓扑
TOCTitle: 定义和配置拓扑
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398339(v=OCS.15)
ms:contentKeyID: 49312841
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义和配置拓扑

 

_**上一次修改主题：** 2012-09-14_

可使用 拓扑生成器定义和配置拓扑。 拓扑生成器不要求您是本地 Administrators 组或特许域组（如 Domain Admins）的成员。您能够以标准用户身份定义拓扑。如果首次使用和以后编辑会话时启动 拓扑生成器，将会提示您选择希望 拓扑生成器加载当前配置文档的位置。选项如下所示：

  - 从现有部署下载拓扑

  - 从本地文件打开拓扑

  - 新建拓扑

如果已定义一个拓扑并建立 中央管理存储，则应选择从现有部署下载拓扑。 拓扑生成器将读取数据库并检索当前定义。如果您有现有 中央管理存储，则应始终选择此选项。

如果尚未建立 中央管理存储，并且希望编辑以前保存的配置，则应选择从本地文件打开拓扑。将要打开的文件就是以前会话中保存的配置文件。可以使用此选项编辑以前保存的拓扑。

> [!WARNING]
> 如果您已有发布的拓扑，则不应加载本地配置文件，而应选择从现有部署下载拓扑。


如果要创建新的 拓扑生成器配置，请选择创建新的拓扑。以前保存的设计不会被覆盖，除非选择将其另存为以前设计会话中创建的同一文件。

在每个选项中，都会提示您选择存储 拓扑生成器配置文件的位置。文件的位置可以是本地位置、已建立文件共享上的共享位置或可移动介质。

## 本部分内容

  - [在 Lync Server 2013 拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [在 Lync Server 2013 中针对灾难恢复部署配对的前端池](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [在 Lync Server 2013 中编辑或配置简单 URL](lync-server-2013-edit-or-configure-simple-urls.md)

  - [在 Lync Server 2013 中选择中央管理服务器](lync-server-2013-select-the-central-management-server.md)


---
title: 迁移过程
TOCTitle: 迁移过程
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204696(v=OCS.15)
ms:contentKeyID: 49312083
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移过程

 

_**上一次修改主题：** 2012-09-17_

建议和支持的 Lync Server 2013 迁移过程是并行迁移过程。本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。

## 并行迁移

在几乎每个迁移中，都应该使用并行迁移路径。在并行迁移中，将具有 Lync Server 2013 的新服务器与运行 Lync Server 2010 的相应服务器一起部署，然后将操作转移到新服务器。如果需要回滚到 Lync Server 2010，只需将操作切换回原来的服务器即可。请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。

## 共存测试

在将 Lync Server 2013 与 Lync Server 2010 并行部署后，部署表示 Lync Server 2013 和 Lync Server 2010 的共存测试状态。在此状态下，必须测试和确保服务已启动，可以管理每个站点，并且客户端可以与当前用户和旧用户通信。在迁移所有用户之前，必须了解每个部署的状态并确保每个部署正常运行。通常，此共存测试阶段贯穿 Lync Server 2013 试点测试始终。将旧用户移动到 Lync Server 2013 中一段时间，以确保应用程序兼容性和功能正常发挥作用。在试点测试后，将用户和应用程序移到生产版本的 Lync Server 2013 中，并停用 Lync Server 2010 的旧池和应用程序。


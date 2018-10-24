---
title: Lync Server 2013：为用户启用 E9-1-1
TOCTitle: 为用户启用 E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425892(v=OCS.15)
ms:contentKeyID: 49312571
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为用户启用 E9-1-1

 

_**上一次修改主题：** 2012-06-06_

在客户端注册过程中， Lync Server 使用位置策略为启用企业语音的用户配置 E9-1-1 属性。此策略包含定义 E9-1-1 实现方式的设置。例如，位置策略包含诸如紧急拨号串和是否需要用户手动输入位置（如果 位置信息服务未自动提供位置）等信息。有关位置策略的完整定义，请参阅 [为 Lync Server 2013 定义位置策略](lync-server-2013-defining-the-location-policy.md)。

Lync Server 可以通过子网向客户端或通过全局、每站点或每用户策略直接向用户分配位置策略。为帮助确定启用用户的方式，应首先回答以下问题。

  - **您计划启用所有用户还是限制为对企业的特定地理区域的支持？**  
    可以使用全局位置策略为企业中的所有用户分配位置。但是，通过向 Lync Server 网络站点分配位置策略，然后向该站点添加子网，您可以限制只有企业中选定的位置支持 E9-1-1，并基于站点指定 E9-1-1 路由行为。

<!-- end list -->

  - **您是否计划通过用户策略启用单个用户？**  
    如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。

<!-- end list -->

  - **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**  
    如果向用户分配了全局、站点或每用户位置策略，并且客户端不在定义的子网中，或者 位置信息服务没有找到位置，则用户可能需要向该客户端手动输入位置。有关详细信息，请参阅 [在 Lync Server 2013 中定义手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。


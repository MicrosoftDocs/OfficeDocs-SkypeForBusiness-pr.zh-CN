---
title: Lync Server 2013：启用 Kerberos 身份验证的先决条件
TOCTitle: 启用 Kerberos 身份验证的先决条件
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425909(v=OCS.15)
ms:contentKeyID: 49312620
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件

 

_**上一次修改主题：** 2013-02-21_

启用 Kerberos 身份验证前，请确保完成所有必备配置和基础结构准备：

  - 已为 Lync Server 2013 扩展 Active Directory 架构。

  - 已为 Lync Server 2013 完成 Active Directory 林准备。

  - 已为 Lync Server 2013 完成 Active Directory 域准备。

  - 中央管理存储已成功安装并可用。

  - 已使用 拓扑生成器创建并发布了拓扑。

  - 已定义和部署需要 Web 服务的服务器和角色，包括前端服务器、Standard Edition Server 和控制器。

  - Internet Information Services (IIS) 已配置并部署了推荐的角色服务，从而可在 Lync Server 2013 中支持 Web 服务。

满足先决条件之后，就已准备好为部署创建一个或多个帐户以供 Web 服务用于 Kerberos 身份验证。至少需要为每个部署创建一个 Kerberos 身份验证帐户。但是，可以为每个站点创建一个帐户，以在该站点提供本地 Kerberos 身份验证。只能为每个站点指定一个 Kerberos 身份验证帐户。


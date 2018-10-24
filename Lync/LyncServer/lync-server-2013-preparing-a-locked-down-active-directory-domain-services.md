---
title: Lync Server 2013：准备锁定的 Active Directory 域服务
TOCTitle: 准备锁定的 Active Directory 域服务
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398492(v=OCS.15)
ms:contentKeyID: 49313135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中准备锁定的 Active Directory 域服务

 

_**上一次修改主题：** 2012-05-14_

组织通常锁定 Active Directory 域服务 以帮助降低安全风险。但是，锁定 Active Directory 环境会限制 Lync Server 2013 所需的权限。为 Lync Server 2013 正确准备锁定的 Active Directory 环境涉及一些额外的注意事项和步骤。

在锁定的 Active Directory 环境中，权限以如下两种常见方式受到限制：

  - 从容器中删除经过身份验证的用户的访问控制项 (ACE)。

  - 权限继承在用户、联系人、InetOrgPerson 或计算机对象的容器上被禁用。

## 本节内容

  - [在 Lync Server 2013 中删除经过身份验证的用户的权限](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Lync Server 2013 中权限继承在计算机、用户或 InetOrgPerson 容器上被禁用](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)


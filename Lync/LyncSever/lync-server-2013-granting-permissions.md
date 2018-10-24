---
title: Lync Server 2013：授予权限
TOCTitle: 授予权限
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398901(v=OCS.15)
ms:contentKeyID: 49314323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中授予权限

 

_**上一次修改主题：** 2012-10-15_

对于安装，可向特定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 通用组授予权限，使该 OU 中的 RTCUniversalServerAdmins 组的成员能够在指定域中安装 Lync Server 2013。为 OU 授予权限时，授予的权限包括：

  - 读取

  - 写入

  - ReadSPN

  - WriteSPN

对于管理，可将权限添加到指定 OU 以便林准备过程创建的 RTC 通用组成员可以访问 OU，而不必是 Domain Admins 组成员。添加到指定 OU 的权限与 **Enable-CsAdDomain** cmdlet 添加到计算机和用户 OU 容器的权限相同。

## 本节内容

  - [在 Lync Server 2013 中授予安装权限](lync-server-2013-granting-setup-permissions.md)

  - [在 Lync Server 2013 中授予组织单位权限](lync-server-2013-granting-organizational-unit-permissions.md)


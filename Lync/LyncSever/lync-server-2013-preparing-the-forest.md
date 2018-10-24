---
title: Lync Server 2013：准备林
TOCTitle: 准备林
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425898(v=OCS.15)
ms:contentKeyID: 49312581
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 准备林

 

_**上一次修改主题：** 2013-02-21_

林准备会创建 Active Directory 全局设置和对象以及 Active Directory 通用组以供 Lync Server 2013 使用，并且授予对 Active Directory 对象的相应访问权限。有关林准备创建的通用组以及全局设置和对象的说明，请参阅 [Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。

林准备还创建包含 Lync Server 2013 所用属性集和显示说明符的对象，并将其存储在配置容器中。

> [!IMPORTANT]
> 执行林准备过程之前，确保已将架构准备更改复制到所有域控制器。如果复制尚未完成，则会出错。


如果正在执行新的 Lync Server 部署，必须将全局设置存储在配置容器中。如果正在从早期版本进行升级且仍将全局设置存储在系统容器中，则可继续使用系统容器。

只有林根目录域的 Enterprise Admins 组或 Domain Admins 组的成员才能执行此过程。

## 本部分内容

  - [为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md)

  - [针对 Lync Server 2013 使用 Cmdlet 反向执行林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)


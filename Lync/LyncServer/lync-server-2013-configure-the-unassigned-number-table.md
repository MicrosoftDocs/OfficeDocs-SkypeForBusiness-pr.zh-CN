---
title: Lync Server 2013：配置未分配号码表
TOCTitle: 配置未分配号码表
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399053(v=OCS.15)
ms:contentKeyID: 49314632
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置未分配号码表

 

_**上一次修改主题：** 2012-10-30_

在 Lync Server 2013 中，可以指定对特定电话号码的传入呼叫的行为，这些号码对组织有效但尚未分配给用户或电话。呼叫者可以收听消息或将消息路由到其他目标，或同时实现这两者。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。

> [!IMPORTANT]  
> 在配置未分配号码表之前，系统必须已定义通知，或已设置 Exchange 统一消息 (UM) 自动助理。


> [!TIP]
> 当有人呼叫未分配号码时， Lync Server 从上到下搜索未分配号码表，然后使用第一个匹配范围。因此，要在万不得已时执行的操作应指定给表中最后一个范围。


## 本部分内容

[在 Lync Server 2013 中创建或修改未分配号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [在 Lync Server 2013 中创建通知](lync-server-2013-create-an-announcement.md)


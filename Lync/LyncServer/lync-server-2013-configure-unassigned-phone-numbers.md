---
title: 配置未分配电话号码
TOCTitle: 配置未分配电话号码
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182559(v=OCS.15)
ms:contentKeyID: 49313784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置未分配电话号码

 

_**上一次修改主题：** 2012-11-01_

利用 Lync Server，您可以配置对特定电话号码的传入呼叫的行为，这些号码对组织有效但尚未分配给用户或电话。若要配置对此类呼叫的处理，请设置未分配号码表。您可以使用此表将呼叫路由到通知应用程序或 Exchange UM 服务器。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。

> [!IMPORTANT]  
> 在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange UM 自动助理。有关创建通知的详细信息，请参阅<a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</a>。若要查看是否已配置 Exchange UM 设置，请运行 <strong>Get-CsExUmContact</strong> cmdlet。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</a>。


## 本部分内容

  - [在 Lync Server 2013 中创建或修改未分配号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [删除未分配号码范围](lync-server-2013-delete-an-unassigned-number-range.md)


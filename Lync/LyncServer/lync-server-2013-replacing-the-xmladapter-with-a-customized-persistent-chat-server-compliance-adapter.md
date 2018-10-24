---
title: 在 Lync Server 2013 中使用自定义持久聊天服务器合规性适配器替换 XmlAdapter
TOCTitle: 在 Lync Server 2013 中使用自定义持久聊天服务器合规性适配器替换 XmlAdapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49888344
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用自定义持久聊天服务器合规性适配器替换 XmlAdapter

 

_**上一次修改主题：** 2012-11-01_

您可以编写自定义适配器而不使用与持久聊天服务器一起安装的 XmlAdapter。若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。您必须将此程序集置于持久聊天服务器池中每台服务器的持久聊天服务器安装文件夹中。任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。

## 实现 IComplianceAdapter 接口

此接口在 Compliance.dll 程序集中的命名空间 `Microsoft.Rtc.Internal.Chat.Server.Compliance` 中定义，它定义您的自定义适配器必须实现的两种方法。

    void SetConfig(AdapterConfig config)

持久聊天合规性服务器将在适配器首次加载时调用此方法。`AdapterConfig` 包含与合规性适配器相关的持久聊天合规性配置。

    void Translate(ConversationCollection conversations)

只要有要转换的新数据，持久聊天合规性服务器就会定期调用此方法。此时间间隔等于持久聊天合规性配置中设置的 `RunInterval`。

`ConversationCollection` 包含上次调用此方法时收集的对话信息。


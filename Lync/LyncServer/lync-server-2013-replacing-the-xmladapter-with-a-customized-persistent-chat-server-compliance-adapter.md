---
title: 'Lync Server 2013: 将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>在 Lync Server 2013 中将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

你可以编写自定义适配器, 而不是使用随永久聊天服务器一起安装的 XmlAdapter。 若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。 必须将此程序集放在持久聊天服务器池中每台服务器的持久聊天服务器安装文件夹中。 任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>实现 IComplianceAdapter 接口

该接口在命名空间`Microsoft.Rtc.Internal.Chat.Server.Compliance`中的合规 .dll 程序集中定义。 该接口定义您的自定义适配器必须实现的两种方法。

    void SetConfig(AdapterConfig config)

在适配器首次加载时, 持久聊天合规性服务器将调用此方法。 `AdapterConfig`包含与合规性适配器相关的持久聊天合规性配置。

    void Translate(ConversationCollection conversations)

只要存在要翻译的新数据, 永久聊天合规性服务器将按定期时间间隔调用此方法。 此时间间隔等于持久聊天合规`RunInterval`性配置中的设置。

`ConversationCollection`包含上次调用此方法时收集的对话信息。

</div>

</div>

<span> </span>

</div>

</div>

</div>


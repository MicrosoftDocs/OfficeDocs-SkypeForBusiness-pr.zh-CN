---
title: Lync Server 2013：将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器
description: Lync Server 2013：将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576138"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="5c061-103">在 Lync Server 2013 中将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器</span><span class="sxs-lookup"><span data-stu-id="5c061-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c061-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5c061-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5c061-105">您可以编写自定义适配器，而不是使用随持久聊天服务器一起安装的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="5c061-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="5c061-106">若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="5c061-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="5c061-107">您必须将此程序集放置在持久聊天服务器池中每台服务器的持久聊天服务器安装文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5c061-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="5c061-108">任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="5c061-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="5c061-109">实现 IComplianceAdapter 接口</span><span class="sxs-lookup"><span data-stu-id="5c061-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="5c061-110">接口是在命名空间中的 Compliance.dll 程序集中定义的 `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。</span><span class="sxs-lookup"><span data-stu-id="5c061-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="5c061-111">此接口定义您的自定义适配器必须实现的两种方法。</span><span class="sxs-lookup"><span data-stu-id="5c061-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="5c061-112">在适配器第一次加载时，持久聊天合规性服务器将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="5c061-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="5c061-113">`AdapterConfig`包含与合规性适配器相关的持久聊天合规性配置。</span><span class="sxs-lookup"><span data-stu-id="5c061-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="5c061-114">只要有要翻译的新数据，持久聊天合规性服务器将定期调用此方法。</span><span class="sxs-lookup"><span data-stu-id="5c061-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="5c061-115">此时间间隔等于 `RunInterval` 在持久聊天合规性配置中设置的。</span><span class="sxs-lookup"><span data-stu-id="5c061-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="5c061-116">`ConversationCollection`包含上次调用此方法时收集的对话信息。</span><span class="sxs-lookup"><span data-stu-id="5c061-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


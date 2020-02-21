---
title: Lync Server 2013：将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器
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
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="82d68-102">在 Lync Server 2013 中将 XmlAdapter 替换为自定义的持久聊天服务器合规性适配器</span><span class="sxs-lookup"><span data-stu-id="82d68-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82d68-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="82d68-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="82d68-104">您可以编写自定义适配器，而不是使用随持久聊天服务器一起安装的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="82d68-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="82d68-105">若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="82d68-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="82d68-106">您必须将此程序集放置在持久聊天服务器池中每台服务器的持久聊天服务器安装文件夹中。</span><span class="sxs-lookup"><span data-stu-id="82d68-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="82d68-107">任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="82d68-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="82d68-108">实现 IComplianceAdapter 接口</span><span class="sxs-lookup"><span data-stu-id="82d68-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="82d68-109">接口在命名空间`Microsoft.Rtc.Internal.Chat.Server.Compliance`中的合规 .dll 程序集中定义。</span><span class="sxs-lookup"><span data-stu-id="82d68-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="82d68-110">此接口定义您的自定义适配器必须实现的两种方法。</span><span class="sxs-lookup"><span data-stu-id="82d68-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="82d68-111">在适配器第一次加载时，持久聊天合规性服务器将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="82d68-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="82d68-112">`AdapterConfig`包含与合规性适配器相关的持久聊天合规性配置。</span><span class="sxs-lookup"><span data-stu-id="82d68-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="82d68-113">只要有要翻译的新数据，持久聊天合规性服务器将定期调用此方法。</span><span class="sxs-lookup"><span data-stu-id="82d68-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="82d68-114">此时间间隔等于在持久聊天`RunInterval`合规性配置中设置的。</span><span class="sxs-lookup"><span data-stu-id="82d68-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="82d68-115">`ConversationCollection`包含上次调用此方法时收集的对话信息。</span><span class="sxs-lookup"><span data-stu-id="82d68-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


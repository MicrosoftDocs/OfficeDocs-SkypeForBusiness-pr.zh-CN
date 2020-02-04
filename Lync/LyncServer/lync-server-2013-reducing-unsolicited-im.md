---
title: Lync Server 2013：减少垃圾 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="cb3cb-102">减少 Lync Server 2013 的垃圾 IM</span><span class="sxs-lookup"><span data-stu-id="cb3cb-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb3cb-103">_**主题上次修改时间：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="cb3cb-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="cb3cb-104">智能 IM 筛选器应用程序可帮助保护 Microsoft Lync Server 2013 部署，使其不会受到最常见病毒的攻击，最大程度地降低用户体验。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="cb3cb-105">智能 IM 筛选器提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="cb3cb-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="cb3cb-106">增强的 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="cb3cb-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="cb3cb-107">增强的文件传输筛选</span><span class="sxs-lookup"><span data-stu-id="cb3cb-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="cb3cb-108">使用智能 IM 筛选器配置筛选器，阻止来自公司防火墙外的未知终结点的未经请求或可能有害的即时消息。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="cb3cb-109">通过指定用于确定应阻止的条件的条件（如包含超链接的即时消息和具有特定扩展名的文件）来配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="cb3cb-110">在部署智能 IM 消息筛选器应用程序之前，应了解当邮件从一个 Lync Server 2013 服务器路由到另一个时如何应用筛选选项。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="cb3cb-111">应用这些筛选选项的方式是一致的，无论服务器位于单个组织还是跨组织边界。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="cb3cb-112">此一致性适用于将自定义通知和警告文本插入到邮件中并在服务器上发送的方式。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="cb3cb-113">建议的筛选选项是允许带有超链接的即时消息，但需要智能 IM 筛选器通过在其前面插入下划线来禁用链接。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="cb3cb-114">如果选择此选项，则可以选择向用户提供通知，该选项显示在包含超链接的每个即时消息的开头。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="cb3cb-115">第二个筛选选项允许带有未修改的超链接的即时消息。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="cb3cb-116">如果选择此选项，则会有附加选项（推荐），对插入到每封邮件中的用户撰写警告。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="cb3cb-117">第三个选项是阻止所有包含超链接的即时消息。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="cb3cb-118">如果选择此选项，服务器会向用户发送警告。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="cb3cb-119">必须编写此警告。</span><span class="sxs-lookup"><span data-stu-id="cb3cb-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


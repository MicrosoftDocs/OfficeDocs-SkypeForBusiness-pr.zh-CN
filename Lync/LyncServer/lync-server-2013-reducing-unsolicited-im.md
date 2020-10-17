---
title: Lync Server 2013：减少未经请求的 IM
description: Lync Server 2013：减少未经请求的 IM。
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
ms.openlocfilehash: 294c53a6b82b4dc345fbb9afcf9983d5bd35893a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559108"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="bdd22-103">为 Lync Server 2013 减少未经请求的 IM</span><span class="sxs-lookup"><span data-stu-id="bdd22-103">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd22-104">_**上次修改的主题：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="bdd22-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="bdd22-105">智能 IM 筛选器应用程序可帮助保护 Microsoft Lync Server 2013 部署不受最常见病毒的攻击，最大程度地降低用户体验。</span><span class="sxs-lookup"><span data-stu-id="bdd22-105">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="bdd22-106">智能 IM 筛选器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="bdd22-106">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="bdd22-107">增强的 URL 筛选功能</span><span class="sxs-lookup"><span data-stu-id="bdd22-107">Enhanced URL filtering</span></span>

  - <span data-ttu-id="bdd22-108">增强的文件传输筛选功能</span><span class="sxs-lookup"><span data-stu-id="bdd22-108">Enhanced file transfer filtering</span></span>

<span data-ttu-id="bdd22-p102">使用智能 IM 筛选器可以对筛选器进行配置，以阻止来自企业防火墙外部的未知终结点的未经请求或可能有害的即时消息。可通过指定用于确定应阻止的内容（例如，包含超链接的即时消息和具有特定扩展名的文件）的条件来配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="bdd22-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="bdd22-111">在部署智能 IM 邮件筛选器应用程序之前，应了解在将邮件从一台 Lync Server 2013 服务器路由到另一台时如何应用筛选选项。</span><span class="sxs-lookup"><span data-stu-id="bdd22-111">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="bdd22-112">应用这些筛选选项的方式是一致的，无论服务器是位于单个组织中还是跨越多个组织。</span><span class="sxs-lookup"><span data-stu-id="bdd22-112">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="bdd22-113">在消息中插入自定义通知和警告文本以及在服务器之间发送这些消息的方式也是一致的。</span><span class="sxs-lookup"><span data-stu-id="bdd22-113">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="bdd22-p104">建议的筛选选项是允许带有超链接的即时消息，但要求智能 IM 筛选器在链接前插入下划线字符来禁用链接。如果选择此选项，则还可以选择撰写一则用户通知，显示在包含超链接的每条即时消息的开头。</span><span class="sxs-lookup"><span data-stu-id="bdd22-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="bdd22-p105">第二个筛选选项是允许带有未经修改的超链接的即时消息。如果选择此选项，则还可以选择撰写将插入到每条消息中的用户警告（推荐）。</span><span class="sxs-lookup"><span data-stu-id="bdd22-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="bdd22-p106">第三个选项是阻止包含超链接的所有即时消息。如果选择此选项，则服务器将向用户发送警告。您必须编写此警告。</span><span class="sxs-lookup"><span data-stu-id="bdd22-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


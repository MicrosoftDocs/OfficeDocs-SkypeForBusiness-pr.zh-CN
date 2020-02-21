---
title: Lync Server 2013：规划远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8586df49eb1dd7a10e94d3231cc2fdc082353
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="80326-102">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="80326-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80326-103">_**上次修改的主题：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="80326-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="80326-104">在 Lync Server 2013 中，支持远程呼叫控制方案使用户能够通过在其台式计算机上使用 Lync 2013 控制其专用的分支 exchange （PBX）电话。</span><span class="sxs-lookup"><span data-stu-id="80326-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="80326-105">本节介绍远程呼叫控制功能以及部署远程呼叫控制的要求。</span><span class="sxs-lookup"><span data-stu-id="80326-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="80326-106">PBX 和 Lync Server 2013 之间的集成使远程呼叫控制启用的用户可以使用 Lync 2013 用户界面（UI）按以下方式控制其 PBX 电话上的呼叫：</span><span class="sxs-lookup"><span data-stu-id="80326-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80326-107">最终，承载用户 PBX 电话的 PBX 的功能将决定可供该用户使用的远程呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="80326-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="80326-108">发出传出呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-108">Make an outgoing call</span></span>

  - <span data-ttu-id="80326-109">应答传入呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-109">Answer an incoming call</span></span>

  - <span data-ttu-id="80326-110">使用即时消息应答传入呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80326-111">也就是说，当呼叫者的电话号码可以与组织的全局地址列表（GAL）中的即时消息地址关联，在被叫方的 Lync 联系人列表中，或在联盟伙伴的组织中。</span><span class="sxs-lookup"><span data-stu-id="80326-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="80326-112">转接呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-112">Transfer a call</span></span>

  - <span data-ttu-id="80326-113">转接传入呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-113">Forward an incoming call</span></span>

  - <span data-ttu-id="80326-114">将呼叫置于保持状态</span><span class="sxs-lookup"><span data-stu-id="80326-114">Place calls on hold</span></span>

  - <span data-ttu-id="80326-115">交替处理多个并发呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="80326-116">在呼叫过程中应答第二个呼叫（即，呼叫等待）</span><span class="sxs-lookup"><span data-stu-id="80326-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="80326-117">双音多频 (DTMF) 数字拨号</span><span class="sxs-lookup"><span data-stu-id="80326-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="80326-118">在“对话”窗口中，键入 Microsoft Office OneNote 的做笔记程序的注释</span><span class="sxs-lookup"><span data-stu-id="80326-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="80326-119">此外，当用户启用远程呼叫控制时，Lync 2013 向用户提供以下呼叫信息：</span><span class="sxs-lookup"><span data-stu-id="80326-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="80326-120">当呼叫者的电话号码存在于远程呼叫控制启用的用户的 Microsoft Office Outlook 消息和协作客户端、Lync 联系人列表或组织的 GAL 中时，按名称标识呼叫者。</span><span class="sxs-lookup"><span data-stu-id="80326-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="80326-121">以前的传入和传出呼叫，保存在 Outlook 的“对话历史记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="80326-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="80326-122">未接来电通知将被发送到用户的 Outlook 收件箱文件夹，但仅当接收到传入呼叫时，才会生成 Lync。</span><span class="sxs-lookup"><span data-stu-id="80326-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="80326-123">远程呼叫控制和企业语音</span><span class="sxs-lookup"><span data-stu-id="80326-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="80326-124">虽然远程呼叫控制功能是独立于企业语音功能的，并且用户不能同时启用，但企业语音也提供了可供启用远程呼叫控制的用户使用的功能子集。</span><span class="sxs-lookup"><span data-stu-id="80326-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="80326-125">如果部署了企业语音，则启用远程呼叫控制的用户可以使用 Lync 访问以下企业语音功能：</span><span class="sxs-lookup"><span data-stu-id="80326-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="80326-126">发出和接收对其他 Lync 客户端的音频呼叫</span><span class="sxs-lookup"><span data-stu-id="80326-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="80326-127">加入由启用了企业语音的用户创建的会议的音频部分</span><span class="sxs-lookup"><span data-stu-id="80326-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="80326-128">本部分内容</span><span class="sxs-lookup"><span data-stu-id="80326-128">In This Section</span></span>

  - [<span data-ttu-id="80326-129">Lync Server 2013 中的远程呼叫控制的部署任务</span><span class="sxs-lookup"><span data-stu-id="80326-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


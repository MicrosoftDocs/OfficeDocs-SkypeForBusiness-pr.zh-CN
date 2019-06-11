---
title: 'Lync Server 2013: 规划远程呼叫控制'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="cf558-102">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cf558-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf558-103">_**主题上次修改时间:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="cf558-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="cf558-104">在 Lync Server 2013 中, 对远程呼叫控制方案的支持允许用户通过在其桌面计算机上使用 Lync 2013 控制其专用分支机构 (PBX) 手机。</span><span class="sxs-lookup"><span data-stu-id="cf558-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="cf558-105">本部分介绍了部署远程呼叫控制的远程呼叫控制功能和要求。</span><span class="sxs-lookup"><span data-stu-id="cf558-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="cf558-106">通过 PBX 和 Lync Server 2013 之间的集成, 用户可以使用 Lync 2013 用户界面 (UI) 使用 Lync 用户界面 (UI) 通过以下方式控制其 PBX 手机上的呼叫:</span><span class="sxs-lookup"><span data-stu-id="cf558-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf558-107">最终, 承载用户 PBX 电话的 PBX 的功能决定了该用户可以使用的远程呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="cf558-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="cf558-108">进行拨出通话</span><span class="sxs-lookup"><span data-stu-id="cf558-108">Make an outgoing call</span></span>

  - <span data-ttu-id="cf558-109">接听来电</span><span class="sxs-lookup"><span data-stu-id="cf558-109">Answer an incoming call</span></span>

  - <span data-ttu-id="cf558-110">使用即时消息应答传入呼叫</span><span class="sxs-lookup"><span data-stu-id="cf558-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf558-111">也就是说, 当呼叫者的电话号码可以与组织的全球通讯簿 (GAL) 中的即时消息地址关联时, 在被呼叫者的 Lync 联系人列表中, 或在联盟伙伴的组织中。</span><span class="sxs-lookup"><span data-stu-id="cf558-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="cf558-112">转移来电</span><span class="sxs-lookup"><span data-stu-id="cf558-112">Transfer a call</span></span>

  - <span data-ttu-id="cf558-113">转发来电</span><span class="sxs-lookup"><span data-stu-id="cf558-113">Forward an incoming call</span></span>

  - <span data-ttu-id="cf558-114">通话暂候</span><span class="sxs-lookup"><span data-stu-id="cf558-114">Place calls on hold</span></span>

  - <span data-ttu-id="cf558-115">在多个并发通话之间切换</span><span class="sxs-lookup"><span data-stu-id="cf558-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="cf558-116">接听通话中的第二个呼叫 (即呼叫等待)</span><span class="sxs-lookup"><span data-stu-id="cf558-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="cf558-117">拨号双音调 multifrequency (DTMF) 数字</span><span class="sxs-lookup"><span data-stu-id="cf558-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="cf558-118">在对话窗口中, 在 Microsoft Office OneNote 笔记记录程序中键入备注</span><span class="sxs-lookup"><span data-stu-id="cf558-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="cf558-119">此外, 当用户启用 "远程呼叫控制" 时, Lync 2013 向用户提供以下调用信息:</span><span class="sxs-lookup"><span data-stu-id="cf558-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="cf558-120">当呼叫者的电话号码位于启用远程呼叫控制的用户的 Microsoft Office Outlook 消息和协作客户端、Lync 联系人列表或组织的 GAL 的联系人列表中时, 按名称标识呼叫者。</span><span class="sxs-lookup"><span data-stu-id="cf558-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="cf558-121">过去拨入和拨出的电话, 它们保存在 Outlook 的 "对话历史记录" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf558-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="cf558-122">未接来电通知将发送到用户的 Outlook 收件箱文件夹, 但仅当接收来电时, 才会生成 Lync。</span><span class="sxs-lookup"><span data-stu-id="cf558-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="cf558-123">远程通话控制和企业语音</span><span class="sxs-lookup"><span data-stu-id="cf558-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="cf558-124">虽然远程呼叫控制功能与企业语音功能不同, 并且不能同时启用用户, 但企业语音还提供了一种可供启用远程呼叫控制的用户使用的功能子集。</span><span class="sxs-lookup"><span data-stu-id="cf558-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="cf558-125">如果部署了企业语音, 则启用远程呼叫控制的用户可以使用 Lync 访问下列企业语音功能:</span><span class="sxs-lookup"><span data-stu-id="cf558-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="cf558-126">拨打和接听其他 Lync 客户端的音频电话</span><span class="sxs-lookup"><span data-stu-id="cf558-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="cf558-127">加入由已启用企业语音的用户创建的会议的音频部分</span><span class="sxs-lookup"><span data-stu-id="cf558-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf558-128">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf558-128">In This Section</span></span>

  - [<span data-ttu-id="cf558-129">Lync Server 2013 中远程呼叫控制的部署任务</span><span class="sxs-lookup"><span data-stu-id="cf558-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


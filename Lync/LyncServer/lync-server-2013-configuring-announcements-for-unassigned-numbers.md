---
title: Lync Server 2013：配置未分配号码的通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8375e3481703078013d85060d20d0e9f500374b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="96686-102">在 Lync Server 2013 中配置未分配号码的通知</span><span class="sxs-lookup"><span data-stu-id="96686-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96686-103">_**主题上次修改时间:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="96686-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="96686-104">"发布" 应用程序是一种企业语音功能, 可让你配置调用未分配的扩展 (对你的组织有效, 但未分配给某个人或手机的扩展) 所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="96686-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="96686-105">例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="96686-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="96686-106">在部署企业语音时, "发布" 应用程序作为 "响应组应用程序" 的一项功能安装在前端服务器或标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="96686-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="96686-107">需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。</span><span class="sxs-lookup"><span data-stu-id="96686-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="96686-108">本部分将指导你完成 Lync Server 公告的配置。</span><span class="sxs-lookup"><span data-stu-id="96686-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="96686-109">它假设你已阅读与公告相关的规划部分, 并使用企业语音部署企业版服务器或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="96686-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96686-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="96686-110">In This Section</span></span>

  - [<span data-ttu-id="96686-111">Lync Server 2013 中的通知配置先决条件和角色</span><span class="sxs-lookup"><span data-stu-id="96686-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="96686-112">Lync Server 2013 中的公告应用程序的部署过程</span><span class="sxs-lookup"><span data-stu-id="96686-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="96686-113">在 Lync Server 2013 中创建公告</span><span class="sxs-lookup"><span data-stu-id="96686-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="96686-114">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="96686-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="96686-115">可选在 Lync Server 2013 中验证公告部署</span><span class="sxs-lookup"><span data-stu-id="96686-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96686-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96686-116">See Also</span></span>


[<span data-ttu-id="96686-117">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="96686-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


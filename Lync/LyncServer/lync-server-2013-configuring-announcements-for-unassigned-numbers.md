---
title: Lync Server 2013：配置未分配号码的通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89f8fe84e046f49304d987fa51adf6dda61b8ce3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="ea2ef-102">在 Lync Server 2013 中配置未分配号码的公告</span><span class="sxs-lookup"><span data-stu-id="ea2ef-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea2ef-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ea2ef-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ea2ef-104">"通知应用程序" 是一种企业语音功能，可让您配置呼叫未分配的分机（对组织有效但未分配给个人或电话的分机）所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="ea2ef-105">例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="ea2ef-106">当您部署企业语音时，通知应用程序作为响应组应用程序在前端服务器或 Standard Edition Server 上的一项功能安装。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ea2ef-107">需要通过上载音频文件或配置文本到语音转换 (TTS) 和配置未分配号码表来配置通知。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="ea2ef-108">本部分将指导您完成 Lync Server 通知的配置。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="ea2ef-109">它假定您已阅读与公告相关的规划部分，并已使用企业版服务器或具有企业语音的 Standard Edition 服务器进行了部署。</span><span class="sxs-lookup"><span data-stu-id="ea2ef-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ea2ef-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ea2ef-110">In This Section</span></span>

  - [<span data-ttu-id="ea2ef-111">在 Lync Server 2013 中通知配置先决条件和角色</span><span class="sxs-lookup"><span data-stu-id="ea2ef-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="ea2ef-112">Lync Server 2013 中的通知应用程序的部署过程</span><span class="sxs-lookup"><span data-stu-id="ea2ef-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="ea2ef-113">在 Lync Server 2013 中创建通知</span><span class="sxs-lookup"><span data-stu-id="ea2ef-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="ea2ef-114">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="ea2ef-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="ea2ef-115">Optional在 Lync Server 2013 中验证通知部署</span><span class="sxs-lookup"><span data-stu-id="ea2ef-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea2ef-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea2ef-116">See Also</span></span>


[<span data-ttu-id="ea2ef-117">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="ea2ef-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


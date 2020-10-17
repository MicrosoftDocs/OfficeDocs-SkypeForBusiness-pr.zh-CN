---
title: Lync Server 2013：使用 Lync 会议室系统管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677fdd070994c8cc1f63f775ffb2569642768f0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529939"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="174b1-102">在 Lync Server 2013 中使用 Lync 会议室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="174b1-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="174b1-103">_**上次修改的主题：** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="174b1-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="174b1-104">在服务器上部署 LRS 之后，您可以通过从浏览器登录到 LRS 管理 Web 门户来检查所有 LRS 聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="174b1-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="174b1-105">登录</span><span class="sxs-lookup"><span data-stu-id="174b1-105">Sign in</span></span>

1.  <span data-ttu-id="174b1-106">浏览到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="174b1-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="174b1-107">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="174b1-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="174b1-108">输入 LRSSupport 帐户的凭据或已添加到 LRSSupportAdminGroup 安全组的帐户。</span><span class="sxs-lookup"><span data-stu-id="174b1-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="174b1-109">![Lync 会议室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 会议室系统管理门户登录屏幕")</span><span class="sxs-lookup"><span data-stu-id="174b1-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="174b1-110">LRS 管理 Web 门户摘要页</span><span class="sxs-lookup"><span data-stu-id="174b1-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="174b1-111">"摘要" 页面为服务器上部署的所有 LRS 聊天室提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="174b1-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="174b1-112">**标记**    管理员为会议室提供的自定义名称。</span><span class="sxs-lookup"><span data-stu-id="174b1-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="174b1-113">可以通过单击聊天室名称在门户中设置标记。</span><span class="sxs-lookup"><span data-stu-id="174b1-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="174b1-114">**运行状况**    会议室的运行状况状态，该状态源自会议室的聚合运行状况状态，显示在 "会议室设置" 页面的 "运行状况" 部分下。</span><span class="sxs-lookup"><span data-stu-id="174b1-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="174b1-115">**下次会议**    安排下一个会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="174b1-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="174b1-116">**LRS 版本、制造商、型号**    这些值是预设在 LRS 中。</span><span class="sxs-lookup"><span data-stu-id="174b1-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="174b1-117">根据制造商的不同，这些字段可能保留为空。</span><span class="sxs-lookup"><span data-stu-id="174b1-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="174b1-118">**上次刷新**    显示上次刷新网页的时间。</span><span class="sxs-lookup"><span data-stu-id="174b1-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="174b1-119">![Lync 会议室系统管理门户摘要视图](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 会议室系统管理门户摘要视图")</span><span class="sxs-lookup"><span data-stu-id="174b1-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="174b1-120">LRS 会议室信息</span><span class="sxs-lookup"><span data-stu-id="174b1-120">LRS Room Information</span></span>

<span data-ttu-id="174b1-121">通过门户的 "会议室信息" 部分，可以查看和配置单个 LRS 会议室。</span><span class="sxs-lookup"><span data-stu-id="174b1-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="174b1-122">它包含四个部分：设置、详细信息、故障排除和运行状况。</span><span class="sxs-lookup"><span data-stu-id="174b1-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="174b1-123">设置</span><span class="sxs-lookup"><span data-stu-id="174b1-123">Settings</span></span>

<span data-ttu-id="174b1-124">在 "设置" 部分中，您可以设置会议室的密码、会议室标记和默认音量级别。</span><span class="sxs-lookup"><span data-stu-id="174b1-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="174b1-125">如果您配置这些设置，更改仅在您重新启动 LRS 控制台之后进行复制。</span><span class="sxs-lookup"><span data-stu-id="174b1-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="174b1-126">您将仅看到版本15.12 及更高版本的 Lync 会议室系统的系统更新设置。</span><span class="sxs-lookup"><span data-stu-id="174b1-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="174b1-127">![Lync 会议室系统管理门户聊天室设置](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 会议室系统管理门户聊天室设置")</span><span class="sxs-lookup"><span data-stu-id="174b1-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="174b1-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="174b1-128">Details</span></span>

<span data-ttu-id="174b1-129">详细信息部分提供了 LRS 会议室设置的只读摘要，包括：上次刷新的时间;下一个会议;上次更新、维护和校准;默认扬声器、麦克风和铃声设置;版本SIP URI;屏幕数量和每个屏幕的详细信息;状态和活动。</span><span class="sxs-lookup"><span data-stu-id="174b1-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="174b1-130">![Lync 会议室系统管理员门户详细信息视图](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 会议室系统管理员门户详细信息视图")</span><span class="sxs-lookup"><span data-stu-id="174b1-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="174b1-131">疑难解答</span><span class="sxs-lookup"><span data-stu-id="174b1-131">Troubleshooting</span></span>

<span data-ttu-id="174b1-132">故障排除部分可用于远程收集日志并将其保存到指定位置。</span><span class="sxs-lookup"><span data-stu-id="174b1-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="174b1-133">您还可以重新启动 LRS 控制台 (LRS 用户界面) 或重新启动整个系统。</span><span class="sxs-lookup"><span data-stu-id="174b1-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="174b1-134">若要收集日志，请提供指定格式的文件夹路径，并确保该文件夹具有给定的对 LRS 计算机帐户的写入权限。</span><span class="sxs-lookup"><span data-stu-id="174b1-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="174b1-135">如果日志太大，可能需要长达5分钟才能完成日志收集。</span><span class="sxs-lookup"><span data-stu-id="174b1-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="174b1-136">刷新页面将为你提供最新状态。</span><span class="sxs-lookup"><span data-stu-id="174b1-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="174b1-137">![Lync 会议室系统管理门户聊天室日志记录](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 会议室系统管理门户聊天室日志记录")</span><span class="sxs-lookup"><span data-stu-id="174b1-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="174b1-138">健康</span><span class="sxs-lookup"><span data-stu-id="174b1-138">Health</span></span>

<span data-ttu-id="174b1-139">"运行状况" 部分提供了 Lync Server 连接、音频设备、视频设备、复原状态和屏幕设备的运行状况的可视指示。</span><span class="sxs-lookup"><span data-stu-id="174b1-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="174b1-140">![Lync 会议室系统管理门户会议室运行状况](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 会议室系统管理门户会议室运行状况")</span><span class="sxs-lookup"><span data-stu-id="174b1-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="174b1-141">有关管理 Web 门户的其他说明</span><span class="sxs-lookup"><span data-stu-id="174b1-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="174b1-142">只有在 LRS 系统重新启动之后，才会应用设置更改。</span><span class="sxs-lookup"><span data-stu-id="174b1-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="174b1-143">如果 LRSApp 帐户密码过期，将无法看到聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="174b1-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="174b1-144">配置 LRSAppuser 帐户密码，使其永不过期，或者确保在密码即将过期时更新密码。</span><span class="sxs-lookup"><span data-stu-id="174b1-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="174b1-145">仅本地部署支持 LRS 管理 web 门户。</span><span class="sxs-lookup"><span data-stu-id="174b1-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="174b1-146">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="174b1-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="174b1-147">为什么我无法登录管理 web 门户？</span><span class="sxs-lookup"><span data-stu-id="174b1-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="174b1-148">当你打开时 https://localhost/lrs ，你将能够看到登录页，但在你键入凭据时，无法登录。</span><span class="sxs-lookup"><span data-stu-id="174b1-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="174b1-149">在这种情况下，您必须打开 https://FQDNofFEserver/lrs 以登录到管理 web 门户。</span><span class="sxs-lookup"><span data-stu-id="174b1-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="174b1-150">如果要从中访问管理 web 门户的计算机位于工作组中，则 "http://" 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="174b1-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="174b1-151">请改用 "https"。</span><span class="sxs-lookup"><span data-stu-id="174b1-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="174b1-152">为什么我在管理 web 门户中看不到 LRS？</span><span class="sxs-lookup"><span data-stu-id="174b1-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="174b1-153">请确保您的部署中有 LRS 帐户，并根据 LRS 管理 Web 门户部署建议创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="174b1-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="174b1-154">请确保在 Lync server 上使用 Enable-Disable-csmeetingroom，而不是 Enable-Get-csuser 设置 LRS 帐户。</span><span class="sxs-lookup"><span data-stu-id="174b1-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="174b1-155">如果您已创建 LRS 帐户，但在管理 web 门户中看不到这些帐户，请使用选择 **MeetingPortal** 组件的 Lync Server 日志记录工具收集服务器日志，然后将其发送到 LRS 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="174b1-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="174b1-156">为什么我在管理 web 门户中看不到 LRS 的状态？</span><span class="sxs-lookup"><span data-stu-id="174b1-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="174b1-157">请确保 LRSApp 用户帐户启用了 SIP。</span><span class="sxs-lookup"><span data-stu-id="174b1-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="174b1-158">如果仍有问题，请从 D： Trace LRSAdminLogs 中收集 LRS 系统中的 **Trace .log** 文件 \\ \\ \\ ，然后将其发送到 LRS 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="174b1-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


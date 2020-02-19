---
title: Lync Server 2013：通知应用程序的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6282c77a93097ad09aae91dcaf493cf8b7de6f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="c804e-102">Lync Server 2013 中的通知应用程序的部署过程</span><span class="sxs-lookup"><span data-stu-id="c804e-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c804e-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c804e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c804e-104">本节概述了部署通知应用程序所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="c804e-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="c804e-105">您必须先部署企业语音，然后才能配置通知。</span><span class="sxs-lookup"><span data-stu-id="c804e-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="c804e-106">当您部署企业语音时，会安装并启用通知应用程序所需的组件。</span><span class="sxs-lookup"><span data-stu-id="c804e-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="c804e-107">通知部署过程</span><span class="sxs-lookup"><span data-stu-id="c804e-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c804e-108">阶段</span><span class="sxs-lookup"><span data-stu-id="c804e-108">Phase</span></span></th>
<th><span data-ttu-id="c804e-109">步骤</span><span class="sxs-lookup"><span data-stu-id="c804e-109">Steps</span></span></th>
<th><span data-ttu-id="c804e-110">角色</span><span class="sxs-lookup"><span data-stu-id="c804e-110">Roles</span></span></th>
<th><span data-ttu-id="c804e-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="c804e-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c804e-112">配置通知设置</span><span class="sxs-lookup"><span data-stu-id="c804e-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c804e-113">通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。</span><span class="sxs-lookup"><span data-stu-id="c804e-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="c804e-114">配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。</span><span class="sxs-lookup"><span data-stu-id="c804e-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c804e-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c804e-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c804e-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c804e-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c804e-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c804e-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c804e-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c804e-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="c804e-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c804e-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c804e-120"><a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</a></span><span class="sxs-lookup"><span data-stu-id="c804e-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c804e-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中配置未分配号码表</a></span><span class="sxs-lookup"><span data-stu-id="c804e-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c804e-122">验证通知部署</span><span class="sxs-lookup"><span data-stu-id="c804e-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="c804e-123">通过侦听通知来进行测试以验证配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="c804e-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c804e-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Optional在 Lync Server 2013 中验证通知部署</a></span><span class="sxs-lookup"><span data-stu-id="c804e-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


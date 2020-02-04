---
title: Lync Server 2013：按类别分类的 Lync Server cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d5d0dfc2540f5c623bff18f9739968983288e9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="b4988-102">按类别分类的 Lync Server 2013 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b4988-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4988-103">_**主题上次修改时间：** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="b4988-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="b4988-104">Microsoft Lync Server 2013 随附了几乎 550 cmdlet，专门设计用于允许管理员从命令行管理 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b4988-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="b4988-105">可从 Lync Server 命令行管理程序访问 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b4988-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="b4988-106">你可以通过键入类似如下的命令，直接从命令行检索有关 cmdlet 的帮助：</span><span class="sxs-lookup"><span data-stu-id="b4988-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="b4988-107">前面的命令将检索**CsVoicePolicy** cmdlet 的所有可用帮助。</span><span class="sxs-lookup"><span data-stu-id="b4988-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="b4988-108">将对**CsVoicePolicy**的引用替换为要检索帮助的 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="b4988-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="b4988-109">若要检索可用于管理 Microsoft Lync Server 2013 的 cmdlet 的完整列表，请在 Lync Server Management Shell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="b4988-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="b4988-110">如果您不确定需要哪些 cmdlet，我们还提供了一组分类的 cmdlet 及其帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b4988-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="b4988-111">你将发现，某些 cmdlet 显示在多个类别中，这是应用于产品的多个区域的故意。</span><span class="sxs-lookup"><span data-stu-id="b4988-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="b4988-112">以下是类别列表：</span><span class="sxs-lookup"><span data-stu-id="b4988-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b4988-113">Skype for Business cmdlet 参考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b4988-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="b4988-114">单击下面的链接将转至新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="b4988-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="b4988-115">内容现在是开源的，可通过 GitHub 用于社区投稿。</span><span class="sxs-lookup"><span data-stu-id="b4988-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="b4988-116">对投稿感兴趣？</span><span class="sxs-lookup"><span data-stu-id="b4988-116">Interested in contributing?</span></span> <span data-ttu-id="b4988-117">查看存储库中的自述文件：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="b4988-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4988-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="b4988-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4988-119"><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 中的用户管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-120"><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 中的语音应用程序 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4988-121"><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 中的客户端管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 中的高级企业语音 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4988-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 中的 IM 和状态 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 中的 PSTN 连接 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4988-125"><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 中的会议 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 中的电话和设备 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4988-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 中的基础结构和部署 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 中的迁移和共存 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4988-129"><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 中的安全 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server Management Shell 配置 cmdlet 在 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="b4988-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4988-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 中的服务器角色和服务 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-132"><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 中的移动 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4988-133"><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 中的应用程序管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 中的持久聊天服务器 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4988-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 中的联盟和外部访问 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b4988-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 中的集中式日志记录 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4988-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 中的企业语音 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="b4988-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4988-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4988-138">See Also</span></span>


[<span data-ttu-id="b4988-139">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="b4988-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


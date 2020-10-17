---
title: Lync Server 2013：检查最佳实践分析程序的更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97dff101a581927ba0d508da45b1f648d1b9908
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520609"
---
# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e1e61-102">在 Lync Server 2013 中检查最佳实践分析程序的更新</span><span class="sxs-lookup"><span data-stu-id="e1e61-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1e61-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e1e61-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e1e61-104">当您启动最佳实践分析工具时，该工具将提供一个选项，用于搜索工具的最新更新。</span><span class="sxs-lookup"><span data-stu-id="e1e61-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="e1e61-105">如果有可用的更新，则可以下载更新。</span><span class="sxs-lookup"><span data-stu-id="e1e61-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="e1e61-106">如果选择不下载更新，或者最佳实践分析工具无法访问 Internet，则可以继续使用计算机上已有的版本。</span><span class="sxs-lookup"><span data-stu-id="e1e61-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1e61-107">如果需要代理身份验证才能访问 Internet，最佳实践分析工具无法访问要下载的新更新。</span><span class="sxs-lookup"><span data-stu-id="e1e61-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="e1e61-108">不过，您可以从 Microsoft 下载中心手动下载 RtcBPA.msi 的最新版本 <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A> 。</span><span class="sxs-lookup"><span data-stu-id="e1e61-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="e1e61-109">下载文件后，可以将其复制到要更新最佳实践分析工具的计算机上，并使用 .msi 文件在该计算机上安装该工具的新版本。</span><span class="sxs-lookup"><span data-stu-id="e1e61-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="e1e61-110">若要更新最佳实践分析工具规则，必须在本地计算机上以管理员身份运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e1e61-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="e1e61-111">如果您未使用属于 Administrators 组成员的帐户进行登录，并且检测到更新，请关闭最佳实践分析工具，然后使用以下过程启动该程序。</span><span class="sxs-lookup"><span data-stu-id="e1e61-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="e1e61-112">以管理员身份打开最佳实践分析工具以检查是否有更新</span><span class="sxs-lookup"><span data-stu-id="e1e61-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="e1e61-113">在安装了最佳实践分析工具的计算机上，单击 " **开始**"，指向 " **Microsoft Lync Server 2013**"，右键单击 " **最佳实践分析工具**"，然后单击 "以 **管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="e1e61-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e1e61-114">指定属于 Administrators 组成员的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="e1e61-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：检查最佳做法分析器的更新
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
ms.openlocfilehash: ffd05761a1c107ac72c7b9c3242fb18a5a3c7a27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="d5a0f-102">在 Lync Server 2013 中检查最佳做法分析器的更新</span><span class="sxs-lookup"><span data-stu-id="d5a0f-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a0f-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d5a0f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d5a0f-104">当您启动最佳做法分析器时，该工具会向您提供一个选项，可用于搜索该工具的最新更新。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="d5a0f-105">如果有可用更新，则可以下载更新。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="d5a0f-106">如果您选择不下载更新，或者最佳做法分析器无法访问 Internet，则可以继续使用计算机上已有的版本。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5a0f-107">如果需要代理身份验证才能访问 Internet，最佳做法分析器无法访问要下载的新更新。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="d5a0f-108">但是，您可以从 Microsoft 下载中心手动下载最新版本的 RtcBPA <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="d5a0f-109">下载文件后，您可以将其复制到要更新最佳做法分析器的计算机上，并使用 .msi 文件在该计算机上安装新版本的工具。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="d5a0f-110">若要更新最佳做法分析器规则，必须以本地计算机上的管理员身份运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="d5a0f-111">如果您未使用管理员组成员的帐户登录，并且检测到更新，请关闭最佳做法分析器，然后按以下步骤启动程序。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="d5a0f-112">以管理员身份打开最佳做法分析器以检查更新</span><span class="sxs-lookup"><span data-stu-id="d5a0f-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="d5a0f-113">在安装了最佳做法分析器的计算机上，单击 "**开始**"，指向 " **Microsoft Lync Server 2013**"，右键单击 "**最佳做法分析器**"，然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="d5a0f-114">指定属于管理员组成员的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 安装 Lync Server 2013 core 文件和 RTCLocal 数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eefd8316e0e33ab8c4418a6ce72ea9eb05fc84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="8c2c9-102">安装 Lync Server 2013 core 文件和 RTCLocal 数据库</span><span class="sxs-lookup"><span data-stu-id="8c2c9-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c2c9-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8c2c9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8c2c9-104">若要在计算机上安装 Lync Server 2013 core 文件，请完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="8c2c9-105">当您安装核心文件时，将自动安装 RTCLocal 数据库。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="8c2c9-106">请注意，不需要在观察程序节点上安装 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="8c2c9-107">相反，系统会自动为你安装 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="8c2c9-108">若要安装 Lync Server 2013 core 文件和 RTCLocal 数据库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8c2c9-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="8c2c9-109">在观察程序节点计算机上，依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“附件”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8c2c9-110">在控制台窗口中，键入以下命令，然后按 ENTER，并使用适用于 Lync Server 安装程序文件的路径：</span><span class="sxs-lookup"><span data-stu-id="8c2c9-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="8c2c9-111">若要验证是否已成功安装核心 Lync Server 组件，请依次单击 "**开始**"、"**所有程序**"、" **lync server 2013**"，然后单击 " **lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="8c2c9-112">在 "Lync Server 2013 命令行管理程序" 中，键入以下 Windows PowerShell 命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="8c2c9-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="8c2c9-113">首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="8c2c9-114">只要命令在不返回错误的情况下运行，您就可以假定 Lync Server 安装程序已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="8c2c9-115">如果您的观察程序节点计算机位于您的外围网络中，则可以运行以下命令来验证 Lync Server 2013 的安装：</span><span class="sxs-lookup"><span data-stu-id="8c2c9-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="8c2c9-116">根据配置用于您的组织的个人标识号 (PIN) 策略的数目，您将收到如下信息：</span><span class="sxs-lookup"><span data-stu-id="8c2c9-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="8c2c9-117">如果显示有关您的 PIN 策略的信息，表明您已成功安装核心组件。</span><span class="sxs-lookup"><span data-stu-id="8c2c9-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


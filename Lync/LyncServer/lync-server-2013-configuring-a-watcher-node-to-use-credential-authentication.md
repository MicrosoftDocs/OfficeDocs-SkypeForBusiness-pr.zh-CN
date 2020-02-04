---
title: Lync Server 2013：配置观察程序节点以使用凭据身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="20b0c-102">将观察程序节点配置为使用 Lync Server 2013 中的凭据身份验证</span><span class="sxs-lookup"><span data-stu-id="20b0c-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20b0c-103">_**主题上次修改时间：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="20b0c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="20b0c-104">如果你的观察程序节点计算机位于外围网络之外，则你必须执行稍有不同的过程，才能将该观察程序节点配置为运行合成事务。</span><span class="sxs-lookup"><span data-stu-id="20b0c-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="20b0c-105">具体而言，不应创建受信任的应用程序池和受信任的应用程序，并且必须安装一个允许观察程序节点向外围网络内的计算机发送警报的证书。</span><span class="sxs-lookup"><span data-stu-id="20b0c-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="20b0c-106">这意味着你需要完成两个单独的任务：</span><span class="sxs-lookup"><span data-stu-id="20b0c-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="20b0c-107">更新计算机的 RTC 本地只读管理员组中的成员身份</span><span class="sxs-lookup"><span data-stu-id="20b0c-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="20b0c-108">安装观察程序节点配置文件</span><span class="sxs-lookup"><span data-stu-id="20b0c-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="20b0c-109">更新 RTC 本地只读管理员组中的成员身份</span><span class="sxs-lookup"><span data-stu-id="20b0c-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="20b0c-110">如果你的观察程序节点位于外围网络外部，则必须将网络服务帐户添加到观察程序节点计算机上的 RTC 本地只读管理员组。</span><span class="sxs-lookup"><span data-stu-id="20b0c-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="20b0c-111">若要执行此操作，请在 "观察程序" 节点上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="20b0c-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="20b0c-112">单击 "**开始**"，右键单击 "**计算机**"，然后单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="20b0c-113">在服务器管理器中，展开 "**配置**"，展开 "**本地用户和组**"，然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="20b0c-114">在 "组" 窗格中，双击 " **RTC 本地只读管理员**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="20b0c-115">在 " **RTC 本地只读管理员属性**" 对话框中，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="20b0c-116">在 "**选择用户、计算机、服务帐户或组**" 对话框中，单击 "**位置**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="20b0c-117">在 "**位置**" 对话框中，选择 "观察程序节点" 计算机的名称，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="20b0c-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="20b0c-118">在 "**输入要选择的对象名称**" 框中，键入 "**网络服务**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="20b0c-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="20b0c-119">在 " **RTC 本地只读管理员属性**" 对话框中，单击 **"确定**"，然后关闭 "**服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="20b0c-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="20b0c-120">重新启动观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="20b0c-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="20b0c-121">安装观察程序节点配置文件</span><span class="sxs-lookup"><span data-stu-id="20b0c-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="20b0c-122">在观察程序节点计算机重启后，下一步是运行文件 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="20b0c-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="20b0c-123">若要运行此文件，请依次单击 "**开始**"、"**所有程序**"、" **lync server 2013**"，然后单击 " **Lync Server Management Shell**"，打开 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="20b0c-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="20b0c-124">在 Lync Server 命令行管理器中，键入以下命令，然后按 ENTER （确保并指定 Watchernode 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="20b0c-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="20b0c-125">正如前面所述，Watchernode 也可以从命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="20b0c-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="20b0c-126">若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="20b0c-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="20b0c-127">当 "命令" 窗口打开时，键入与前面所示相同的命令。</span><span class="sxs-lookup"><span data-stu-id="20b0c-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="20b0c-p105">任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。在此模式中，管理员需要管理观察程序节点上的测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="20b0c-p105">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


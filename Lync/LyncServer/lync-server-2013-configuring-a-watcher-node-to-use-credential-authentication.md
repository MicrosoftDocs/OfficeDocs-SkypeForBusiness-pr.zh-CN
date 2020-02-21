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
ms.openlocfilehash: 3ee0d5a07ebd04e6eec585c79eb13b9be7fe98a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="b0182-102">将观察程序节点配置为在 Lync Server 2013 中使用凭据身份验证</span><span class="sxs-lookup"><span data-stu-id="b0182-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0182-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b0182-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b0182-p101">如果您的观察程序节点计算机位于外围网络之外，则您必须遵循一个略有不同的过程来配置该观察程序节点以运行综合事务。具体而言，不应创建一个受信任的应用程序池和受信任的应用程序，而且必须安装一个证书，使得观察程序节点能够向外围网络内的计算机发送警报。这意味着您需要完成两个单独的任务：</span><span class="sxs-lookup"><span data-stu-id="b0182-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="b0182-107">更新计算机的 RTC Local Read-only Administrators 组中的成员身份</span><span class="sxs-lookup"><span data-stu-id="b0182-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="b0182-108">安装观察程序节点配置文件</span><span class="sxs-lookup"><span data-stu-id="b0182-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="b0182-109">更新 RTC Local Read-Only Administrators 组中的成员身份</span><span class="sxs-lookup"><span data-stu-id="b0182-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="b0182-p102">如果您的观察程序节点位于外围网络之外，则您必须将 Network Service 帐户添加到观察程序节点计算机上的 RTC Local Read-only Administrators 组。为此，请在观察程序节点上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="b0182-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="b0182-112">单击“开始”\*\*\*\*，右键单击“计算机”\*\*\*\*，然后单击“管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="b0182-113">在服务器管理器中，展开“配置”\*\*\*\*，展开“本地用户和组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="b0182-114">在“组”窗格中，双击“RTC Local Read-only Administrators”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="b0182-115">在“RTC Local Read-only Administrators 属性”\*\*\*\* 对话框中，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="b0182-116">在“选择用户、计算机、服务帐户或组”\*\*\*\* 对话框中，单击“位置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="b0182-117">在“位置”\*\*\*\* 对话框中，选择观察程序节点计算机的名称，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="b0182-118">在“输入要选择的对象名称”\*\*\*\* 框中，键入“Network Service”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="b0182-119">在“RTC Local Read-only Administrators 属性”\*\*\*\* 对话框中，单击“确定”\*\*\*\*，然后关闭“服务器管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0182-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="b0182-120">重新启动观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="b0182-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="b0182-121">安装观察程序节点配置文件</span><span class="sxs-lookup"><span data-stu-id="b0182-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="b0182-122">重新启动观察程序节点计算机后，下一步是运行文件 Watchernode.msi。</span><span class="sxs-lookup"><span data-stu-id="b0182-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="b0182-123">若要运行此文件，请依次单击 "**开始**"、"**所有程序**"、" **lync Server 2013**" 和 " **lync server 命令行管理**程序"，打开 Lync server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b0182-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="b0182-124">在 Lync Server 命令行管理程序中，键入以下命令，然后按 ENTER （确保并指定 Watchernode.msi 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="b0182-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="b0182-p104">如上所述，还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。命令窗口打开后，键入如上所示的相同命令。</span><span class="sxs-lookup"><span data-stu-id="b0182-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="b0182-128">任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。</span><span class="sxs-lookup"><span data-stu-id="b0182-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="b0182-129">在此模式中，管理员需要管理观察程序节点上的测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="b0182-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


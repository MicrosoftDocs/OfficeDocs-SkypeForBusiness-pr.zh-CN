---
title: Lync Server 2013：对 Lync VDI 插件进行故障排除
description: Lync Server 2013：对 Lync VDI 插件进行故障排除。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548938"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="32a43-103">在 Lync Server 2013 中对 Lync VDI 插件进行故障排除</span><span class="sxs-lookup"><span data-stu-id="32a43-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32a43-104">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="32a43-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="32a43-105">解决在瘦客户端上安装 Lync VDI 插件时出现的问题</span><span class="sxs-lookup"><span data-stu-id="32a43-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="32a43-106">如果在瘦客户端上安装 VDI 插件时出现问题，请检查以下几点：</span><span class="sxs-lookup"><span data-stu-id="32a43-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="32a43-107">确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。</span><span class="sxs-lookup"><span data-stu-id="32a43-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="32a43-p101">确保已关闭写保护。有关说明，请参阅设备制造商的文档。</span><span class="sxs-lookup"><span data-stu-id="32a43-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="32a43-110">排除配对问题</span><span class="sxs-lookup"><span data-stu-id="32a43-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="32a43-111">当 VDI 插件配对失败时，右下方的配对图标将显示为红色的“X”，如图所示：</span><span class="sxs-lookup"><span data-stu-id="32a43-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="32a43-112">![显示成功配对的 Lync VDI 图标](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "显示成功配对的 Lync VDI 图标")</span><span class="sxs-lookup"><span data-stu-id="32a43-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="32a43-113">以下是出现故障的可能原因以及可以采取的更正措施。</span><span class="sxs-lookup"><span data-stu-id="32a43-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="32a43-114">**用户在登录期间输入错误凭据。**</span><span class="sxs-lookup"><span data-stu-id="32a43-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="32a43-115">用户应注销 Lync，然后使用正确的凭据重新登录。</span><span class="sxs-lookup"><span data-stu-id="32a43-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="32a43-116">配对对话框将重新出现，并显示配对是否成功。</span><span class="sxs-lookup"><span data-stu-id="32a43-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="32a43-117">**另一个远程桌面客户端的实例正在运行。**</span><span class="sxs-lookup"><span data-stu-id="32a43-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="32a43-118">如果他们使用的是 Windows 中的远程桌面连接，则用户应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="32a43-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="32a43-119">启动任务管理器：按“Alt+Ctrl+Delete”\*\*\*\*，然后单击“启动任务管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32a43-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="32a43-120">单击“进程”\*\*\*\* 选项卡并在列表中查找名为“mstsc.exe”\*\*\*\* 的所有进程。</span><span class="sxs-lookup"><span data-stu-id="32a43-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="32a43-121">突出显示每个“mstsc.exe”\*\*\*\* 进程，然后单击“结束进程”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32a43-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="32a43-122">启动新远程桌面会话并尝试再次连接。</span><span class="sxs-lookup"><span data-stu-id="32a43-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="32a43-123">**必要的文件未正确安装。**</span><span class="sxs-lookup"><span data-stu-id="32a43-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="32a43-124">将插件安装在本地计算机上后，下列文件应显示在 C： \\ Program files \\ Microsoft Office \\ Office15 (或相应的驱动器号) ：</span><span class="sxs-lookup"><span data-stu-id="32a43-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="32a43-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="32a43-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="32a43-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="32a43-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="32a43-127">如果 VDI 配对出现任何问题，请检查以确保本地计算机上显示这些文件。</span><span class="sxs-lookup"><span data-stu-id="32a43-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="32a43-128">**Lync 客户端正在本地计算机上运行。**</span><span class="sxs-lookup"><span data-stu-id="32a43-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="32a43-129">若要使用 Lync VDI 插件，Lync 客户端不得在本地计算机上运行，否则配对将会失败。</span><span class="sxs-lookup"><span data-stu-id="32a43-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="32a43-130">最佳做法是，用户不应在本地计算机上安装 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="32a43-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


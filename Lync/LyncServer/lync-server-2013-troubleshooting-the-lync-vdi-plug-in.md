---
title: 'Lync Server 2013: 疑难解答 Lync VDI 插件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="bfb95-102">在 Lync Server 2013 中对 Lync VDI 插件进行故障排除</span><span class="sxs-lookup"><span data-stu-id="bfb95-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfb95-103">_**主题上次修改时间:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="bfb95-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="bfb95-104">解决在瘦客户端上安装 Lync VDI 插件时遇到的问题</span><span class="sxs-lookup"><span data-stu-id="bfb95-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="bfb95-105">如果在瘦客户端上安装 VDI 插件时出现问题, 请检查以下事项:</span><span class="sxs-lookup"><span data-stu-id="bfb95-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="bfb95-106">确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。</span><span class="sxs-lookup"><span data-stu-id="bfb95-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="bfb95-p101">确保已关闭写保护。有关说明，请参阅设备制造商的文档。</span><span class="sxs-lookup"><span data-stu-id="bfb95-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="bfb95-109">排除在配对时出现的问题</span><span class="sxs-lookup"><span data-stu-id="bfb95-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="bfb95-110">当 VDI 插件配对失败时, 右下角的配对图标将显示为红色的 "X", 如下所示:</span><span class="sxs-lookup"><span data-stu-id="bfb95-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="bfb95-111">![LYNC VDI 图标显示成功配对](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "LYNC VDI 图标显示成功配对")</span><span class="sxs-lookup"><span data-stu-id="bfb95-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="bfb95-112">以下是失败的可能原因以及可以执行的纠正操作。</span><span class="sxs-lookup"><span data-stu-id="bfb95-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="bfb95-113">**用户在登录期间输入的凭据不正确。**</span><span class="sxs-lookup"><span data-stu-id="bfb95-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="bfb95-114">用户应注销 Lync, 然后使用正确的凭据再次登录。</span><span class="sxs-lookup"><span data-stu-id="bfb95-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="bfb95-115">配对对话框将重新出现，并显示配对是否成功。</span><span class="sxs-lookup"><span data-stu-id="bfb95-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="bfb95-116">**远程桌面客户端的另一个实例正在运行。**</span><span class="sxs-lookup"><span data-stu-id="bfb95-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="bfb95-117">如果他们使用的是 Windows 中的远程桌面连接, 则用户应该执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="bfb95-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="bfb95-118">启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。</span><span class="sxs-lookup"><span data-stu-id="bfb95-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="bfb95-119">单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。</span><span class="sxs-lookup"><span data-stu-id="bfb95-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="bfb95-120">突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。</span><span class="sxs-lookup"><span data-stu-id="bfb95-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="bfb95-121">启动新的远程桌面会话并再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="bfb95-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="bfb95-122">**未正确安装必要的文件。**</span><span class="sxs-lookup"><span data-stu-id="bfb95-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="bfb95-123">在本地计算机上安装插件后, 以下文件应存在于 C:\\Program 文件\\Microsoft Office\\Office15 (或相应的驱动器号) 下:</span><span class="sxs-lookup"><span data-stu-id="bfb95-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="bfb95-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="bfb95-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="bfb95-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="bfb95-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="bfb95-126">如果 VDI 配对存在任何问题, 请检查以确保本地计算机上存在这些文件。</span><span class="sxs-lookup"><span data-stu-id="bfb95-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="bfb95-127">**Lync 客户端正在本地计算机上运行。**</span><span class="sxs-lookup"><span data-stu-id="bfb95-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="bfb95-128">若要使用 Lync VDI 插件, Lync 客户端不能在本地计算机上运行, 否则配对将失败。</span><span class="sxs-lookup"><span data-stu-id="bfb95-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="bfb95-129">最佳做法是, 用户不应在本地计算机上安装 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="bfb95-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 运行 LyncPerfTool
description: 运行 LyncPerfTool。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560078"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="95042-103">运行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="95042-103">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95042-104">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="95042-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="95042-105">在运行 Lync Server 2013 的压力和性能工具之前 ( # A0) 中，必须创建用户、联系人和方案。</span><span class="sxs-lookup"><span data-stu-id="95042-105">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="95042-106">有关使用这些工具执行这些操作的详细信息，请参阅 [创建用户和联系人](create-users-and-contacts.md) 和 [配置用户配置文件](configure-user-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="95042-106">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="95042-107">运行这些工具还将生成一个文件，该文件将作为批处理文件的一部分运行 LyncPerfTool.exe，其中包含所需的参数。</span><span class="sxs-lookup"><span data-stu-id="95042-107">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="95042-108">运行 Lync Server 2013 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="95042-108">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="95042-109">UserProfileGenerator.exe 工具创建批处理文件，通过注册 LyncPerfTool 性能计数器并加载 XML 配置文件，可以运行 LyncPerfTool.exe。</span><span class="sxs-lookup"><span data-stu-id="95042-109">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="95042-110">批处理文件运行每个配置文件 LyncPerfTool.exe 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="95042-110">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="95042-111">若要运行批处理文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95042-111">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="95042-112">将包含配置文件夹和文件的文件夹复制到每台客户端计算机上包含 LyncStressTool.exe 的目录中。</span><span class="sxs-lookup"><span data-stu-id="95042-112">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="95042-113"> (例如，如果在名为 1.28 13.16.16 的文件夹中生成配置文件 \_ ，请将该文件夹复制到每个客户端上包含 LyncPerfTool.exe 的文件夹中。 ) </span><span class="sxs-lookup"><span data-stu-id="95042-113">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="95042-114">导航到相应编号的客户端文件夹，并运行 RunClient 批处理脚本。</span><span class="sxs-lookup"><span data-stu-id="95042-114">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="95042-115">您可以简单地在 Windows 资源管理器中双击批处理文件，它将运行该客户端编号的所有配置文件。</span><span class="sxs-lookup"><span data-stu-id="95042-115">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="95042-116">您还可以通过使用以下语法，从相应的客户端文件夹运行脚本：</span><span class="sxs-lookup"><span data-stu-id="95042-116">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="95042-117">若要直接运行 LyncPerfTool.exe，请打开命令提示符，然后在命令行中键入以下命令， (在首次执行此操作时，请务必注册性能计数器 regsvr32/i/i/i/n LyncPerfToolPerf.dll，如本主题后面的注释所示) # A2/file：\<configXML\></span><span class="sxs-lookup"><span data-stu-id="95042-117">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="95042-118">若要使该工具显示配置文件中的值，请在前面的命令中包含/displayfile 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="95042-118">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="95042-119">若要结束此过程，请按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="95042-119">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95042-120">在直接运行 LyncPerfTool 之前，必须注册性能计数器。</span><span class="sxs-lookup"><span data-stu-id="95042-120">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="95042-121">输入以下命令以注册性能计数器：</span><span class="sxs-lookup"><span data-stu-id="95042-121">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="95042-122">启动的每个 LyncPerfTool.exe 实例都会立即开始在用户中进行签名，通常是每秒一个用户的速度。</span><span class="sxs-lookup"><span data-stu-id="95042-122">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="95042-123">池的最大用户登录速率为每秒大约12次。</span><span class="sxs-lookup"><span data-stu-id="95042-123">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="95042-124">这意味着，您不应同时启动多于12个 LyncPerfTool 实例，而用户仍在登录。</span><span class="sxs-lookup"><span data-stu-id="95042-124">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="95042-125">1000用户需要大约20分钟才能完全登录，每秒一个。</span><span class="sxs-lookup"><span data-stu-id="95042-125">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95042-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95042-126">See Also</span></span>


[<span data-ttu-id="95042-127">创建用户和联系人</span><span class="sxs-lookup"><span data-stu-id="95042-127">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="95042-128">配置用户配置文件</span><span class="sxs-lookup"><span data-stu-id="95042-128">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 预配要运行加载的拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026915b4a08073e96d29b32278adc4e260eaaea4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="49978-102">预配要运行加载的拓扑</span><span class="sxs-lookup"><span data-stu-id="49978-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49978-103">_**主题上次修改时间:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="49978-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="49978-104">预配要运行加载的拓扑</span><span class="sxs-lookup"><span data-stu-id="49978-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="49978-105">你可能需要在你的环境中进行以下更改, 具体取决于 Lync Server 2013 的现有设置和配置:</span><span class="sxs-lookup"><span data-stu-id="49978-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="49978-106">将 Windows PowerShell 执行策略设置为 "无限制"。</span><span class="sxs-lookup"><span data-stu-id="49978-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="49978-107">若要检查执行策略设置, 请打开 Lync Server 命令行管理程序, 然后运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="49978-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="49978-108">如果此命令不会返回不受限制的值, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="49978-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="49978-109">若要有效配置 Lync Server 2013, 您需要:</span><span class="sxs-lookup"><span data-stu-id="49978-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="49978-110">熟悉 Lync Server 2013 拓扑 (例如, 计算机名称、服务实例、站点名称和策略)。</span><span class="sxs-lookup"><span data-stu-id="49978-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="49978-111">将已创建的某些用户分配给组, 例如 "响应组查寻组" (例如 SIP Uri)。</span><span class="sxs-lookup"><span data-stu-id="49978-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="49978-112">若要从命令行运行脚本, 您可以使用:</span><span class="sxs-lookup"><span data-stu-id="49978-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="49978-113">通常, 在此程序包中的某个脚本运行后, 脚本生成的跟踪将存储在一个文件中, 该文件位于调用脚本的同一路径中, 名为\<scriptname\>$h $ m $ s .txt。</span><span class="sxs-lookup"><span data-stu-id="49978-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="49978-114">例如, 在 12:15 P.M. 运行 ArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="49978-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="49978-115">将生成一个日志文件, 如 ArchivingPolicy121500。</span><span class="sxs-lookup"><span data-stu-id="49978-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="49978-116">最后, 请注意, 虽然我们提供了配置服务器的示例, 但你负责在运行完加载后修改或删除配置。</span><span class="sxs-lookup"><span data-stu-id="49978-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


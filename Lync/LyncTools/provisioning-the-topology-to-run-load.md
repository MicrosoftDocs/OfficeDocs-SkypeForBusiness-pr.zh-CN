---
title: 设置要运行负载的拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a913dc678b2f5e929ad22e09e1d8350f667ce39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="d1c90-102">设置要运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="d1c90-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c90-103">_**上次修改的主题：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="d1c90-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="d1c90-104">设置要运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="d1c90-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="d1c90-105">根据您现有的 Lync Server 2013 的设置和配置，您可能需要在您的环境中进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="d1c90-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="d1c90-106">将 Windows PowerShell 执行策略设置为无限制。</span><span class="sxs-lookup"><span data-stu-id="d1c90-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="d1c90-107">若要检查执行策略设置，请打开 Lync Server 命令行管理程序，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1c90-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="d1c90-108">如果此命令不会返回不受限制的值，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1c90-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="d1c90-109">若要有效配置 Lync Server 2013，您将需要：</span><span class="sxs-lookup"><span data-stu-id="d1c90-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="d1c90-110">熟悉 Lync Server 2013 拓扑（例如，计算机名称、服务实例、站点名称和策略）。</span><span class="sxs-lookup"><span data-stu-id="d1c90-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="d1c90-111">将一些已创建的用户分配给组，例如响应组智能寻线（例如，SIP Uri）。</span><span class="sxs-lookup"><span data-stu-id="d1c90-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="d1c90-112">若要从命令行运行脚本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="d1c90-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="d1c90-113">通常，在此包中的一个脚本运行之后，脚本生成的跟踪将存储在一个文件中，该文件与从中调用脚本的路径相同，名为\<scriptname\>$h $ m $ s .txt。</span><span class="sxs-lookup"><span data-stu-id="d1c90-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="d1c90-114">例如，在 12:15 P.M. 运行 ArchivingPolicy。. ps1</span><span class="sxs-lookup"><span data-stu-id="d1c90-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="d1c90-115">将生成一个日志文件，如 ArchivingPolicy121500。</span><span class="sxs-lookup"><span data-stu-id="d1c90-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="d1c90-116">最后，请注意，虽然我们提供了配置服务器的示例，但您负责在运行完负载后修改或删除配置。</span><span class="sxs-lookup"><span data-stu-id="d1c90-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


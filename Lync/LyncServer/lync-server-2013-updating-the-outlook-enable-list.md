---
title: Lync Server 2013：更新 Outlook 启用列表
description: Lync Server 2013：更新 Outlook 启用列表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546228"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="b395f-103">在 Lync Server 2013 中更新 Outlook 启用列表</span><span class="sxs-lookup"><span data-stu-id="b395f-103">Updating the Outlook enable list in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b395f-104">_**上次修改的主题：** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="b395f-104">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="b395f-105">您可以通过在 Outlook 外接程序管理列表中创建包含它的策略来确保 Microsoft Lync 2013 的联机会议外接程序始终为用户启用。</span><span class="sxs-lookup"><span data-stu-id="b395f-105">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="b395f-106">外接程序管理列表策略包含在组策略管理控制台的 Office 管理模板文件中。</span><span class="sxs-lookup"><span data-stu-id="b395f-106">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="b395f-107">它在 "HKCU \\ 软件 \\ 策略 \\ Microsoft \\ Office \\ 15.0 \\ Outlook15 \\ 弹性 \\ AddinList" 下创建一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="b395f-107">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="b395f-108">您可以将 ucaddin.dll 的值添加到此项，并配置 ucaddin.dll 值以使其始终处于启用状态，以便用户无法手动禁用它</span><span class="sxs-lookup"><span data-stu-id="b395f-108">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="b395f-109">将 ucaddin.dll 添加到 Outlook 外接列表中</span><span class="sxs-lookup"><span data-stu-id="b395f-109">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="b395f-110">若要在 "HKCU \\ 软件 \\ 策略 Microsoft Office 15.0 Outlook15 弹性 AddinList" 下找到 AddinList 注册表项， \\ \\ \\ \\ \\ \\ 请添加以下值：</span><span class="sxs-lookup"><span data-stu-id="b395f-110">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="b395f-111">注册表类型 = REG \_ SZ</span><span class="sxs-lookup"><span data-stu-id="b395f-111">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="b395f-112">名称 = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="b395f-112">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="b395f-113">值 = 1（指定外接程序始终保持启用状态，且无法由最终用户管理）</span><span class="sxs-lookup"><span data-stu-id="b395f-113">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


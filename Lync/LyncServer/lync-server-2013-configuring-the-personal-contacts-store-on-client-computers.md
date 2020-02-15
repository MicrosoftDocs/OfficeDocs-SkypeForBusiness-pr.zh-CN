---
title: Lync Server 2013：在客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5672619302e169db5e89281323eec4b5d8312c06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="c9723-102">在客户端计算机上为 Lync Server 2013 配置个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="c9723-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9723-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c9723-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c9723-104">如果要集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，建议您在运行 Microsoft Lync 2010 的任何客户端计算机上配置个人联系人存储。</span><span class="sxs-lookup"><span data-stu-id="c9723-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="c9723-105">特别是，应将 Lync 配置为将 Exchange 用作个人联系人存储，同时确保用户无法覆盖该决定。</span><span class="sxs-lookup"><span data-stu-id="c9723-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="c9723-106">这可以通过在每个客户端计算机上创建和配置注册表值来完成。</span><span class="sxs-lookup"><span data-stu-id="c9723-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="c9723-107">请注意，运行 Lync 2013 的计算机上不需要执行此项。</span><span class="sxs-lookup"><span data-stu-id="c9723-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="c9723-108">要在单个计算机上配置此值，请完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="c9723-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="c9723-109">在客户端计算机上，单击 "**开始**"，然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="c9723-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c9723-110">在 "**运行**" 对话框中，键入 "regedit"，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="c9723-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="c9723-111">在注册表编辑器中，**展开\_"\_HKEY 本地计算机**"，展开 "**软件**"，展开 "**策略**"，展开 " **Microsoft**"，然后展开 " **Communicator**"。</span><span class="sxs-lookup"><span data-stu-id="c9723-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="c9723-112">右键单击 " **Communicator**"，指向 "**新建**"，然后单击 " **DWORD （32-位）值**"。</span><span class="sxs-lookup"><span data-stu-id="c9723-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="c9723-113">创建新值后，键入**PersonalContactStoreOverride** ，然后按 enter 以重命名该值。</span><span class="sxs-lookup"><span data-stu-id="c9723-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c9723-114">验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="c9723-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="c9723-115">如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c9723-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="c9723-116">有关详细信息，请参阅中的组[http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)策略文档。</span><span class="sxs-lookup"><span data-stu-id="c9723-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


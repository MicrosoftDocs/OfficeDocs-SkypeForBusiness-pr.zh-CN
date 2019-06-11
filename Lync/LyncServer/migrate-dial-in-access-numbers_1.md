---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="dc344-102">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="dc344-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc344-103">_**主题上次修改时间:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="dc344-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="dc344-104">迁移拨入访问号码需要两个步骤: 运行**CsLegacyConfiguration** cmdlet (在[导入策略和设置](import-policies-and-settings.md)中完成) 若要迁移拨号计划和其他拨入访问号码设置, 并运行**CsApplicationEndpoint** cmdlet 迁移联系人对象。</span><span class="sxs-lookup"><span data-stu-id="dc344-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="dc344-105">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="dc344-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="dc344-106">打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="dc344-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="dc344-107">在控制台树中, 右键单击 "林" 节点, 单击 "**属性**", 然后单击 "**会议助理属性**"。</span><span class="sxs-lookup"><span data-stu-id="dc344-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="dc344-108">在 "**访问电话号码**" 选项卡上, 单击 "**按池服务**" 以按其关联的池对访问电话号码进行排序, 并确定要从中迁移的池的所有访问号码。</span><span class="sxs-lookup"><span data-stu-id="dc344-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="dc344-109">若要标识每个访问号码的 SIP URI, 请双击访问号码以打开 "**编辑会议助理号码**" 对话框, 然后查看 " **SIP URI**" 下的对话框。</span><span class="sxs-lookup"><span data-stu-id="dc344-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="dc344-110">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="dc344-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="dc344-111">若要将每个拨入访问号码移动到 Lync Server 2013 上托管的池, 请运行:</span><span class="sxs-lookup"><span data-stu-id="dc344-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="dc344-112">在 Office 通信服务器 2007 R2 管理工具中的 "**访问电话号码**" 选项卡上, 验证你要从中迁移的 Office 通信服务器 2007 R2 池不保留拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="dc344-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


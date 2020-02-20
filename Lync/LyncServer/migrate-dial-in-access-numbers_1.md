---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="80c7e-102">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="80c7e-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80c7e-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="80c7e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="80c7e-104">迁移拨入访问号码需要两个步骤：运行**CsLegacyConfiguration** cmdlet （在 "[导入策略和设置](import-policies-and-settings.md)" 中完成）以迁移拨号计划和其他电话拨入式访问号码设置，并运行**CsApplicationEndpoint** cmdlet 以迁移 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="80c7e-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="80c7e-105">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="80c7e-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="80c7e-106">打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="80c7e-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="80c7e-107">在控制台树中，右键单击林节点，单击“属性”\*\*\*\*，然后单击“会议助理属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80c7e-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="80c7e-108">在“访问电话号码”\*\*\*\* 选项卡上，单击“由池提供服务”\*\*\*\*，按照访问电话号码的关联池排序这些号码，然后确定要从其中迁移的池的所有访问号码。</span><span class="sxs-lookup"><span data-stu-id="80c7e-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="80c7e-109">要确定每个访问号码的 SIP URI，请双击相应访问号码以打开“编辑会议助理号码”\*\*\*\* 对话框，然后在“SIP URI”\*\*\*\* 下进行查找。</span><span class="sxs-lookup"><span data-stu-id="80c7e-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="80c7e-110">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="80c7e-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="80c7e-111">若要将每个拨入访问号码移到在 Lync Server 2013 上托管的池，请运行：</span><span class="sxs-lookup"><span data-stu-id="80c7e-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="80c7e-112">在 "Office 通信服务器 2007 R2 管理工具" 的 "**访问电话号码**" 选项卡上，验证您要从中迁移的 Office 通信服务器 2007 R2 池不保留拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="80c7e-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


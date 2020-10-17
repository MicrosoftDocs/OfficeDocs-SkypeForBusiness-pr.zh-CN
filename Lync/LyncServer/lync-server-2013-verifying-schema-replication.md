---
title: Lync Server 2013：验证架构复制
description: Lync Server 2013：验证架构复制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560168"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="cf0c9-103">在 Lync Server 2013 中验证 Active Directory 架构复制</span><span class="sxs-lookup"><span data-stu-id="cf0c9-103">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf0c9-104">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="cf0c9-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="cf0c9-105">在运行林准备之前，请手动验证架构分区是否已复制。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-105">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="cf0c9-106">手动验证架构复制</span><span class="sxs-lookup"><span data-stu-id="cf0c9-106">To manually verify schema replication</span></span>

1.  <span data-ttu-id="cf0c9-107">以 Enterprise Admins 组成员的身份登录到域控制器。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-107">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="cf0c9-108">依次单击 **“开始”**、**“管理工具”**、**“ADSI Edit”** 以打开 ADSI Edit。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-108">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="cf0c9-109">此外，还可以从命令行运行 <STRONG>adsiedit.msc</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-109">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="cf0c9-110">在 Microsoft 管理控制台 (MMC) 树中，单击 **“ADSI Edit”**（如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-110">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="cf0c9-111">在 **“操作”** 菜单上，单击 **“连接到”**。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-111">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="cf0c9-112">在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-112">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="cf0c9-113">在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-113">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="cf0c9-114">如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-114">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="cf0c9-115">如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="cf0c9-115">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf0c9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf0c9-116">See Also</span></span>


[<span data-ttu-id="cf0c9-117">在 Lync Server 2013 中运行 Active Directory 架构准备</span><span class="sxs-lookup"><span data-stu-id="cf0c9-117">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="cf0c9-118">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="cf0c9-118">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


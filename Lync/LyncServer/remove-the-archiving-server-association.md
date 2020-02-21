---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c53ef1e70b174681149593237db3f9d0268209
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="6bdb3-102">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="6bdb3-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bdb3-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6bdb3-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="6bdb3-104">若要删除存档服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="6bdb3-105">您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="6bdb3-106">清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="6bdb3-107">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="6bdb3-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="6bdb3-108">打开 Lync Server 2013 前端服务器，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="6bdb3-109">导航到 "Lync Server 2010" 节点。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="6bdb3-110">在拓扑生成器中，根据在其中定义存档服务器的位置扩展**Enterprise Edition 前端池**、 **Standard edition 前端服务器**或**分支站点**。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="6bdb3-111">如果你有与 Survivable 分支服务器相关联的，请展开 "**分支站点**"，展开分支站点名称，然后展开 " **Survivable 分支设备**"。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6bdb3-112">用户界面中的<STRONG>Survivable 分支设备</STRONG>适用于 Survivable 分支服务器和 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="6bdb3-113">右键单击与存档服务器关联的池、服务器或设备，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="6bdb3-114">在“编辑属性”\*\*\*\* 的“常规”\*\*\*\* 下的“关联”\*\*\*\* 下，清除“关联存档服务器”\*\*\*\* 复选框，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="6bdb3-115">对与要删除的存档服务器关联的任何其他池、服务器或设备重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="6bdb3-116">右键单击存档服务器，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="6bdb3-117">在“删除相关存储”\*\*\*\* 上，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="6bdb3-118">发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="6bdb3-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


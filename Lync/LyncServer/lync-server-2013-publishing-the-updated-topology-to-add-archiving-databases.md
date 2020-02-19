---
title: Lync Server 2013：发布更新的拓扑以添加存档数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5d6e409682aaafd6e48966fa47797b870f90b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="073ab-102">发布更新后的拓扑以在 Lync Server 2013 中添加存档数据库</span><span class="sxs-lookup"><span data-stu-id="073ab-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="073ab-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="073ab-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="073ab-104">在拓扑生成器中更新拓扑之后，必须先将拓扑发布到中央管理存储，然后才能配置和使用存档。</span><span class="sxs-lookup"><span data-stu-id="073ab-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="073ab-105">数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="073ab-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="073ab-106">发布更新后的拓扑</span><span class="sxs-lookup"><span data-stu-id="073ab-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="073ab-107">在运行 Lync Server 2013 的计算机上，或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组的成员（或具有等效用户权限的帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="073ab-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="073ab-108">您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要发布拓扑（将服务器添加到拓扑，则必须）。您必须使用属于<STRONG>Domain Admins</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且在您对 Lync server 2013 文件存储使用的文件共享上具有完全控制权限（即读取、写入和修改）（即，以便拓扑生成器可以配置所需的随机访问控制列表（dacl），或具有等效权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="073ab-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="073ab-109">使用拓扑生成器打开在上一节中创建的拓扑。</span><span class="sxs-lookup"><span data-stu-id="073ab-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="073ab-110">在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="073ab-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="073ab-111">在“发布拓扑”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="073ab-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="073ab-112">在“创建数据库”\*\*\*\* 页上，确认已经选择了数据库，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="073ab-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="073ab-113">如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。</span><span class="sxs-lookup"><span data-stu-id="073ab-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="073ab-114">有关所需的管理员权限和权限的详细信息，请参阅部署文档中的在<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中部署 SQL Server 的权限</A>。</span><span class="sxs-lookup"><span data-stu-id="073ab-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="073ab-115">只能使用拓扑生成器安装专用 SQL Server 服务器上的数据库。</span><span class="sxs-lookup"><span data-stu-id="073ab-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="073ab-116">与其他服务器组件并置的 SQL Server 服务器上的数据库必须通过在该计算机上运行本地安装程序来安装。</span><span class="sxs-lookup"><span data-stu-id="073ab-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="073ab-117">在“发布向导完成”\*\*\*\* 页上，确认已成功发布拓扑，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="073ab-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="073ab-118">发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="073ab-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="073ab-119">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中配置存档支持</A>。</span><span class="sxs-lookup"><span data-stu-id="073ab-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


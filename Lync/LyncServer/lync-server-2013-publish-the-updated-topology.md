---
title: Lync Server 2013：发布更新后的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f696b06f317ac20b98a14734f1eaf076105dbd8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512309"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="8dcd0-102">在 Lync Server 2013 中发布更新后的拓扑</span><span class="sxs-lookup"><span data-stu-id="8dcd0-102">Publish the updated topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dcd0-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8dcd0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8dcd0-104">在拓扑生成器中更新拓扑之后，您必须先将拓扑发布到中央管理存储，然后才能配置和使用持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="8dcd0-105">数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="8dcd0-106">发布更新后的拓扑</span><span class="sxs-lookup"><span data-stu-id="8dcd0-106">To publish an updated topology</span></span>

<span data-ttu-id="8dcd0-107">在发布拓扑之前，请安装持久聊天服务器的数据库。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="8dcd0-108">使用拓扑生成器，通过选择 " **操作** " 和 " **安装数据库**" 来安装数据库。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="8dcd0-109">在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上，使用属于 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组成员的帐户登录。并且具有完全控制权限 (该文件存储中的) 用于持久聊天服务器文件存储 (，以便拓扑生成器可以配置所需的任意自由访问控制列表 (dacl) # A5 或具有等效用户权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="8dcd0-110">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-110">Start Topology Builder.</span></span> <span data-ttu-id="8dcd0-111">选择“从现有部署下载拓扑”\*\*\*\* 或“从本地文件打开拓扑”\*\*\*\*（如果在本地保存它）。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="8dcd0-112">在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 " **发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="8dcd0-113">在“发布拓扑”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="8dcd0-114">在“发布向导完成”\*\*\*\* 页上，确认已成功发布拓扑，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8dcd0-115">发布拓扑后，您必须先配置持久聊天服务器的支持，然后才能存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="8dcd0-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：安装本地配置存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e16d4edfb53511712c58cb41510559fcf69cfa9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498569"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="aff19-102">在 Lync Server 2013 中安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="aff19-102">Install the Local Configuration store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff19-103">_**上次修改的主题：** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="aff19-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="aff19-104">在执行以下步骤之前，请确保您使用具有本地管理员和 RTCUniversalReadOnlyAdmin 组成员的域用户帐户登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="aff19-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="aff19-105">若要能够在 Lync Server 部署向导中执行任何操作，我们需要在服务器上存在本地配置存储。</span><span class="sxs-lookup"><span data-stu-id="aff19-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="aff19-106">本地配置存储是中央管理存储的只读副本，它是在本地安装 SQL Server Express 之后创建的。</span><span class="sxs-lookup"><span data-stu-id="aff19-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="aff19-107">中央管理存储本身将添加到安装在 Standard Edition Server 或基于 SQL Server Express 的数据库上的现有 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="aff19-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aff19-108">如果之前未在此服务器上运行 Lync Server 2013 安装程序，系统会提示你提供用于安装 Lync Server 2013 的驱动器和路径。</span><span class="sxs-lookup"><span data-stu-id="aff19-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="aff19-109">这将允许你安装到除系统驱动器之外的驱动器，如果你的组织需要，或者你有空间问题。</span><span class="sxs-lookup"><span data-stu-id="aff19-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="aff19-110">只需将 "安装程序" 对话框中的 Lync Server 文件的安装位置路径更改为新的可用驱动器即可。</span><span class="sxs-lookup"><span data-stu-id="aff19-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="aff19-111">如果将安装文件安装到此路径（包括 OCSCore.msi），则其余的 Lync Server 2013 文件也将部署到其中。</span><span class="sxs-lookup"><span data-stu-id="aff19-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="aff19-112">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="aff19-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="aff19-113">在安装媒体中，浏览到 \\ setup \\ amd64 \\Setup.exe，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aff19-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="aff19-114">如果系统提示您安装 Microsoft Visual c + + 2012 可再发行组件，请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="aff19-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="aff19-115">在“Lync Server 2013 安装位置”\*\*\*\* 页上，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aff19-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="aff19-116">在 " **最终用户许可协议** " 页上，查看许可条款，您需要选择 " **我接受许可协议中的条款**"，然后单击 **"确定"** 才能继续。</span><span class="sxs-lookup"><span data-stu-id="aff19-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="aff19-117">在“部署向导”页上，单击 **“安装或更新 Lync Server 系统”**。</span><span class="sxs-lookup"><span data-stu-id="aff19-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="aff19-118">在“Lync Server 2013”\*\*\*\* 页上，在“步骤 1: 安装本地配置存储”\*\*\*\* 旁边，单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aff19-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="aff19-119">在 " **安装本地配置存储** " 页上，确保选择了 " **直接从中央管理存储区检索** " 选项，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aff19-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="aff19-120">本地服务器配置安装完成后，应单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="aff19-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


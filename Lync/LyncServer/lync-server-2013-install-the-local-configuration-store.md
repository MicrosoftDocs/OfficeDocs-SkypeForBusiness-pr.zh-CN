---
title: Lync Server 2013：安装本地配置存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="1361f-102">在 Lync Server 2013 中安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="1361f-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1361f-103">_**主题上次修改时间:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="1361f-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="1361f-104">在执行以下步骤之前, 请确保你使用既是本地管理员又是 RTCUniversalReadOnlyAdmin 组成员的域用户帐户登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="1361f-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="1361f-105">为了能够使用 Lync Server 部署向导执行任何操作, 需要在服务器上存在本地配置存储。</span><span class="sxs-lookup"><span data-stu-id="1361f-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="1361f-106">本地配置存储是中央管理存储的只读副本, 它是在 SQL Server Express 的本地安装之后创建的。</span><span class="sxs-lookup"><span data-stu-id="1361f-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="1361f-107">将中央管理存储本身添加到安装在标准版服务器或基于 SQL Server Express 的数据库上的现有 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="1361f-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1361f-108">如果以前未在此服务器上运行 Lync Server 2013 设置, 系统将提示你提供安装 Lync Server 2013 的驱动器和路径。</span><span class="sxs-lookup"><span data-stu-id="1361f-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="1361f-109">这将允许你安装到除系统驱动器之外的驱动器, 如果你的组织需要, 或者你有空间问题。</span><span class="sxs-lookup"><span data-stu-id="1361f-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="1361f-110">您只需将 "设置" 对话框中的 Lync 服务器文件的安装位置路径更改为新的可用驱动器。</span><span class="sxs-lookup"><span data-stu-id="1361f-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="1361f-111">如果将安装文件安装到此路径 (包括 OCSCore), 则 Lync Server 2013 文件的其余部分也将部署到其中。</span><span class="sxs-lookup"><span data-stu-id="1361f-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="1361f-112">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="1361f-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="1361f-113">从安装媒体中, 浏览到\\"\\安装\\Amd64 Setup.exe", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1361f-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="1361f-114">如果系统提示您安装 Microsoft Visual c + + 2012 可再发行组件, 请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="1361f-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="1361f-115">在 " **Lync Server 2013 安装位置**" 页面上, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1361f-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="1361f-116">在 "**最终用户许可协议**" 页面上, 查看许可条款, 您需要选择 "**我接受许可协议中的条款**", 然后单击 **"确定"** 以继续。</span><span class="sxs-lookup"><span data-stu-id="1361f-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="1361f-117">在 "部署向导" 页面上, 单击 "**安装或更新 Lync Server 系统**"。</span><span class="sxs-lookup"><span data-stu-id="1361f-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="1361f-118">在 " **Lync Server 2013** " 页面上, 在 " **Step1: 安装本地配置存储**" 旁边, 单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="1361f-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="1361f-119">在“**安装本地配置存储**”页面上，确保选择“**直接从中央管理存储中检索**”选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1361f-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="1361f-120">本地服务器配置安装完成后, 应单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="1361f-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


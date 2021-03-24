---
title: 将文件存储数据移动到 Skype for Business Server 中的新文件存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 如果需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者需要进行其他更改，使当前文件存储不可用，则首先需要创建新共享。 然后，您需要执行以下步骤：
ms.openlocfilehash: a2870f024964a385852b7ecc781dbfb5647550b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093300"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="28236-104">将文件存储数据移动到 Skype for Business Server 中的新文件存储</span><span class="sxs-lookup"><span data-stu-id="28236-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="28236-105">如果需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者需要进行其他更改，使当前文件存储不可用，则首先需要创建新共享。</span><span class="sxs-lookup"><span data-stu-id="28236-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="28236-106">然后，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="28236-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="28236-107">关闭使用计划删除的文件存储的 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="28236-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="28236-108">在拓扑生成器中定义文件存储并发布更改，使新文件存储可供部署使用。</span><span class="sxs-lookup"><span data-stu-id="28236-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="28236-109">将数据移动到新文件存储。</span><span class="sxs-lookup"><span data-stu-id="28236-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="28236-110">重新启动服务器或服务。</span><span class="sxs-lookup"><span data-stu-id="28236-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="28236-111">（可选）删除旧文件共享和文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="28236-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="28236-112">将文件存储数据从一个文件存储移动到新文件存储</span><span class="sxs-lookup"><span data-stu-id="28236-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="28236-113">以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组（其中安装了 Skype for Business Server 管理工具）的成员登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="28236-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="28236-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="28236-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="28236-115">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="28236-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="28236-116">对于使用计划删除的文件存储的每个控制器池、控制器、Standard Edition Server 和前端池，选择服务器或池，单击"操作"，然后单击"停止 **所有服务"。**</span><span class="sxs-lookup"><span data-stu-id="28236-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="28236-117">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="28236-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="28236-118">启动拓扑生成器 **：单击"** 开始"，单击"**所有程序"，** 单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 拓扑生成器"。**</span><span class="sxs-lookup"><span data-stu-id="28236-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="28236-119">选择使用文件存储的服务器或池，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28236-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="28236-120">右键单击服务器或池，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="28236-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="28236-121">在 **"编辑属性"** 中的 **"关联"下的**"**文件存储"下**，单击"**新建"。**</span><span class="sxs-lookup"><span data-stu-id="28236-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="28236-122">在 **"定义新文件** 存储"中的"文件服务器 **FQDN"** 下，键入 (FQDN) 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="28236-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="28236-123">在 **"文件共享**"下，键入新文件共享的文件夹名称，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="28236-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="28236-124">此步骤定义用于拓扑生成器的新文件存储。</span><span class="sxs-lookup"><span data-stu-id="28236-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="28236-125">只定义一次，而不是为每个服务器定义一次。</span><span class="sxs-lookup"><span data-stu-id="28236-125">You define it only once, not for each server.</span></span> <span data-ttu-id="28236-126">在发布拓扑之前，您必须在定义的文件服务器上创建定义的文件存储。</span><span class="sxs-lookup"><span data-stu-id="28236-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="28236-127">有关详细信息，请参阅[Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14))。</span><span class="sxs-lookup"><span data-stu-id="28236-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="28236-128">对于使用文件存储的每个服务器或池，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28236-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="28236-129">右键单击服务器或池，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="28236-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="28236-130">在 **"编辑属性**"中的 **"关联"下的**"**文件** 存储"中，选择新的文件共享，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="28236-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="28236-131">发布拓扑，检查复制状态，然后根据需要运行 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="28236-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="28236-132">有关详细信息，请参阅[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))。</span><span class="sxs-lookup"><span data-stu-id="28236-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="28236-133">启动命令提示符：单击 **"开始"，** 单击 **"运行**"，然后键入cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="28236-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="28236-134">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="28236-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="28236-135">/S 开关复制文件、目录和子目录。</span><span class="sxs-lookup"><span data-stu-id="28236-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="28236-136">/XF 开关跳过名为 Meeting.Active 的所有文件。</span><span class="sxs-lookup"><span data-stu-id="28236-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="28236-137">带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。</span><span class="sxs-lookup"><span data-stu-id="28236-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="28236-138">对于 /LOG 开关，请使用目录路径日志文件名称，格式为 C:\Logfiles\log.txt。</span><span class="sxs-lookup"><span data-stu-id="28236-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="28236-139">此开关在日志文件位置创建一系列操作。</span><span class="sxs-lookup"><span data-stu-id="28236-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="28236-140">数据副本完成后，在 Lync Server 控制面板中，单击"拓扑 **"，** 然后单击"状态 **"。**</span><span class="sxs-lookup"><span data-stu-id="28236-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="28236-141">对于停止服务的每个服务器或池，选择服务器或池，单击"**操作**"，然后单击"**启动所有服务"。**</span><span class="sxs-lookup"><span data-stu-id="28236-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="28236-142">从拓扑中删除旧文件存储，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="28236-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="28236-143">有关详细信息，请参阅[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))。</span><span class="sxs-lookup"><span data-stu-id="28236-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="28236-144">（可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含您刚删除的文件存储的计算机，然后删除旧文件共享和目录。</span><span class="sxs-lookup"><span data-stu-id="28236-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="28236-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28236-145">See also</span></span>

<span data-ttu-id="28236-146">[将服务器重新分配给另一个文件存储](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="28236-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="28236-147">[删除文件存储](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="28236-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>
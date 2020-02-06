---
title: 将文件存储数据移动到 Skype for Business 服务器中的新文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 如果你需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者你需要进行其他更改以使当前文件存储不可用，你首先需要创建新的共享。 然后需要执行以下步骤：
ms.openlocfilehash: e1c4338e33e736c04dbb1a2a2e81a7233df65763
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817103"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="bad6b-104">将文件存储数据移动到 Skype for Business 服务器中的新文件存储</span><span class="sxs-lookup"><span data-stu-id="bad6b-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="bad6b-105">如果你需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者你需要进行其他更改以使当前文件存储不可用，你首先需要创建新的共享。</span><span class="sxs-lookup"><span data-stu-id="bad6b-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="bad6b-106">然后需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bad6b-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="bad6b-107">关闭使用您打算删除的文件存储的 Skype for Business 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="bad6b-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="bad6b-108">在拓扑生成器中定义文件存储并发布更改，使新文件存储可用于你的部署。</span><span class="sxs-lookup"><span data-stu-id="bad6b-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="bad6b-109">将数据移动到新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="bad6b-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="bad6b-110">重新启动服务器或服务。</span><span class="sxs-lookup"><span data-stu-id="bad6b-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="bad6b-111">（可选）删除旧的文件共享和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bad6b-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="bad6b-112">将文件存储数据从一个文件存储移动到新文件存储</span><span class="sxs-lookup"><span data-stu-id="bad6b-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="bad6b-113">以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组成员的身份登录到计算机，其中安装了 Skype for Business 服务器、管理工具。</span><span class="sxs-lookup"><span data-stu-id="bad6b-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2.  <span data-ttu-id="bad6b-114">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="bad6b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="bad6b-115">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="bad6b-116">对于每个使用你计划删除的文件存储的 Director 池、主管、标准版服务器和前端池，选择服务器或池，单击 "**操作**"，然后单击 "**停止所有服务**"。</span><span class="sxs-lookup"><span data-stu-id="bad6b-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="bad6b-117">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="bad6b-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="bad6b-118">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business**服务器**"，然后单击 " **skype for business 服务器拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="bad6b-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="bad6b-119">选择使用文件存储的服务器或池，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bad6b-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="bad6b-120">a.</span><span class="sxs-lookup"><span data-stu-id="bad6b-120">a.</span></span> <span data-ttu-id="bad6b-121">右键单击服务器或池，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="bad6b-122">b.</span><span class="sxs-lookup"><span data-stu-id="bad6b-122">b.</span></span> <span data-ttu-id="bad6b-123">在“**编辑属性**”中的“**关联**”下的“**文件存储**”下面，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="bad6b-124">c.</span><span class="sxs-lookup"><span data-stu-id="bad6b-124">c.</span></span> <span data-ttu-id="bad6b-125">在“**定义新文件存储**”中的“**文件服务器 FQDN**”下，键入文件服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="bad6b-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="bad6b-126">在“**文件共享**”下，键入新文件共享的文件夹名称，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bad6b-127">此步骤定义要在拓扑生成器中使用的新文件存储。</span><span class="sxs-lookup"><span data-stu-id="bad6b-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="bad6b-128">只需定义一次，无需针对每台服务器定义。</span><span class="sxs-lookup"><span data-stu-id="bad6b-128">You define it only once, not for each server.</span></span> <span data-ttu-id="bad6b-129">发布拓扑之前，必须在定义的文件服务器上创建定义的文件共享。</span><span class="sxs-lookup"><span data-stu-id="bad6b-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="bad6b-130">有关详细信息，请参阅[Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bad6b-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="bad6b-131">对于每个使用文件存储的服务器或池，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bad6b-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="bad6b-132">a.</span><span class="sxs-lookup"><span data-stu-id="bad6b-132">a.</span></span> <span data-ttu-id="bad6b-133">右键单击服务器或池，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="bad6b-134">b.</span><span class="sxs-lookup"><span data-stu-id="bad6b-134">b.</span></span> <span data-ttu-id="bad6b-135">在“**编辑属性**”中的“**关联**”下面的“**文件存储**”中，选择新的文件共享，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="bad6b-136">发布拓扑，检查复制状态，然后根据需要运行 Skype for Business 服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="bad6b-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="bad6b-137">有关详细信息，请参阅[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bad6b-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="bad6b-138">启动命令提示符：单击 "**开始**"，单击 "**运行**"，然后键入 cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="bad6b-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="bad6b-139">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bad6b-139">At the command line, type the following:</span></span>

     ```console
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="bad6b-140">/S 开关复制文件、目录和子目录。</span><span class="sxs-lookup"><span data-stu-id="bad6b-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="bad6b-141">/XF 开关跳过名为 Meeting.Active 的所有文件。</span><span class="sxs-lookup"><span data-stu-id="bad6b-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="bad6b-142">带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。</span><span class="sxs-lookup"><span data-stu-id="bad6b-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="bad6b-143">对于/LOG 开关，使用 C:\Logfiles\log.txt. 形式的目录路径和日志文件名</span><span class="sxs-lookup"><span data-stu-id="bad6b-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="bad6b-144">该开关可在指定位置创建操作的日志文件。</span><span class="sxs-lookup"><span data-stu-id="bad6b-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="bad6b-145">数据复制完成后，在 Lync Server 控制面板中单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="bad6b-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="bad6b-146">对于已停止服务的每个服务器或池，选择该服务器或池，单击“**操作**”，然后单击“**启动所有服务**”。</span><span class="sxs-lookup"><span data-stu-id="bad6b-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="bad6b-p111">从拓扑中删除旧文件存储，然后发布拓扑。有关详细信息，请参阅[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bad6b-p111">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="bad6b-149">（可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含你刚删除的文件存储的计算机，然后删除旧文件共享和目录。</span><span class="sxs-lookup"><span data-stu-id="bad6b-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="bad6b-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bad6b-150">See also</span></span>


[<span data-ttu-id="bad6b-151">将服务器重新分配到其他文件存储</span><span class="sxs-lookup"><span data-stu-id="bad6b-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="bad6b-152">删除文件存储</span><span class="sxs-lookup"><span data-stu-id="bad6b-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)


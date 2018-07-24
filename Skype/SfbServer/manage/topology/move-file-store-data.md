---
title: 移动文件存储数据移到新文件存储中的业务服务器 Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 如果您需要删除目前充当业务服务器部署中，您 Skype 的文件存储的文件服务器，或如果您需要进行其他更改，使当前文件存储不可用，首先需要创建新的共享。 然后需要执行以下步骤：
ms.openlocfilehash: a80e6b4e039f7423a3e622062b6bee237ee00947
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992306"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="c7dab-104">移动文件存储数据移到新文件存储中的业务服务器 Skype</span><span class="sxs-lookup"><span data-stu-id="c7dab-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>
 
<span data-ttu-id="c7dab-105">如果您需要删除目前充当业务服务器部署中，您 Skype 的文件存储的文件服务器，或如果您需要进行其他更改，使当前文件存储不可用，首先需要创建新的共享。</span><span class="sxs-lookup"><span data-stu-id="c7dab-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="c7dab-106">然后需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c7dab-106">Then you need to perform the following steps:</span></span>
  
1. <span data-ttu-id="c7dab-107">关闭使用计划删除的文件存储的业务 Server 服务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="c7dab-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>
    
2. <span data-ttu-id="c7dab-108">拓扑生成器中定义的文件存储，然后发布更改，以使新文件存储供您的部署。</span><span class="sxs-lookup"><span data-stu-id="c7dab-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>
    
3. <span data-ttu-id="c7dab-109">将数据移动到新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="c7dab-109">Move the data to the new file store.</span></span>
    
4. <span data-ttu-id="c7dab-110">重新启动服务器或服务。</span><span class="sxs-lookup"><span data-stu-id="c7dab-110">Restart the servers or services.</span></span>
    
5. <span data-ttu-id="c7dab-111">（可选）删除旧的文件共享和文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7dab-111">Optionally, remove the old file share and file folder.</span></span>
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="c7dab-112">将文件存储数据从一个文件存储移动到新文件存储</span><span class="sxs-lookup"><span data-stu-id="c7dab-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="c7dab-113">安装 Business Server，管理工具的 Skype 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组的成员身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="c7dab-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>
    
2.  <span data-ttu-id="c7dab-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c7dab-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c7dab-115">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span> 
    
4. <span data-ttu-id="c7dab-116">为每个控制器池、 控制器、 Standard Edition server 和使用计划删除的文件存储的前端池，选择服务器或池，单击**操作**，然后单击**停止所有服务**。</span><span class="sxs-lookup"><span data-stu-id="c7dab-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span> 
    
5. <span data-ttu-id="c7dab-117">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="c7dab-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
6. <span data-ttu-id="c7dab-118">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="c7dab-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
7. <span data-ttu-id="c7dab-119">选择使用文件存储的服务器或池，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7dab-119">Select a server or pool that uses the file store, and do the following:</span></span>
    
   <span data-ttu-id="c7dab-120">a.</span><span class="sxs-lookup"><span data-stu-id="c7dab-120">a.</span></span> <span data-ttu-id="c7dab-121">右键单击服务器或池，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-121">Right-click the server or pool, and then click **Edit Properties**.</span></span> 
    
   <span data-ttu-id="c7dab-122">b.</span><span class="sxs-lookup"><span data-stu-id="c7dab-122">b.</span></span> <span data-ttu-id="c7dab-123">在“**编辑属性**”中的“**关联**”下的“**文件存储**”下面，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>
    
   <span data-ttu-id="c7dab-124">c.</span><span class="sxs-lookup"><span data-stu-id="c7dab-124">c.</span></span> <span data-ttu-id="c7dab-125">在“**定义新文件存储**”中的“**文件服务器 FQDN**”下，键入文件服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c7dab-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="c7dab-126">在“**文件共享**”下，键入新文件共享的文件夹名称，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c7dab-127">此步骤在拓扑生成器中定义为使用新文件存储。</span><span class="sxs-lookup"><span data-stu-id="c7dab-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="c7dab-128">只需定义一次，无需针对每台服务器定义。</span><span class="sxs-lookup"><span data-stu-id="c7dab-128">You define it only once, not for each server.</span></span> <span data-ttu-id="c7dab-129">发布拓扑之前，必须在定义的文件服务器上创建定义的文件共享。</span><span class="sxs-lookup"><span data-stu-id="c7dab-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="c7dab-130">有关详细信息，请参阅[定义前端的文件存储区](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7dab-130">For details, see [Define the File Store for the Front End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span> 
  
8. <span data-ttu-id="c7dab-131">对于每个使用文件存储的服务器或池，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7dab-131">For each server or pool that uses the file store, do the following:</span></span>
    
   <span data-ttu-id="c7dab-132">a.</span><span class="sxs-lookup"><span data-stu-id="c7dab-132">a.</span></span> <span data-ttu-id="c7dab-133">右键单击服务器或池，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-133">Right-click the server or pool, and then click **Edit properties**.</span></span>
    
   <span data-ttu-id="c7dab-134">b.</span><span class="sxs-lookup"><span data-stu-id="c7dab-134">b.</span></span> <span data-ttu-id="c7dab-135">在“**编辑属性**”中的“**关联**”下面的“**文件存储**”中，选择新的文件共享，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>
    
9. <span data-ttu-id="c7dab-136">发布拓扑，检查复制状态，并根据需要业务 Server 部署向导运行 Skype。</span><span class="sxs-lookup"><span data-stu-id="c7dab-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="c7dab-137">有关详细信息，请参阅[Removing Lync Servers and 组件的常见过程](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7dab-137">For details, see [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>
    
10. <span data-ttu-id="c7dab-138">启动命令提示符： 单击**开始**，单击**运行**，然后键入 cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="c7dab-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>
    
11. <span data-ttu-id="c7dab-139">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="c7dab-139">At the command line, type the following:</span></span>
    
     ```
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="c7dab-140">/S 开关复制文件、目录和子目录。</span><span class="sxs-lookup"><span data-stu-id="c7dab-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="c7dab-141">/XF 开关跳过名为 Meeting.Active 的所有文件。</span><span class="sxs-lookup"><span data-stu-id="c7dab-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="c7dab-142">带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。</span><span class="sxs-lookup"><span data-stu-id="c7dab-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="c7dab-143">对于 /LOG 开关，使用 C:\Logfiles\log.txt 的窗体中的目录路径和日志文件名称。</span><span class="sxs-lookup"><span data-stu-id="c7dab-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="c7dab-144">该开关可在指定位置创建操作的日志文件。</span><span class="sxs-lookup"><span data-stu-id="c7dab-144">This switch creates a log file of operations at the named location.</span></span> 
  
12. <span data-ttu-id="c7dab-145">数据复制完成后，在 Lync Server Control Panel 后，单击**拓扑**，，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="c7dab-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>
    
13. <span data-ttu-id="c7dab-146">对于已停止服务的每个服务器或池，选择该服务器或池，单击“**操作**”，然后单击“**启动所有服务**”。</span><span class="sxs-lookup"><span data-stu-id="c7dab-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span> 
    
14. <span data-ttu-id="c7dab-147">从拓扑中删除旧文件存储，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c7dab-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="c7dab-148">有关详细信息，请参阅[删除文件存储](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7dab-148">For details, see [Remove a file store](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>
    
15. <span data-ttu-id="c7dab-149">（可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含你刚删除的文件存储的计算机，然后删除旧文件共享和目录。</span><span class="sxs-lookup"><span data-stu-id="c7dab-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c7dab-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7dab-150">See also</span></span>


[<span data-ttu-id="c7dab-151">重新分配到不同的文件存储的服务器</span><span class="sxs-lookup"><span data-stu-id="c7dab-151">Reassign a Server to a Different File Store</span></span>](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[<span data-ttu-id="c7dab-152">删除文件存储</span><span class="sxs-lookup"><span data-stu-id="c7dab-152">Remove a file store</span></span>](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)


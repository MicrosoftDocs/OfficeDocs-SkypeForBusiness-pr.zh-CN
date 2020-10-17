---
title: Lync Server 2013：为虚拟智能卡配置 Windows 8
description: Lync Server 2013：为虚拟智能卡配置 Windows 8。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542158"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="e947e-103">为在 Lync Server 2013 中使用虚拟智能卡配置 Windows 8</span><span class="sxs-lookup"><span data-stu-id="e947e-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e947e-104">_**上次修改的主题：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e947e-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e947e-105">部署双因素身份验证和智能卡技术时要考虑的一个因素是实施成本。</span><span class="sxs-lookup"><span data-stu-id="e947e-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e947e-106">Windows 8 提供了许多新的安全功能，最感兴趣的新功能之一是支持虚拟智能卡。</span><span class="sxs-lookup"><span data-stu-id="e947e-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e947e-107">对于装备了受信任的平台模块的计算机 (符合规范版本1.2 的 TPM) 芯片，组织现在可以获得智能卡登录的好处，而无需在硬件中进行任何额外的投资。</span><span class="sxs-lookup"><span data-stu-id="e947e-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e947e-108">有关详细信息，请参阅在上使用虚拟智能卡和 Windows 8 [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) 。</span><span class="sxs-lookup"><span data-stu-id="e947e-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e947e-109">为虚拟智能卡配置 Windows 8</span><span class="sxs-lookup"><span data-stu-id="e947e-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="e947e-110">使用启用了 Lync 的用户的凭据登录到 Windows 8 计算机。</span><span class="sxs-lookup"><span data-stu-id="e947e-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e947e-111">在 Windows 8 "开始" 屏幕上，将光标移到屏幕的右下角。</span><span class="sxs-lookup"><span data-stu-id="e947e-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="e947e-112">选择 " **搜索** " 选项，然后搜索 " **命令提示符**"。</span><span class="sxs-lookup"><span data-stu-id="e947e-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="e947e-113">右键单击 " **命令提示符**"，然后选择 " **以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="e947e-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="e947e-114">通过运行以下命令，打开受信任的平台模块 (TPM) 管理控制台：</span><span class="sxs-lookup"><span data-stu-id="e947e-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="e947e-115">在 TPM 管理控制台中，验证你的 TPM 规范版本是否至少为1。2</span><span class="sxs-lookup"><span data-stu-id="e947e-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e947e-116">如果您收到一个对话框，指示找不到兼容的信任平台模块 (TPM) ，请验证该计算机是否具有兼容的 TPM 模块以及是否已在系统 BIOS 中启用。</span><span class="sxs-lookup"><span data-stu-id="e947e-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="e947e-117">关闭 TPM 管理控制台</span><span class="sxs-lookup"><span data-stu-id="e947e-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="e947e-118">在命令提示符处，使用以下命令创建新的虚拟智能卡：</span><span class="sxs-lookup"><span data-stu-id="e947e-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e947e-119">若要在创建虚拟智能卡时提供自定义 PIN 值，请改用/pin prompt。</span><span class="sxs-lookup"><span data-stu-id="e947e-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="e947e-120">在命令提示符处，通过运行以下命令打开 "计算机管理" 控制台：</span><span class="sxs-lookup"><span data-stu-id="e947e-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="e947e-121">在 "计算机管理" 控制台中，选择 " **设备管理**"。</span><span class="sxs-lookup"><span data-stu-id="e947e-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e947e-122">展开 " **智能卡读取器**"。</span><span class="sxs-lookup"><span data-stu-id="e947e-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e947e-123">验证是否已成功创建新的虚拟智能卡读卡器。</span><span class="sxs-lookup"><span data-stu-id="e947e-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


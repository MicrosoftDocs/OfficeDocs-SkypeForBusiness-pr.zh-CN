---
title: 将 collocated 中介服务器转换为独立的中介服务器 (可选)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="ec313-102">将 collocated 中介服务器转换为独立的中介服务器 (可选)</span><span class="sxs-lookup"><span data-stu-id="ec313-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec313-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ec313-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ec313-104">使用以下过程将你的中介服务器 (collocated) 从你的标准版服务器或前端池切换到独立的中介服务器以进行单站点部署。</span><span class="sxs-lookup"><span data-stu-id="ec313-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="ec313-105">将 collocated 中介服务器转换为独立的中介服务器</span><span class="sxs-lookup"><span data-stu-id="ec313-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="ec313-106">从拓扑生成器打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="ec313-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="ec313-107">在左窗格中, 导航到 "**中介池**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="ec313-108">右键单击 "**中介池**", 然后选择 "**新建中介服务器**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="ec313-109">在 "**定义新的中介池**" 页面上, 提供新中介服务器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ec313-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="ec313-110">此外, 选择此池是单服务器池还是多服务器池, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="ec313-111">选择新中介服务器将向其路由入站呼叫的下一个跃点前端服务器池, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="ec313-112">选择要由中介服务器使用的边缘池, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="ec313-113">在 "**指定 PSTN 网关**" 页面上, 将以前的 PSTN 网关与中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="ec313-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="ec313-114">选择网关, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="ec313-115">单击 "**完成**" 以关闭 "**定义新的中介池**" 向导。</span><span class="sxs-lookup"><span data-stu-id="ec313-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="ec313-116">从**拓扑生成器**中, 选择顶级节点**Lync Server 2013**。</span><span class="sxs-lookup"><span data-stu-id="ec313-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="ec313-117">从 "**操作**" 窗格中, 选择 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="ec313-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="ec313-118">按照在 "部署" 文档中的[Lync server 2013 中安装中介服务器文件](lync-server-2013-install-the-files-for-mediation-server.md)中的步骤进行操作, 以在新的中介服务器上安装文件。</span><span class="sxs-lookup"><span data-stu-id="ec313-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="ec313-119">在中介服务器上安装文件后, 返回到拓扑生成器, 然后在左窗格中导航到该池。</span><span class="sxs-lookup"><span data-stu-id="ec313-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="ec313-120">右键单击该池, 然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="ec313-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="ec313-121">在 "**中介服务器**" 下, 清除 "**启用中介服务器 Collocated** " 复选框, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ec313-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="ec313-122">从**拓扑生成器**中, 选择顶级节点**Lync Server 2013**。</span><span class="sxs-lookup"><span data-stu-id="ec313-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="ec313-123">从 "**操作**" 菜单中, 选择 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="ec313-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


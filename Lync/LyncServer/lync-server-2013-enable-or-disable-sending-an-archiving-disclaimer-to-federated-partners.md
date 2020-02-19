---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bb71b00e01bff53d743122a1712660914ad01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="53cce-102">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="53cce-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53cce-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="53cce-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="53cce-p101">在部署边缘服务器并为组织启用联盟时，应该已经指定了是否自动向联盟伙伴发送存档免责声明。如果要对外部通信进行存档，应启用发送存档免责声明。使用本主题中的过程更改此配置。</span><span class="sxs-lookup"><span data-stu-id="53cce-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="53cce-107">以下过程假定您已为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="53cce-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="53cce-108">有关启用联合的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="53cce-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="53cce-109">启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="53cce-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="53cce-110">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="53cce-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="53cce-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="53cce-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53cce-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="53cce-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53cce-113">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“访问边缘配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53cce-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="53cce-114">在“访问边缘配置”\*\*\*\* 选项卡上，单击“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53cce-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="53cce-115">在“编辑访问边缘配置”\*\*\*\* 的“启用与联盟用户的通信”\*\*\*\* 下，选中或清除“向联盟伙伴发送存档免责声明”\*\*\*\* 复选框以启用或禁用自动发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="53cce-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="53cce-116">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53cce-116">Click **Commit**.</span></span>

<span data-ttu-id="53cce-117">若要使联合用户能够与 Lync Server 2013 部署中的用户进行协作，您还必须至少配置一个外部访问策略来支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="53cce-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="53cce-118">有关详细信息，请参阅部署文档或操作文档中的[MANAGE XMPP 联盟合作伙伴 In Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="53cce-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="53cce-119">有关控制对特定联盟域的访问权限的详细信息，请参阅部署文档或操作文档中的在[Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="53cce-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="53cce-120">使用 Windows PowerShell Cmdlet 启用或禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="53cce-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="53cce-121">可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="53cce-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="53cce-122">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="53cce-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="53cce-123">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="53cce-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="53cce-124">启用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="53cce-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="53cce-125">要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="53cce-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="53cce-126">禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="53cce-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="53cce-127">要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="53cce-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


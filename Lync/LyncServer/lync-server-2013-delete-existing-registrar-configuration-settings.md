---
title: Lync Server 2013：删除现有注册机构配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960d0dd055ccf2f380b1ebf8124432da8daf6563
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b6944-102">删除 Lync Server 2013 中的现有注册机构配置设置</span><span class="sxs-lookup"><span data-stu-id="b6944-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6944-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b6944-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b6944-104">请按照以下步骤删除注册机构。</span><span class="sxs-lookup"><span data-stu-id="b6944-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="b6944-105">删除现有注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="b6944-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="b6944-106">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b6944-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b6944-107">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b6944-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6944-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b6944-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6944-109">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“注册器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6944-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="b6944-110">在“注册器”\*\*\*\* 页上的搜索字段中，键入要删除的注册器的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="b6944-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="b6944-111">在列表中，单击所需的注册器，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6944-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="b6944-112">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="b6944-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b6944-113">使用 Windows PowerShell Cmdlet 删除注册机构配置设置</span><span class="sxs-lookup"><span data-stu-id="b6944-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b6944-114">你可以使用 Windows PowerShell 和**CsProxyConfiguration** Cmdlet 删除注册机构配置设置。</span><span class="sxs-lookup"><span data-stu-id="b6944-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="b6944-115">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6944-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b6944-116">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="b6944-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="b6944-117">删除一组特定的注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="b6944-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="b6944-118">以下命令会删除应用到边缘服务器 atl-edge-011.litwareinc.com 的注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="b6944-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="b6944-119">删除应用到站点范围的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="b6944-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="b6944-120">以下命令会删除应用到注册器服务的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="b6944-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="b6944-121">删除允许 NTLM 身份验证的所有注册器安全设置</span><span class="sxs-lookup"><span data-stu-id="b6944-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="b6944-122">以下命令会删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：</span><span class="sxs-lookup"><span data-stu-id="b6944-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="b6944-123">有关详细信息，请参阅[Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="b6944-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


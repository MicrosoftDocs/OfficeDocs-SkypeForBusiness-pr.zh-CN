---
title: 配置会议加入页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73cab2e4344054d1e95b77c1a64eda425d22654
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="3eeb1-102">配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="3eeb1-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eeb1-103">_**上次修改的主题：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="3eeb1-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="3eeb1-104">当用户单击会议请求中的会议链接时，"会议加入" 页将检测用户计算机上是否已安装 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="3eeb1-105">如果已经安装，则该客户端会打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="3eeb1-106">如果未安装客户端，则默认情况下将打开2013版本的 Microsoft Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="3eeb1-107">如果您希望允许用户加入使用 Office Communicator 2007 R2 或 Lync 2010 助理的会议，则可以修改会议加入页面的行为。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="3eeb1-108">这些配置选项已从 Lync Server 2013 控制面板中删除，但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="3eeb1-109">会议加入页面 CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="3eeb1-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eeb1-110">CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="3eeb1-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="3eeb1-111">Description</span><span class="sxs-lookup"><span data-stu-id="3eeb1-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eeb1-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="3eeb1-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="3eeb1-113">如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会通过使用 Office Communicator 2007 R2 加入会议。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="3eeb1-114">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eeb1-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="3eeb1-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="3eeb1-p104">设置为 True 时，用于加入联机会议的备用选项（如 Office Communicator 2007 R2）将自动展开并显示给用户。设置为 False（默认值）时，这些选项仍然可用，但用户必须自己操作才能显示选项列表。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="3eeb1-118">使用 Lync Server 2013 命令行管理程序配置会议加入页</span><span class="sxs-lookup"><span data-stu-id="3eeb1-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="3eeb1-119">启动 Lync Server 2013 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3eeb1-120">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3eeb1-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="3eeb1-121">此 cmdlet 将返回 Web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="3eeb1-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="3eeb1-122">运行以下命令，将参数设置为 True 或 False，具体取决于你的首选项（有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档）：</span><span class="sxs-lookup"><span data-stu-id="3eeb1-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>


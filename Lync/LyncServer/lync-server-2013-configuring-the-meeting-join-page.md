---
title: Lync Server 2013：配置会议加入页面
description: Lync Server 2013：配置会议加入页面。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e7c9dde0fdb6829da7bd11e16261a4bd76b7554
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564298"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="ac0ca-103">在 Lync Server 2013 中配置会议加入页</span><span class="sxs-lookup"><span data-stu-id="ac0ca-103">Configuring the meeting join page in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac0ca-104">_**上次修改的主题：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="ac0ca-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="ac0ca-105">当用户单击会议请求中的会议链接时，"会议加入" 页将检测用户计算机上是否已安装 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="ac0ca-106">如果已安装客户端，则将打开该客户端并加入会议。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="ac0ca-107">如果未安装客户端，则默认情况下会打开2013版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-107">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="ac0ca-108">如果您希望允许用户加入使用 Office Communicator 2007 R2 或 Lync 2010 助理的会议，则可以修改会议加入页面的行为。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-108">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="ac0ca-109">这些配置选项已从 Lync Server 2013 控制面板中删除，但你可以使用 Set-CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-109">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="ac0ca-110">与会页面 Set-CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="ac0ca-110">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac0ca-111">Set-CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="ac0ca-111">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="ac0ca-112">说明</span><span class="sxs-lookup"><span data-stu-id="ac0ca-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac0ca-113">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="ac0ca-113">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="ac0ca-114">如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会通过使用 Office Communicator 2007 R2 加入会议。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-114">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="ac0ca-115">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-115">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac0ca-116">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="ac0ca-116">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="ac0ca-p104">设置为 True 时，用于加入联机会议的备用选项（如 Office Communicator 2007 R2）将自动展开并显示给用户。设置为 False（默认值）时，这些选项仍然可用，但用户必须自己操作才能显示选项列表。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="ac0ca-119">使用 Lync Server 2013 命令行管理程序配置会议加入页</span><span class="sxs-lookup"><span data-stu-id="ac0ca-119">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="ac0ca-120">启动 Lync Server 2013 命令行管理程序：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="ac0ca-120">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ac0ca-121">若要查看 Web 服务配置设置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ac0ca-121">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="ac0ca-122">运行以下命令，将参数设置为 True 或 False，具体取决于您的首选项 (有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档) 中的 [CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) ：</span><span class="sxs-lookup"><span data-stu-id="ac0ca-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac0ca-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0ca-123">See Also</span></span>


[<span data-ttu-id="ac0ca-124">CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac0ca-124">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


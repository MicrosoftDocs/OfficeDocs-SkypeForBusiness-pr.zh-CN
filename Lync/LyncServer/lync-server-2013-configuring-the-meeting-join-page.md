---
title: Lync Server 2013：配置与会页面
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
ms.openlocfilehash: 8471b6b897a365763d55edcbd55e4a9bab4a3124
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="f8c45-102">在 Lync Server 2013 中配置与会页面</span><span class="sxs-lookup"><span data-stu-id="f8c45-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8c45-103">_**主题上次修改时间：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="f8c45-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="f8c45-104">当用户单击会议请求中的会议链接时，会议加入页面检测是否已在用户的计算机上安装了 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="f8c45-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="f8c45-105">如果已安装客户端，客户端将打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="f8c45-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="f8c45-106">如果未安装客户端，则默认情况下将打开2013版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="f8c45-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="f8c45-107">如果您希望允许用户通过 Office Communicator 2007 R2 或 Lync 2010 助理加入会议，则可以修改会议加入页面的行为。</span><span class="sxs-lookup"><span data-stu-id="f8c45-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="f8c45-108">这些配置选项已从 Lync Server 2013 控制面板中删除，但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="f8c45-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="f8c45-109">会议加入页面设置-CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="f8c45-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8c45-110">CsWebServiceConfiguration 参数</span><span class="sxs-lookup"><span data-stu-id="f8c45-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="f8c45-111">说明</span><span class="sxs-lookup"><span data-stu-id="f8c45-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8c45-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="f8c45-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="f8c45-113">如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会通过使用 Office Communicator 2007 R2 加入会议。</span><span class="sxs-lookup"><span data-stu-id="f8c45-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="f8c45-114">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="f8c45-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8c45-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="f8c45-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="f8c45-116">当设置为 True 时，用于加入联机会议的备用选项（如 Office Communicator 2007 R2）将自动展开并向用户显示。</span><span class="sxs-lookup"><span data-stu-id="f8c45-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="f8c45-117">当设置为 False （默认值）时，这些选项将可用，但用户将必须显示其自身的选项列表。</span><span class="sxs-lookup"><span data-stu-id="f8c45-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="f8c45-118">使用 Lync Server 2013 命令行管理程序配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="f8c45-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="f8c45-119">启动 Lync Server 2013 命令行管理程序：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="f8c45-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f8c45-120">若要查看 web 服务配置设置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f8c45-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="f8c45-121">运行以下命令，将参数设置为 True 或 False，具体取决于你的首选项（有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 管理外壳文档中的[Set CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) ）：</span><span class="sxs-lookup"><span data-stu-id="f8c45-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8c45-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8c45-122">See Also</span></span>


[<span data-ttu-id="f8c45-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8c45-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


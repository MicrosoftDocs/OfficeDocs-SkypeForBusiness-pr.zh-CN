---
title: Lync Server 2013：（可选）验证电话拨入式会议设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bff47410f46516061a5a3be64bce17476b453e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="08a13-102">Optional在 Lync Server 2013 中验证电话拨入式会议设置</span><span class="sxs-lookup"><span data-stu-id="08a13-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08a13-103">_**上次修改的主题：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="08a13-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="08a13-104">作为对电话拨入式会议配置的最终验证，可以搜索电话拨入式会议区域未被任何访问号码和未指定电话拨入式会议区域的访问号码使用的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="08a13-104">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="08a13-105">此为可选步骤。</span><span class="sxs-lookup"><span data-stu-id="08a13-105">This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="08a13-106">使用未被访问号码使用的电话拨入式会议区域查找拨号计划</span><span class="sxs-lookup"><span data-stu-id="08a13-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="08a13-107">以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="08a13-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="08a13-108">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08a13-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08a13-109">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="08a13-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="08a13-110">此 cmdlet 返回具有未被访问号码使用的电话拨入式会议区域的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="08a13-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="08a13-111">查找未分配区域的访问号码</span><span class="sxs-lookup"><span data-stu-id="08a13-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="08a13-112">以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="08a13-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="08a13-113">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08a13-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08a13-114">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="08a13-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="08a13-115">此 cmdlet 返回未与区域关联的所有电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="08a13-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


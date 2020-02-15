---
title: Lync Server 2013：修改现有的 Web 服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6d29868c6f4b18bd4bb02dac651a671684ecc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="40f14-102">在 Lync Server 2013 中修改现有的 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="40f14-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40f14-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40f14-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40f14-104">您可以使用 " **Web 服务**" 页来配置用于访问 Lync Server 2013 相关 web 服务器和 web 服务的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="40f14-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="40f14-105">按照以下步骤修改现有的 Web 服务策略。</span><span class="sxs-lookup"><span data-stu-id="40f14-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="40f14-106">修改现有的 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="40f14-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="40f14-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="40f14-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="40f14-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="40f14-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40f14-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="40f14-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40f14-110">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“Web 服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40f14-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="40f14-111">在“Web 服务”\*\*\*\* 页上，单击某个配置，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40f14-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="40f14-112">在“编辑 Web 服务设置”\*\*\*\* 的“集成 Windows 身份验证”\*\*\*\* 中，选择“协商”\*\*\*\*、“集成 Windows 身份验证”\*\*\*\* 或“无”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40f14-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="40f14-113">根据环境中的客户端功能和支持情况，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="40f14-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="40f14-114">**启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="40f14-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="40f14-115">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="40f14-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="40f14-116">**启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。</span><span class="sxs-lookup"><span data-stu-id="40f14-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="40f14-117">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40f14-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40f14-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40f14-118">See Also</span></span>


[<span data-ttu-id="40f14-119">在 Lync Server 2013 控制面板中配置身份验证</span><span class="sxs-lookup"><span data-stu-id="40f14-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：为控制器配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中为控制器配置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

<div>


> [!IMPORTANT]  
> 当你运行证书向导时，请确保你使用的帐户是已为你将使用的证书模板类型分配了相应权限的组的成员。 默认情况下，Lync Server 2013 证书请求将使用 Web 服务器证书模板。 如果您使用的帐户是 RTCUniversalServerAdmins 组的成员以使用此模板申请证书，请验证该组是否已分配使用该模板所需的注册权限。



</div>

每个控制器都需要默认证书、web 内部证书和 web 外部证书。 有关控制器的证书要求的详细信息，请参阅规划文档中[Lync Server 2013 内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

使用以下过程配置控制器证书。 对每个导演重复该过程。 此过程的步骤介绍了如何从组织部署的内部企业根证书颁发机构（CA）配置证书以及脱机请求处理。 有关从外部 CA 获取证书的详细信息，请与您的支持团队联系。

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>为 Director 或控制器池配置证书

1.  在 Lync Server 部署向导的 "**步骤3：请求、安装或分配证书**" 旁边，单击 "**运行**"。

2.  在“**证书向导**”页上，单击“**请求**”。

3.  在 "**证书请求**" 页面上，单击 "**下一步**"。

4.  在 "**延迟或立即请求**" 页面上，接受默认将**请求立即发送到联机证书颁发机构**选项，然后单击 "**下一步**"。

5.  在 "**选择证书颁发机构（CA）** " 页面上，单击要使用的内部 Windows 证书颁发机构，然后单击 "**下一步**"。

6.  在 "**证书颁发机构帐户**" 页面上，指定要使用的备用凭据（如果您登录的帐户没有足够的权限申请证书），然后单击 "**下一步**"。

7.  在 "**指定备用证书模板**" 页面上，单击 "**下一步**"。

8.  在 "**名称和安全设置**" 页面上，您可以指定一个**友好名称**，接受2048位密钥长度，然后单击 "**下一步**"。

9.  在 "**组织信息**" 页面上，选择 "指定组织信息"，然后单击 "**下一步**"。

10. 在 "**地理信息**" 页面上，选择 "指定地理信息"，然后单击 "**下一步**"。

11. 在 "**主题名称/主题备用名称**" 页面上，单击 "**下一步**"。
    
    <div>
    

    > [!NOTE]  
    > "主题备用名称" 列表应包含要在其上安装 Director 的计算机的名称（如果是单个控制器）或控制器池名称，以及为组织配置的简单 URL 名称。

    
    </div>

12. 在 "**主题备用名称（san）** " 页面上的 "SIP 域设置" 页面上，为希望 Director 控制其处理的所有域选择**已配置的 SIP 域**，然后单击 "**下一步**"。

13. 在 "**配置其他主题备用名称**" 页面上，添加任何其他所需的主题备用名称，然后单击 "**下一步**"。

14. 在 "**证书申请摘要**" 页面上，单击 "**下一步**"。

15. 在 "**执行命令**" 页面上，在命令完成运行后单击 "**下一步**"。

16. 在 "**联机证书请求状态**" 页面上，单击 "**完成**"。

17. 在 "**证书分配**" 页面上，单击 "**下一步**"。
    
    <div>
    

    > [!NOTE]  
    > 如果想要查看证书，请双击列表中的证书。

    
    </div>

18. 在 "**证书分配摘要**" 页面上，单击 "**下一步**"。

19. 在 "**执行命令**" 页面上，在命令完成运行后单击 "**完成**"。

20. 在 "**证书向导**" 页面上，单击 "**关闭**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


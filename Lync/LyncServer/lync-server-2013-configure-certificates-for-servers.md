---
title: Lync Server 2013：为服务器配置证书
description: Lync Server 2013：配置服务器的证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fab2f55f25ed3a289dd2d51b080374b3844029c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578108"
---
# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为服务器配置证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-17_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员或委派了相应权限的用户身份登录。 有关委派权限的详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。 根据组织和请求证书的要求，可能还需要其他组成员身份。 请咨询管理公钥基础结构 (PKI) 证书颁发机构 (CA) 的组。

<div>


> [!NOTE]  
> Lync Server 2013 支持 SHA-1 套件 (SHA-1 将摘要式哈希和签名算法的摘要长度（224、256、384或512）) 用于从运行 Windows 7、Windows Server 2008 R2、windows Server 2008、Windows Vista 或 Windows XP 操作系统的客户端连接，以及 Lync Phone Edition。 若要使用 SHA-1 套件支持外部访问，外部证书由公共 CA 颁发，也可以颁发具有相同位长度摘要的证书。



</div>

<div>


> [!WARNING]  
> 选择哪种散列摘要和签名算法取决于客户端和将使用证书的服务器，以及客户端和服务器与之通信的其他计算机和设备，这些计算机和设备还必须知道如何使用证书中使用的算法。 有关操作系统和一些客户端应用程序中支持的摘要长度的信息，请参阅 <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> 。



</div>

每个 Standard Edition server 或前端服务器最长需要四个证书： oAuthTokenIssuer 证书、默认证书、web 内部证书和 web 外部证书。 但是，可以使用相应的使用者可选名称条目和 oAuthTokenIssuer 证书请求和分配单个默认证书。 有关证书要求的详细信息，请参阅 [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。 有关请求、分配和安装 oAuthTokenIssuer 证书的详细信息，请参阅 [在 Lync server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

使用以下过程可请求、分配和安装 Standard Edition server 或前端服务器证书。 对每个前端服务器重复此过程。

<div>


> [!IMPORTANT]  
> 以下过程介绍如何从组织部署的内部企业 PKI 以及脱机请求处理配置证书。 有关从公用 CA 获取证书的信息，请参阅规划文档中的 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 中的内部服务器的证书要求</A> 。 此外，此过程还介绍了如何在设置前端服务器的过程中请求、分配和安装证书。 如果事先请求了证书，如本部署文档的 " <A href="lync-server-2013-request-certificates-in-advance-optional.md">提前请求证书" (可选) For Lync Server 2013</A> "一节中所述，或者您不使用组织中部署的内部企业 PKI 来获取证书，则必须根据需要修改此过程。



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>为前端服务器配置证书

1.  在 "Lync Server 部署向导" 中，单击 "**步骤3：请求、安装或分配证书"** 旁边的 "**运行**"。

2.  在 **“证书向导”** 页上，单击 **“请求”**。

3.  在 **“证书请求”** 页上，单击 **“下一步”**。

4.  在 "**延迟或即时请求**" 页上，可以通过单击 "**下一步**" 接受默认的 "**立即将请求发送到联机证书颁发机构"** 选项。 如果选择此选项，则必须提供具有自动联机注册的内部 CA。 如果你选择延迟请求的选项，系统会提示你输入名称和位置以保存证书请求文件。 证书请求必须由组织内部的 CA 或公用 CA 提供和处理。 然后，您需要导入证书响应，并将其分配给正确的证书角色。

5.  在 " **选择证书颁发机构 (CA) ** " 页上，选择 " **从在您的环境中检测到的列表中选择一个 CA** " 选项，然后从列表中的 Active DIRECTORY 域服务) CA 注册中选择一个已知的 (。 或者，选择 " **指定另一个证书颁发机构** " 选项，在框中输入另一个 CA 的名称，然后单击 " **下一步**"。

6.  在 " **证书颁发机构帐户** " 页上，系统会提示您提供凭据以请求和处理 CA 的证书请求。 您应该已确定是否需要用户名和密码才能提前请求证书。 你的 CA 管理员将拥有所需的信息，并且可能需要在此步骤中为你提供帮助。 如果需要提供备用凭据，请选中此复选框，在文本框中提供用户名和密码，然后单击 " **下一步**"。

7.  在 " **指定备用证书模板** " 页上，若要使用默认 Web 服务器模板，请单击 " **下一步**"。
    
    <div>
    

    > [!NOTE]  
    > 如果您的组织已创建用于替代默认 Web 服务器 CA 模板的模板，则选中 "" 复选框，然后输入备用模板的名称。 你将需要由 CA 管理员定义的模板名称。

    
    </div>

8.  在 " **名称和安全设置** " 页上，指定允许您标识证书和用途的 **友好名称** 。 如果将其保留为空，则会自动生成一个名称。 设置密钥的 **位长度** ，或接受默认值2048位。 如果您确定需要将证书和私钥移动或复制到其他系统，请选择 "将 **证书的私钥标记为可导出** "，然后单击 " **下一步**"。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 对可导出私钥的要求最低。 其中一种位置是位于池的边缘服务器上，媒体中继身份验证服务使用证书副本，而不是池中每个实例的单独证书。

    
    </div>

9.  在 " **组织信息** " 页上，选择提供组织信息，然后单击 " **下一步**"。

10. 在 " **地理信息** " 页上，选择提供地理位置信息，然后单击 " **下一步**"。

11. 在 " **使用者名称/主题替代名称** " 页上，查看将添加的 "使用者替代名称"，然后单击 " **下一步**"。

12. 在 " **SIP 域设置** " 页上，选择 **sip 域**，然后单击 " **下一步**"。

13. 在 " **配置附加主题备用名称** " 页上，添加任何其他所需的主题替代名称，包括将来其他 SIP 域可能需要的任何其他主题，然后单击 " **下一步**"。

14. 在 " **证书请求摘要** " 页上，查看摘要中的信息。 如果信息正确，请单击 " **下一步**"。 如果需要更正或修改设置，请单击 " **返回** 到正确的页面" 以进行更正或修改。

15. 在 **“执行命令”** 页上，单击 **“下一步”**。

16. 在 " **联机证书请求状态** " 页上，查看返回的信息。 应注意，已颁发证书并已将其安装到本地证书存储中。 如果报告为已颁发并已安装，但无效，请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。 有关如何检索受信任的根 CA 证书，请参阅 CA 文档。 如果需要查看检索到的证书，请单击 " **查看证书详细信息**"。 默认情况下，选中 " **将证书分配给 Lync Server 证书使用** 情况" 复选框。 如果要手动分配证书，请清除复选框，然后单击 " **完成**"。

17. 如果清除了 " **将证书分配给** 前一页上的 Lync Server 证书使用情况" 复选框，则会显示 " **证书分配** " 页。 单击“**下一步**”。

18. 在 " **证书存储** " 页上，选择所请求的证书。 如果要查看证书，请单击 " **查看证书详细信息**"，然后单击 " **下一步** " 继续。
    
    <div>
    

    > [!NOTE]  
    > 如果 " <STRONG>联机证书请求状态</STRONG> " 页报告了证书（如证书无效）的问题，则查看实际证书可帮助解决该问题。 可能导致证书无效的两个具体问题是前面提到的缺少受信任的根 CA 证书，以及与证书相关联的缺少私钥。 请参阅 CA 文档以解决这两个问题。

    
    </div>

19. 在 " **证书分配摘要** " 页上，查看显示的信息，以确保这是应分配的证书，然后单击 " **下一步**"。

20. 在 " **正在执行命令** " 页上，查看命令的输出。 如果要查看分配过程，或者如果发出错误或警告，请单击 " **查看日志** "。 完成审阅后，单击 " **完成**"。

21. 在 " **证书向导** " 页上，验证证书的 **状态** 是否为 "已分配"，然后单击 " **关闭**"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


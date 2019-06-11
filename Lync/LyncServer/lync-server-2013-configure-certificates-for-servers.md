---
title: Lync Server 2013：为服务器配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为服务器配置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-17_

若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录, 或者委派正确的权限。 有关委派权限的详细信息, 请参阅[Lync Server 2013 中的委派设置权限](lync-server-2013-delegate-setup-permissions.md)。 根据您的组织和申请证书的要求, 您可能需要其他组成员身份。 咨询管理公钥基础结构 (PKI) 证书颁发机构 (CA) 的组。

<div>


> [!NOTE]  
> Lync Server 2013 包括对 SHA-1 套件的支持 (SHA-2 对来自运行 Windows 7、Windows Server 512 R2、Windows Server 2008、windows Vista 的客户端的连接) 的摘要哈希和签名算法使用摘要式哈希和签名算法的摘要 384 256 224 长度Windows XP 操作系统, 除了 Lync Phone Edition。 要支持使用 SHA-2 套件进行外部访问，外部证书必须由公共 CA 颁发，公共 CA 也可颁发具有相同位长度摘要的证书。



</div>

<div>


> [!WARNING]  
> 选择哪种哈希摘要和签名算法取决于将使用证书的客户端和服务器，客户端和服务器将与其通信的其他计算机和设备也必须知道如何使用证书中所用的算法。 有关操作系统和某些客户端应用程序支持哪些摘要长度的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>。



</div>

每个标准版服务器或前端服务器最多需要四个证书: oAuthTokenIssuer 证书、默认证书、web 内部证书和 web 外部证书。 但是, 可以使用相应的主题可选名称条目以及 oAuthTokenIssuer 证书请求和分配单个默认证书。 有关证书要求的详细信息, 请参阅[Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。 有关请求、分配和安装 oAuthTokenIssuer 证书的详细信息, 请参阅[在 Lync server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

使用以下过程请求、分配和安装标准版服务器或前端服务器证书。 对每个前端服务器重复该过程。

<div>


> [!IMPORTANT]  
> 以下过程介绍了如何从由组织部署的内部企业 PKI 以及通过脱机请求处理来配置证书。 有关从公共 CA 获取证书的信息, 请参阅规划文档中<A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 内部服务器的证书要求</A>。 此外, 此过程还介绍了如何在设置前端服务器的过程中请求、分配和安装证书。 如果你提前申请证书, 如本部署文档的<A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 的 "提前申请证书 (可选)</A> " 部分中所述, 或者你不使用组织中部署的内部企业 PKI 获取证书, 则必须根据需要修改此过程。



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>配置前端服务器的证书

1.  在 Lync Server 部署向导中, 单击**步骤 3: "请求, 安装或分配证书"** 旁边的 "**运行**"。

2.  在“**证书向导**”页上，单击“**请求**”。

3.  在 "**证书请求**" 页面上, 单击 "**下一步**"。

4.  在“**延迟的请求或即时请求**”页上，可通过单击“**下一步**”接受默认的“**立即将请求发送给联机证书颁发机构**”选项。如果选择此选项，具有自动联机注册的内部 CA 必须可用。如果选择了延迟请求的选项，系统将提示您输入用于保存证书请求文件的名称和位置。证书请求必须由组织内部的 CA 或公共 CA 提出和处理。然后您需要导入证书响应并将其分配给适当的证书角色。

5.  在 "**选择证书颁发机构 (CA)** " 页面上, 选择 "**从你的环境中检测到的列表中选择一个 CA** " 选项, 然后从列表中选择一个已知 (通过注册 Active DIRECTORY 域服务) ca。 或者，选择“**指定其他证书颁发机构**”选项，在框中输入其他 CA 的名称，然后单击“**下一步**”。

6.  在“**证书颁发机构帐户**”页上，将提示您提供凭据，以在 CA 中请求证书和处理证书请求。 您应该已经确定提前请求证书是否需要用户名和密码。 您的 CA 管理员将拥有所需的信息, 并且可能需要在此步骤中为您提供帮助。 如果需要提供备用凭据，请选中相应的复选框，在文本框中输入用户名和密码，然后单击“**下一步**”。

7.  在“**指定替代证书模板**”页上，要使用默认的 Web 服务器模板，请单击“**下一步**”。
    
    <div>
    

    > [!NOTE]  
    > 如果组织已经创建了模板，以用作默认 Web 服务器 CA 模板的备用模板，请选中相应的复选框，然后输入备用模板的名称。您将需要 CA 管理员定义的模板名称。

    
    </div>

8.  在 "**名称和安全设置**" 页面上, 指定允许你标识证书和用途的**友好名称**。 如果将此处留空，则系统会自动生成一个名称。 设置密钥的“**位长度**”，或接受默认值 2048 位。 如果您确定需要将证书和私钥移动或复制到其他系统中，请选择“**将证书的私钥标记为可导出**”，然后单击“**下一步**”。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 对可导出私钥的要求很少。 其中一个可导出的位置是池中的边缘服务器，在这里媒体中继身份验证服务使用证书副本，而不是对池中的每个实例都分别使用单个证书。

    
    </div>

9.  在“**组织信息**”页上，可选择提供组织信息，然后单击“**下一步**”。

10. 在“**地理信息**”页上，可选择提供地理信息，然后单击“**下一步**”。

11. 在“**使用者名称/使用者替代名称**”页上，检查将添加的使用者替代名称，然后单击“**下一步**”。

12. 在“**SIP 域设置**”页上，选择“**SIP 域**”，然后单击“**下一步**”。

13. 在“**配置其他使用者替代名称**”页上，添加其他任何需要的使用者替代名称，包括将来其他 SIP 域可能需要的使用者替代名称，然后单击“**下一步**”。

14. 在“**证书请求摘要**”页上，检查摘要中的信息。如果信息正确，请单击“**下一步**”。如果需要更正或修改设置，请单击“**上一步**”返回相应的页面进行更正或修改。

15. 在“**正在执行命令**”页上，单击“**下一步**”。

16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. 如果报告为已颁发并已安装, 但无效, 请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。 Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. 默认情况下, 选中 "**将证书分配给 Lync Server 证书使用**情况" 复选框。 If you want to manually assign the certificate, clear the check box, and then click **Finish**.

17. 如果已清除 "**将证书分配给上一页的 Lync Server 证书使用**情况" 复选框, 则会显示 "**证书分配**" 页面。 Click **Next**.

18. 在“**证书存储**”页上，选择已请求的证书。如果要查看证书，请单击“**查看证书详细信息**”，然后单击“**下一步**”继续。
    
    <div>
    

    > [!NOTE]  
    > 如果 "<STRONG>联机证书请求状态</STRONG>" 页面报告了证书的问题 (例如证书无效), 查看实际证书可帮助解决问题。 可能导致证书无效的两个具体问题为：先前提到的受信任根 CA 证书缺失，与证书相关联的私钥缺失。 有关如何解决这两个问题的信息，请参阅 CA 文档。

    
    </div>

19. 在“**证书分配摘要**”页上，检查显示的信息以确保此证书是应分配的证书，然后单击“**下一步**”。

20. 在“**正在执行命令**”页上，检查命令的输出。如果要检查分配过程或查看是否出现错误或警告，请单击“**查看日志**”。检查完成后，单击“**完成**”。

21. 在 "**证书向导**" 页面上, 验证证书的**状态**是否为 "已分配", 然后单击 "**关闭**"。

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


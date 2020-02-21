---
title: Lync Server 2013：在运行 Microsoft Exchange Server 统一消息的服务器上配置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 515be9190f9c5012dfd75cdda6621b7f4acfd88f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>在运行 Microsoft Exchange Server 统一消息的服务器上配置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-26_

如果已部署 Exchange 统一消息（UM），如规划文档中的 "[在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 中所述，并且您希望向组织中的企业语音用户提供 exchange um 功能，则可以使用以下过程在运行 Exchange um 的服务器上配置证书。

<div>


> [!IMPORTANT]  
> 对于内部证书，运行 Lync Server 2013 的服务器和运行 Microsoft Exchange 的服务器都必须具有相互信任的受信任根证书颁发机构证书。 证书颁发机构（CA）可以是相同的，也可以是不同的证书颁发机构，前提是服务器在其受信任根证书颁发机构证书存储中注册了证书颁发机构的根证书。



</div>

必须使用服务器证书配置 Exchange 服务器才能连接到 Lync Server 2013：

1.  为 Exchange Server 下载 CA 证书。

2.  为 Exchange Server 安装 CA 证书。

3.  确保该 CA 在 Exchange Server 的受信任的根 CA 列表中。

4.  为 Exchange Server 创建证书请求并安装该证书。

5.  为 Exchange Server 分配证书。

<div>

## <a name="to-download-the-ca-certificate"></a>下载 CA 证书

1.  在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，键入**发证 CA\>服务器\</Certsrv 的 http://名称**，然后单击 **"确定"**。

2.  在 **“选择任务”** 下，单击 **“下载 CA 证书、证书链或 CRL”**。

3.  在 "**下载 Ca 证书、证书链或 CRL**" 下，选择 "**编码方法为基本 64**"，然后单击 "**下载 CA 证书**"。
    
    <div>
    

    > [!NOTE]  
    > 您还可以在此步骤中指定可分辨编码规则（DER）编码。 如果选择 DER 编码，则本过程的下一步中和<STRONG>“安装 CA 证书”</STRONG>的步骤 10 中的文件类型为 .p7b，而非 .cer。

    
    </div>

4.  在 **“文件下载”** 对话框中单击 **“保存”**，然后将文件保存到服务器上的硬盘中。（文件的扩展名将为 .cer 或 .p7b，具体取决于在上一步中选择的编码。）

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>安装 CA 证书

1.  在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，在 "**打开**" 框中键入**MMC** ，然后单击 **"确定"**，以打开 Microsoft 管理控制台（MMC）。

2.  在 **“文件”** 菜单上，单击 **“添加/删除管理单元”**，然后单击 **“添加”**。

3.  在 **“添加独立管理单元”** 框中，单击 **“证书”**，然后单击 **“添加”**。

4.  在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。

5.  在 "**选择计算机**" 对话框中，确认已选中 "**本地计算机：（运行此控制台的计算机）** " 复选框，然后单击 "**完成**"。

6.  单击 **“关闭”**，然后单击 **“确定”**。

7.  在控制台树中，展开 **“证书(本地计算机)”**，展开 **“受信任的根证书颁发机构”**，然后单击 **“证书”**。

8.  右键单击 **“证书”**，单击 **“全部任务”**，然后单击 **“导入”**。

9.  单击 **“下一步”**。

10. 单击 **“浏览”** 找到文件，然后单击 **“下一步”**。（文件的扩展名将为 .cer 或 .p7b，具体取决于在 **“下载 CA 证书”** 的步骤 3 中选择的编码。）

11. 单击 **“将所有证书放入下列存储区”**。

12. 单击 **“浏览”**，然后选择 **“受信任的根证书颁发机构”**。

13. 单击 **“下一步”** 以验证设置，然后单击 **“完成”**。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>确认该 CA 在受信任的根 CA 列表中

1.  在运行 Exchange UM 的服务器上，在 MMC 中展开 "**证书（本地计算机）**"，展开 "**受信任的根证书颁发机构**"，然后单击 "**证书**"。

2.  在详细信息窗格中，验证您的 CA 是否位于受信任的 CA 列表中。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>使用 Lync Server 配置 Exchange Server 2013 UM

1.  有关详细信息，请参阅 Exchange Server 文档中的 "将 Exchange 2013 UM 与 Lync Server [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)集成"。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>创建证书请求并在 Exchange Server 2007 (SP1) 中安装证书

1.  在运行 Exchange UM 的服务器上，依次单击 "**开始**" 和 "**运行**"，键入发证 CA 服务器**\>/certsrv**的**http://\<** 名称，然后单击 **"确定"**。

2.  在 **“选择任务”** 下，单击 **“请求证书”**。

3.  在 **“请求证书”** 下，单击 **“高级证书申请”**。

4.  在 **“高级证书申请”** 下，单击 **“创建并向此 CA 提交一个请求”**。

5.  在 **“高级证书申请”** 下，选择 **“Web 服务器”** 或为服务器身份验证配置的其他服务器证书模板。

6.  在 "**标识脱机模板的信息**" 下的 "**名称**" 框中，键入 Exchange 服务器的完全限定域名（FQDN）。
    
    <div>
    

    > [!NOTE]  
    > 必须输入 Exchange Server 的 FQDN 才能进行通信。

    
    </div>

7.  在 **“密钥选项”** 下单击 **“将证书保存在本地计算机证书存储中”** 复选框。

8.  单击网页底部的 **“提交”** 按钮。

9.  此时将打开一个要求确认的对话框，从中单击 **“是”**。

10. 在“证书已颁发”页上的 **“证书已颁发”** 下单击 **“安装此证书”**。

11. 此时将打开一个要求确认的对话框，从中单击 **“是”**。

12. 确认显示 "您的新证书已成功安装" 消息。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上创建证书

1.  使用适当的用户权限登录到运行 Exchange UM 的服务器。 有关详细信息，请参阅中的 "客户[https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)端访问权限"。

2.  请参阅以下过程来创建证书：
    
    1.  "在处创建新的 Exchange 证书"[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "导入 Exchange 证书"[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 对于证书<STRONG>主题名称</STRONG>，必须输入 Exchange SERVER 的 FQDN，才能使通信正常工作。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>在 Exchange Server 2007 （SP1）上分配证书

1.  在运行 Exchange UM 的服务器上，打开 "MMC"。

2.  在控制台树中，展开 "**个人**"，然后单击 "**证书**"。

3.  在 "详细信息" 窗格中，验证是否显示 "个人证书"。

4.  双击该证书以阅读其详细信息，并验证该证书是否有效。
    
    <div>
    

    > [!NOTE]  
    > 可能需要几分钟的时间才能将证书显示为有效。

    
    </div>

5.  重新启动 Microsoft Exchange 统一消息服务。
    
    <div>
    

    > [!NOTE]  
    > 运行 Exchange Server 2007 SP1 统一消息的服务器将自动检索正确的证书。

    
    </div>

6.  打开事件查看器并查找事件 ID 1112，它指定运行 Exchange Server 2007 SP1 统一消息的服务器已检索的证书。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上分配证书

1.  使用适当的用户权限登录到运行 Exchange UM 的服务器。 有关详细信息，请参阅中的 "客户[https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)端访问权限"。

2.  有关分配证书的过程，请参阅处[https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)的 "将服务分配给证书"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


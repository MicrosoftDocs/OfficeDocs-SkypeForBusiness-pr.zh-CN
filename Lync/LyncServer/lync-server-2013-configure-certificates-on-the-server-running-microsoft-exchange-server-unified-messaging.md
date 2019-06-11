---
title: 'Lync Server 2013: 在运行 Microsoft Exchange Server 统一消息的服务器上配置证书'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>在运行 Microsoft Exchange Server 统一消息的服务器上配置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-26_

如果已部署 Exchange 统一消息 (UM), 请参阅规划文档中[Lync Server 2013 中的 Exchange 统一消息集成规划](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)中所述, 并且你希望向企业语音用户提供 exchange UM 功能组织中, 你可以使用以下过程在运行 Exchange UM 的服务器上配置证书。

<div>


> [!IMPORTANT]  
> 对于内部证书, 运行 Lync Server 2013 和运行 Microsoft Exchange 的服务器的服务器必须具有相互信任的受信任根颁发机构证书。 证书颁发机构 (CA) 既可以是相同的, 也可以是不同的证书颁发机构, 前提是服务器在其受信任的根颁发机构证书存储中注册了证书颁发机构的根证书。



</div>

必须使用服务器证书配置 Exchange 服务器才能连接到 Lync Server 2013:

1.  下载 Exchange 服务器的 CA 证书。

2.  为 Exchange 服务器安装 CA 证书。

3.  验证 CA 是否位于 Exchange 服务器的受信任根 Ca 列表中。

4.  为 Exchange 服务器创建证书请求并安装证书。

5.  为 Exchange Server 分配证书。

<div>

## <a name="to-download-the-ca-certificate"></a>下载 CA 证书

1.  在运行 Exchange UM 的服务器上, 单击 "**开始**", 单击 "**运行**", 键入**发证 CA\>服务器\</Certsrv 的 http://名称**, 然后单击 **"确定"**。

2.  在 "**选择任务**" 下, 单击 "**下载 CA 证书、证书链或 CRL**"。

3.  在 "**下载 Ca 证书、证书链或 CRL**" 下, 选择 "**编码方法以基本 64**", 然后单击 "**下载 CA 证书**"。
    
    <div>
    

    > [!NOTE]  
    > 您还可以在此步骤中指定可分辨编码规则 (DER) 编码。 如果选择 "DER 编码", 此过程的下一步中和<STRONG>安装 CA 证书</STRONG>的步骤10中的文件类型是. p7b 而不是 .cer。

    
    </div>

4.  在 "**文件下载**" 对话框中, 单击 "**保存**", 然后将文件保存到服务器上的硬盘。 (该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于您在上一步中选择的编码。)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>安装 CA 证书

1.  在运行 Exchange UM 的服务器上, 依次单击 "**开始**" 和 "**运行**", 在 "**打开**" 框中键入**MMC** , 然后单击 **"确定"**, 打开 Microsoft 管理控制台 (MMC)。

2.  在 "**文件**" 菜单上, 单击 "**添加/删除管理单元**", 然后单击 "**添加**"。

3.  在 "**添加独立的管理单元**" 框中, 单击 "**证书**", 然后单击 "**添加**"。

4.  在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。

5.  在 "**选择计算机**" 对话框中, 验证 "**本地计算机: (运行此控制台的计算机)** " 复选框是否已选中, 然后单击 "**完成**"。

6.  单击 "**关闭**", 然后单击 **"确定"**。

7.  在控制台树中, 展开 "**证书 (本地计算机)**", 展开 "**受信任的根证书颁发机构**", 然后单击 "**证书**"。

8.  右键单击 "**证书**", 单击 "**所有任务**", 然后单击 "**导入**"。

9.  单击" **下一步**"。

10. 单击 "**浏览**" 找到文件, 然后单击 "**下一步**"。 (该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于**下载 CA 证书**的步骤3中所选的编码。

11. 单击 **"将所有证书放入下列存储"**。

12. 单击 "**浏览**", 然后选择 "**受信任的根证书颁发机构**"。

13. 单击 "**下一步**" 以验证设置, 然后单击 "**完成**"。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>验证 CA 是否位于受信任根 Ca 列表中

1.  在运行 Exchange UM 的服务器上, 在 MMC 中展开 "**证书 (本地计算机)**", 展开 "**受信任的根证书颁发机构**", 然后单击 "**证书**"。

2.  在 "详细信息" 窗格中, 验证您的 CA 是否在受信任的 Ca 列表中。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>将 Exchange Server 2013 UM 配置为 Lync Server

1.  有关详细信息, 请参阅 Exchange Server 文档中的 "将 Exchange 2013 UM 与 Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)相集成"。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>在 Exchange Server 2007 (SP1) 上创建证书请求并安装证书

1.  在运行 Exchange UM 的服务器上, 单击 "**开始**", 单击 "**运行**", 键入发证 CA 服务器**\>/certsrv**的**http://\<** 名称, 然后单击 **"确定"**。

2.  在 "**选择任务**" 下, 单击 "**申请证书**"。

3.  在 "**申请证书**" 下, 单击 "**高级证书申请**"。

4.  在 "**高级证书申请**" 下, 单击 "**创建并向此 CA 提交请求**"。

5.  在 "**高级证书申请**" 下, 选择 " **Web 服务器**" 或 "其他服务器证书" 模板配置为服务器身份验证。

6.  在 "**标识脱机模板的信息**" 下的 "**名称**" 框中, 键入 Exchange 服务器的完全限定的域名 (FQDN)。
    
    <div>
    

    > [!NOTE]  
    > 必须输入 Exchange Server 的 FQDN 才能使通信正常工作。

    
    </div>

7.  在 "**密钥选项**" 下, 单击 "**将证书保存在本地计算机证书存储中**" 复选框。

8.  单击网页底部的 "**提交**" 按钮。

9.  在打开要求确认的对话框中, 单击 **"是"**。

10. 在 "颁发的证书" 页面上的 "**颁发的证书**" 下, 单击 "**安装此证书**"。

11. 在打开要求确认的对话框中, 单击 **"是"**。

12. 验证是否显示 "已成功安装新证书" 消息。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上创建证书

1.  使用相应的用户权限登录到运行 Exchange UM 的服务器。 有关详细信息, 请参阅的[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"客户端访问权限"。

2.  请参阅以下过程来创建证书:
    
    1.  "创建新的 Exchange 证书"[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "导入 Exchange 证书"[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 对于证书<STRONG>使用者名称</STRONG>, 你必须输入 Exchange 服务器的 FQDN 才能使通信正常工作。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>在 Exchange Server 2007 (SP1) 上分配证书

1.  在运行 Exchange UM 的服务器上, 打开 "MMC"。

2.  在控制台树中, 展开 "**个人**", 然后单击 "**证书**"。

3.  在 "详细信息" 窗格中, 验证是否显示 "个人证书"。

4.  双击证书阅读其详细信息并验证其是否有效。
    
    <div>
    

    > [!NOTE]  
    > 在证书显示为有效之前, 可能需要几分钟的时间。

    
    </div>

5.  重新启动 Microsoft Exchange 统一消息服务。
    
    <div>
    

    > [!NOTE]  
    > 运行 Exchange Server 2007 SP1 统一消息的服务器将自动检索正确的证书。

    
    </div>

6.  打开事件查看器并查找事件 ID 1112, 用于指定运行 Exchange Server 2007 SP1 统一消息的服务器已检索的证书。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上分配证书

1.  使用相应的用户权限登录到运行 Exchange UM 的服务器。 有关详细信息, 请参阅的[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"客户端访问权限"。

2.  有关分配证书的过程, 请参阅 "将服务分配给证书" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


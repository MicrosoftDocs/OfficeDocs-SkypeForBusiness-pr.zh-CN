---
title: 在 Skype for Business Server 2015 中部署边缘服务器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要： 了解如何部署到您的业务服务器 2015年环境 Skype 的边缘服务器。
ms.openlocfilehash: ec69655ad5a614e9a2a22e82b7c1e56eed52102b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-servers-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署边缘服务器
 
**摘要：**了解如何部署到您的业务服务器 2015年环境 Skype 的边缘服务器。
  
以下各节包含旨在 Skype 业务服务器 2015年[计划业务服务器 2015年的 Skype 在边缘服务器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)文档已评审后遵循的步骤。 部署步骤如下：
  
- 网络接口
    
- 安装
    
- 证书
    
- 从边缘服务器
    
## <a name="network-interfaces"></a>网络接口

计划中所述，将既为配置网络接口的 DNS 于外围网络中承载边缘服务器，或没有 DNS 外围网络中。
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>使用外围网络中 DNS 服务器的接口配置

1. 为每个边缘服务器，内部接口的接口，其中一个，另一个用于面向外部的接口安装两个网络适配器。
    
    > [!NOTE]
    > 内部子网和外部子网不得相互路由。 
  
2. 在外部接口上，您将配置**一个**下面的：
    
   a. 在外部外围网络子网上配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。 配置适配器 DNS 设置以指向一对外围 DNS 服务器。
    
   b. 在外部外围网络子网上配置一个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。 配置适配器 DNS 设置以指向一对外围 DNS 服务器。 这种配置只是可接受的如果先前已配置拓扑中的端口分配，具有非标准值[创建边拓扑业务服务器 2015年的 Skype 的](create-your-edge-topology.md)文章中已经讨论过它。
    
3. 对内部的接口，内部外围网络子网中，配置一个静态 IP，并不能设置默认网关。 配置适配器 DNS 设置，以指向至少一台 DNS 服务器，但最好是一对外围 DNS 服务器。
    
4. 在 Skype 业务服务器 2015，和 Exchange 统一消息 (UM) 服务器的客户端所在的位置对所有内部网络的内部接口上创建永久的静态路由。
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>不使用外围网络中 DNS 服务器的接口配置

1. 为每个边缘服务器，内部接口的接口，其中一个，另一个用于面向外部的接口安装两个网络适配器。
    
    > [!NOTE]
    > 内部子网和外部子网不得相互路由。 
  
2. 在外部接口上，您将配置**一个**下面的：
    
   a. 在外部外围网络子网上配置三个静态 IP 地址。 您还需要在外部接口上配置默认网关等面向 internet 的路由器或防火墙外部定义的默认网关。 将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。
    
   b. 在外部外围网络子网上配置一个静态 IP 地址。 您还需要在外部接口上配置默认网关等面向 internet 的路由器或防火墙外部定义的默认网关。 将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。 这种配置只是可接受的如果先前已配置拓扑中的端口分配，具有非标准值[创建边拓扑业务服务器 2015年的 Skype 的](create-your-edge-topology.md)文章中已经讨论过它。
    
3. 对内部的接口，内部外围网络子网中，配置一个静态 IP，并不能设置默认网关。 另外将适配器 DNS 设置留空。
    
4. 在 Skype 业务服务器 2015，和 Exchange 统一消息 (UM) 服务器的客户端所在的位置对所有内部网络的内部接口上创建永久的静态路由。
    
5. 编辑主机文件，包含下一个跃点服务器的记录的每个边缘服务器或虚拟 IP (VIP)。 此记录将主管，标准版服务器或前端池配置拓扑生成器中的边缘服务器下一跃点地址。 如果您使用 DNS 负载平衡，包括下一跃点池中的每个成员一行。
    
## <a name="installation"></a>安装

若要成功完成以下步骤，将需要按照[业务服务器 2015年的 Skype 的边缘拓扑创建](create-your-edge-topology.md)文章中的步骤。
  
1. 登录到了边缘服务器角色中的本地管理员组的帐户已配置的服务器。
    
2. 您将需要在此机器上的边缘服务器拓扑文档末尾复制出来的拓扑配置文件。 访问保存该配置文件的外部介质（如 USB 驱动器或共享）。
    
3. 启动**部署向导**。
    
4. 一旦打开该向导，请单击**安装或更新 Skype 业务服务器系统**。
    
5. 本向导将执行检查以查看任何内容是否已经安装。 由于这是首次运行向导时，您需要从**第 1 步开始。安装本地配置存储。**
    
6. 将出现**配置本地副本的中央管理存储**对话框。 您需要单击**导入文件 （建议为边缘服务器） 中**。
    
7. 从这里，浏览到你先前导出拓扑的位置，选择 .zip 文件，然后单击“**打开**”，再单击“**下一步**”。
    
8. 部署向导将读取配置文件并将 XML 配置文件写入到本地计算机。
    
9. “**正在执行命令**”过程完成后，单击“**完成**”。
    
10. 在部署向导中，单击**第 2 步。安装或删除 Skype 业务服务器组件的**。 然后，向导将安装 Skype 业务服务器 2015年边缘被存储在本地计算机的 XML 配置文件中指定的组件。
    
11. 一旦完整的安装，您可以将其移动到下面的**证书**一节中的步骤操作。
    
## <a name="certificates"></a>证书

边缘证书规划文档中找不到边缘服务器的证书要求。 设置证书的步骤如下。
  
> [!NOTE]
> 当运行证书向导中，您需要以具有正确权限的证书模板的类型要使用的帐户身份登录。 默认情况下，将使用 Web 服务器证书模板 Skype 业务服务器证书请求。 如果您正在使用请求通过此模板的证书，请仔细检查，以确保组 RTCUniversalServerAdmins 组的成员帐户登录已分配要使用该模板的注册权限。 
  
### <a name="internal-edge-interface-certificates"></a>内部边缘接口证书

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1.下载或导出 CA 证书链

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;一。 使用 certsrv 网站下载

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 作为本地管理员组的成员登录 Skype 业务服务器 2015年的内部网络中的服务器。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;二。 **启动**和**运行**（或**搜索**和**运行**），打开，然后再键入以下命令：
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。 在颁发 CA certsrv 网页上，在**选择任务**单击**下载 CA 证书，证书链或 CRL**。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。 在“**下载 CA 证书、证书链或 CRL**”下，单击“**下载 CA 证书链**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v。 在“**文件下载**”框中，单击“**保存**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi。 在服务器上，将.p7b 文件保存到硬盘驱动器上，然后将其复制到每个边缘服务器上的文件夹。
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b。 使用 MMC 导出

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 你可以使用 MMC 从任何加入域的计算机导出 CA 根证书。 依次单击“**开始**”和“**运行**”，或者单击“**搜索**”后键入“**MMC**”打开。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;二。 在 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。 从“**添加或删除管理单元**”对话框列表中，选择“**证书**”，然后单击“**添加**”。 系统提示时，选择“**计算机帐户**”，然后选择“**下一步**”。 在“**选择计算机**”对话框中，选择“**本地计算机**”。 单击“**完成**”，然后单击“**确定**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。 展开“**证书(本地计算机)**”。 展开“**受信任的根证书颁发机构**”。 选择“**证书**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v。 单击由 CA 颁发的根证书。 右键单击该证书，选择菜单上的“**所有任务**”，然后选择“**导出**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi。 “**证书导出向导**”随即打开。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;七。 打开“**导出文件格式**”对话框，选择要导出到的格式。 我们的建议是“**加密消息语法标准 – PKCS #7 证书(P7b)**”。 如果这是您的选择也，切记，还选中**如果可能，包括证书路径中的所有证书**复选框，此操作还将导出证书链，其中包括根 CA 证书和所有中间证书。 单击" **下一步**"。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii。 在“**要导出的文件**”对话框的文件名输入框中，键入导出的证书的路径和文件名（默认扩展名为 .p7b）。 在您方便时，选择**浏览**按钮以转到要用于保存、 导出的证书的位置和名称导出的证书。 当您准备好时，请单击**保存**，然后**下一步**。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix。 查看操作摘要，然后单击“**完成**”完成证书的导出。 单击“**确定**”确认导出成功。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x。 将.p7b 文件复制到每个边缘服务器。
    
### <a name="2-import-the-ca-certification-chain"></a>2.导入 CA 证书链

&nbsp;&nbsp;&nbsp;一。 在每个边缘服务器上，打开 MMC （选择**启动**和**运行**，或**搜索**，并键入要打开的**MMC** ）。
    
&nbsp;&nbsp;&nbsp;b。 在“**文件**”菜单上，单击“**添加/删除管理单元**”，然后选择“**添加**”。
    
&nbsp;&nbsp;&nbsp;c。 在“**添加或删除管理单元**”框中，单击“**证书**”，然后单击“**添加**”。
    
&nbsp;&nbsp;&nbsp;d。 在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**选择计算机**”对话框中，确保选中“**本地计算机: (运行此控制台的计算机)**”复选框，然后单击“**完成**”。
    
&nbsp;&nbsp;&nbsp;f。 单击“**关闭**”，然后单击“**确定**”。
    
&nbsp;&nbsp;&nbsp;g。 在控制台树中，展开“**证书(本地计算机)**”，右键单击“**受信任的根证书颁发机构**”，转到“**所有任务**”，然后单击“**导入**”。
    
&nbsp;&nbsp;&nbsp;h。 在出现的向导中，在“**要导入的文件**”文本框中，指定证书的文件名（在上一节中你赋予 .p7b 文件的名称）。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;我。 应选中“**将所有的证书放入下列存储，作为受信任的根证书颁发机构**”单选按钮。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;j。 查看摘要，然后单击“**完成**”以完成导入。
    
&nbsp;&nbsp;&nbsp;k。 这将需要为您要部署的每个边缘服务器来完成。
    
### <a name="3-create-the-certificate-request"></a>3.创建的证书申请

&nbsp;&nbsp;&nbsp;一。 登录到您的某个边缘服务器，启动部署向导，然后在**第 3 步： 请求、 安装或分配证书**，单击**运行**（或**再次运行**，如果已运行过此向导）。
    
&nbsp;&nbsp;&nbsp;b。 在“**证书请求**”页上，确保“**内部边缘证书**”已选中，然后单击“**请求**”。
    
&nbsp;&nbsp;&nbsp;c。 在“**延迟的请求或即时请求**”页上，如果你有权从边缘环境访问联机证书颁发机构，请选择“**立即将请求发送至联机证书颁发机构**”，否则选择“**现在准备请求，但稍后发送**”。
    
&nbsp;&nbsp;&nbsp;d。 在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的其他模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。 否则，什么也不做。
    
&nbsp;&nbsp;&nbsp;f。 在“名称和安全设置”页上，执行以下操作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 在“**友好名称**”中，输入证书的显示名称（例如，内部边缘）。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;二。 在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。 如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。 单击" **下一步**"。
    
&nbsp;&nbsp;&nbsp;g。 在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。 可以输入分部或部门（如 IT）。
    
&nbsp;&nbsp;&nbsp;h。 在“**地理信息**”页上，输入位置信息。
    
&nbsp;&nbsp;&nbsp;我。 在“**使用者名称/使用者替代名称**”页上，这应该由向导自动填充。
    
&nbsp;&nbsp;&nbsp;j。 在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。
    
&nbsp;&nbsp;&nbsp;k。 在**请求摘要**页上，查看将要用于生成您的请求的证书信息。 如果需要进行更改，现在就返回并执行更改。
    
&nbsp;&nbsp;&nbsp;l。 然后单击**下一步**生成 CSR 文件您需要提供给 CA （您可以单击**查看日志**以查看证书申请日志）。
    
&nbsp;&nbsp;&nbsp;米。 生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。 CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。
    

### <a name="4-import-the-certificate"></a>4.导入证书

&nbsp;&nbsp;&nbsp;一。 登录，为本地的管理员组的成员，至边缘服务器做从您的证书申请在最后一个过程中。
    
&nbsp;&nbsp;&nbsp;b。 在部署向导旁边**第 3 步。安装或分配证书请求**，**运行再次**单击。
    
&nbsp;&nbsp;&nbsp;c。 在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。
    
&nbsp;&nbsp;&nbsp;d。 在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。
    
&nbsp;&nbsp;&nbsp;电子。 如果边缘池，其他成员正在导入的证书和证书包含私钥，请务必选择**包含证书的专用密钥的证书文件**复选框，并指定密码。 单击“**下一步**”继续。
    
&nbsp;&nbsp;&nbsp;f。 在**摘要**页上，单击**下一步**，一旦成功导入证书后，已经确认的信息，并**完成**。
    
 
### <a name="5-export-the-certificate"></a>5.导出证书

&nbsp;&nbsp;&nbsp;一。 请确保您已登录到边缘服务器导入到证书以前，为本地的管理员组的成员。
    
&nbsp;&nbsp;&nbsp;b。 单击**开始****运行**（或打开**搜索**），然后键入**MMC**。
    
&nbsp;&nbsp;&nbsp;c。 从 MMC 控制台中，单击“**文件**”，再单击“**添加/删除管理单元**”。
    
&nbsp;&nbsp;&nbsp;d。 从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**证书**”管理单元对话框中，选择“**计算机帐户**”。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;f。 在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。 单击“**完成**”。 单击“**确定**”，MMC 控制台的配置即告完成。
    
&nbsp;&nbsp;&nbsp;g。 双击“**证书(本地计算机)**”展开证书存储。 双击“**个人**”，然后单击“**证书**”。
    
  > [!NOTE]
  > 在这里，您可能会和看不到在个人证书存储本地计算机的任何证书。 您不需要查寻，如果键不存在，导入证书没有与它相关联的私钥。 请重试请求和导入一次，上面的步骤，如果您确信您的所有答对，谈到 CA 管理员或提供程序。 
  
&nbsp;&nbsp;&nbsp;h。 在**个人证书存储区**的本地计算机，右键单击要导出的证书。 从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。
    
&nbsp;&nbsp;&nbsp;我。 在“**证书导出向导**”中，单击“**下一步**”。 选择“**是，导出私钥**”。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;j。 在“**导出文件格式**”对话框中，选择“**个人信息交换 - PKCS#12 (.PFX)**”，然后选择以下选项：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 如果可能，则数据包括证书路径中的所有证书。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;二。 导出所有扩展属性。
    
   > [!NOTE]
   > **切勿**选择“**如果导出成功，删除私钥**”。 这将意味着必须重新导入证书和私钥恢复到此边缘服务器。
  
&nbsp;&nbsp;&nbsp;k。 如果要分配密码来保护私钥，可以键入私钥的密码。 重新输入该密码进行确认，然后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;l。 为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。 既需要可由池中的其他边缘服务器路径或您需要将文件移动通过外部媒体 （如 USB 驱动器）。 当您完成您的选择时，请单击**下一步**。
    
&nbsp;&nbsp;&nbsp;米。 查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。
    
&nbsp;&nbsp;&nbsp;n。 在成功导出对话框中单击“**确定**”。
    
 
### <a name="6-assign-the-certificate"></a>6.将证书分配

&nbsp;&nbsp;&nbsp;一。 在每个边缘服务器，请在部署向导，旁边**第 3 步。安装或分配证书请求**，单击**重新运行**。
    
&nbsp;&nbsp;&nbsp;b。 在“**可用的证书任务**”页上，单击“**分配现有证书**”。
    
&nbsp;&nbsp;&nbsp;c。 在“**证书分配**”页上，选择列表中的“**边缘内部**”。
    
&nbsp;&nbsp;&nbsp;d。 在**证书存储**页上，选择您已经导入 （从上一节） 内部边缘证书。
    
&nbsp;&nbsp;&nbsp;电子。 在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。
    
&nbsp;&nbsp;&nbsp;f。 在向导完成页上，单击“**完成**”。
    
&nbsp;&nbsp;&nbsp;g。 当您完成此过程时，它是非常好的方法来打开每个边缘服务器上的证书 MMC 管理单元、 扩展**证书 （本地计算机）**、 展开**个人**，单击**证书**和确认内部边缘在详细信息窗格中列出了证书。
    
### <a name="external-edge-interface-certificates"></a>外部边缘接口证书

 
### <a name="1-create-the-certificate-request"></a>1.创建的证书申请

&nbsp;&nbsp;&nbsp;一。 登录到您的某个边缘服务器，启动部署向导，然后在**第 3 步： 请求、 安装或分配的证书，单击运行**（或**再次运行**，如果已运行过此向导）。
    
&nbsp;&nbsp;&nbsp;b。 在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。
    
&nbsp;&nbsp;&nbsp;c。 在“**证书请求**”页上，确保“**外部边缘证书**”已选中，然后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;d。 在“**延迟的请求或即时请求**”页上，单击“**现在准备请求，但稍后发送**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;f。 在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。
    
&nbsp;&nbsp;&nbsp;g。 在“名称和安全设置”页上，执行以下操作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 在“**友好名称**”中，键入证书的显示名称（例如，外部边缘）。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;二。 在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。 如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。 单击" **下一步**"。
    
&nbsp;&nbsp;&nbsp;h。 在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。 可以输入分部或部门（如 IT）。
    
&nbsp;&nbsp;&nbsp;我。 在“**地理信息**”页上，输入位置信息。
    
&nbsp;&nbsp;&nbsp;j。 在“**使用者名称/使用者替代名称**”页上，所需的信息由向导自动填充。
    
&nbsp;&nbsp;&nbsp;k。 在**主题备用名称 (San) 上的 SIP 域设置**页中，选中添加 sip 域复选框。<sipdomain> 主题备用名称列表的条目。
    
&nbsp;&nbsp;&nbsp;l。 在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。
    
&nbsp;&nbsp;&nbsp;米。 在**请求摘要**页上，查看将要用于生成您的请求的证书信息。 如果需要进行更改，现在就返回并执行更改。
    
&nbsp;&nbsp;&nbsp;n。 准备就绪之后，请单击**下一步**生成 CSR 文件您需要提供给 CA （您可以单击**查看日志**以查看证书申请日志）。
    
&nbsp;&nbsp;&nbsp;o。 生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。 CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。
    
&nbsp;&nbsp;&nbsp;p。 （可选）在提交 CSR 的内容后，可能需要你提供某些信息，具体如下（CA 之间差异很大，所有这可能不是必需的）：
    
  - **Microsoft** 作为服务器平台
    
  - **IIS** 作为版本
    
  - **Web Server** 作为使用类型
    
  - **PKCS7** 作为响应格式
    
 
### <a name="2-import-the-certificate"></a>2.导入证书

&nbsp;&nbsp;&nbsp;一。 登录，为本地的管理员组的成员，至边缘服务器做从您的证书申请在最后一个过程中。
    
&nbsp;&nbsp;&nbsp;b。 在部署向导旁边**第 3 步。安装或分配证书请求**，**运行再次**单击。
    
&nbsp;&nbsp;&nbsp;c。 在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。
    
&nbsp;&nbsp;&nbsp;d。 在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。 如果您的证书包含私钥，请务必选择**证书文件包含证书的私钥**，并输入私有密钥的密码。 完成后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**导入证书摘要**”页上，查看摘要信息，然后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;f。 在**执行命令**页中，您可以查看导入的结果完成后，单击**查看日志**。 单击“**完成**”完成证书导入。
    
&nbsp;&nbsp;&nbsp;g。 如果池中有其他边缘服务器，您将需要按照下面两个步骤。 如果这是一个独立的边缘服务器，在使用完外部证书。
    
 
### <a name="3-export-the-certificate"></a>3.导出证书

&nbsp;&nbsp;&nbsp;一。 请确保您已登录到边缘服务器导入到以本地管理员身份的证书。
    
&nbsp;&nbsp;&nbsp;b。 单击**开始****运行**（或打开**搜索**），然后键入**MMC**。
    
&nbsp;&nbsp;&nbsp;c。 从 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。
    
&nbsp;&nbsp;&nbsp;d。 从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。
    
&nbsp;&nbsp;&nbsp;电子。 在“**证书**”管理单元对话框中，选择“**计算机帐户**”。 单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;f。 在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。 单击“**完成**”。 单击“**确定**”，MMC 控制台的配置即告完成。
    
&nbsp;&nbsp;&nbsp;g。 双击“**证书(本地计算机)**”展开证书存储。 双击“**个人**”，然后单击“**证书**”。
    
    > [!NOTE]
    > You may be here, and you don't see any certificates in the Certificates Personal store for the local computer. You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it. Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider. 
  
&nbsp;&nbsp;&nbsp;h。 在**个人证书存储区**的本地计算机，右键单击要导出的证书。 从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。
    
&nbsp;&nbsp;&nbsp;我。 在“**证书导出向导**”中，单击“**下一步**”。 选择“**是，导出私钥**”。 单击“**下一步**”。
    
    > [!NOTE]
    > If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it. You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.
  
&nbsp;&nbsp;&nbsp;j。 在“导出文件格式”对话框中，选择“个人信息交换 - PKCS#12 (.PFX)”，然后选择以下选项：
    
 &nbsp;&nbsp;&nbsp;我。 如果可能，则数据包括证书路径中的所有证书。
    
 &nbsp;&nbsp;&nbsp;二。 导出所有扩展属性。
    
    > [!NOTE]
    > **NEVER** select **Delete the private key if the export is successful**. It'll mean you have to reimport the certificate and private key back to this Edge Server.
  
&nbsp;&nbsp;&nbsp;k。 如果要分配密码来保护私钥，可以键入私钥的密码。 重新输入该密码进行确认，然后单击“**下一步**”。
    
&nbsp;&nbsp;&nbsp;l。 为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。 既需要可由池中的其他边缘服务器路径或您需要将文件移动通过外部媒体 （如 USB 驱动器）。 当您完成您的选择时，请单击**下一步**。
    
&nbsp;&nbsp;&nbsp;米。 查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。
    
&nbsp;&nbsp;&nbsp;n。 在成功导出对话框中单击“**确定**”。
    
&nbsp;&nbsp;&nbsp;o。 现在需要返回导入到在这之前的证书部分并将证书导入所有剩余边缘服务器，然后继续进行分配，下面。
    
 
### <a name="4-assign-the-certificate"></a>4.将证书分配

&nbsp;&nbsp;&nbsp;一。 **每**边在服务器上，部署向导，旁边**步骤 3 中。安装或分配证书请求**，单击**重新运行**。
    
&nbsp;&nbsp;&nbsp;b。 在“**可用的证书任务**”页上，单击“**分配现有证书**”。
    
&nbsp;&nbsp;&nbsp;c。 在**证书分配**页中，选择列表中的**外部边缘**。
    
&nbsp;&nbsp;&nbsp;d。 在**证书存储**页上，选择您已经导入的外部边缘 （从上一节） 的证书。
    
&nbsp;&nbsp;&nbsp;电子。 在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。
    
&nbsp;&nbsp;&nbsp;f。 在向导完成页上，单击“**完成**”。
    
&nbsp;&nbsp;&nbsp;g。 当您完成此过程时，它是非常好的方法来打开证书 MMC 管理单元中每台服务器上、 展开**证书 （本地计算机）**、 展开**个人**，单击**证书**和确认内部边缘在详细信息窗格中列出了证书。
    
   > [!NOTE]
    > 你还需要设置反向代理服务器的证书。 介绍设置反向代理服务器为 Skype 业务服务器 2015年主题。 
  
## <a name="starting-the-edge-servers"></a>从边缘服务器

安装完成后，您将需要在您的部署中的每个边缘服务器上启动服务：
  
1. 在每个边缘服务器上，在**部署向导**下一步**步骤 4： 启动服务**，单击**运行**。
    
2. 在**开始的 Skype 业务服务器服务**页上，查看列表中的服务，，然后单击**下一步**启动服务。
    
3. 启动服务后，可以单击“**完成**”关闭向导。
    
4. （可选）仍然在“**步骤 4: 启动服务**”下，单击“**服务状态**”。
    
5.  在每台服务器上的**服务 MMC** ，请验证所有 Skype 业务服务器 2015年服务正在运行。
    


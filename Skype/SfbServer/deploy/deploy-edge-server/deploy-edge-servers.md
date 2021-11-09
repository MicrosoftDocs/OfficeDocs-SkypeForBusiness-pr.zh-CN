---
title: 在部署中部署Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要：了解如何将边缘服务器部署到Skype for Business Server环境中。
ms.openlocfilehash: 30beb7b42b2f77e82d83768d918102cbaa0f7f5e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852726"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>在部署中部署Skype for Business Server
 
**摘要：** 了解如何将边缘服务器部署到Skype for Business Server环境中。
  
以下各节包含一些步骤，这些步骤在查看 Skype for Business Server 中的"规划边缘[服务器](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)Skype for Business Server之后执行。 部署步骤如下：
  
- 网络接口
    
- 安装
    
- 证书
    
- 启动边缘服务器
    
## <a name="network-interfaces"></a>网络接口

如规划中说明，您将在承载边缘服务器的外围网络中配置具有 DNS 的网络接口，或在外围网络中没有 DNS。
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>外围网络中具有 DNS 服务器的接口配置

1. 为每台边缘服务器安装两个网络适配器，一个适用于面向内部的接口，另一个适用于面向外部的接口。
    
    > [!NOTE]
    > 内部子网和外部子网不得相互路由。 
  
2. 在外部接口上，将配置 **以下项** 之一：
    
   a. 外部外围网络子网上的三个静态 IP 地址，将默认网关指向外部防火墙的内部接口。 配置适配器 DNS 设置以指向一对外围 DNS 服务器。
    
   b. 外部外围网络子网上的一个静态 IP 地址，将默认网关指向外部防火墙的内部接口。 配置适配器 DNS 设置以指向一对外围 DNS 服务器。 只有在之前将拓扑配置为在端口分配中具有非标准值时，此配置才可接受，如创建边缘拓扑[Skype for Business Server文章中介绍](create-your-edge-topology.md)。
    
3. 在内部接口上，在内部外围网络子网上配置一个静态 IP，不要设置默认网关。 将适配器 DNS 设置配置为指向至少一台 DNS 服务器，但最好是一对外围 DNS 服务器。
    
4. 在内部接口上创建到统一消息服务器驻留的客户端、Skype for Business Server Exchange的所有内部 (静态) 路由。
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>外围网络中没有 DNS 服务器的接口配置

1. 为每台边缘服务器安装两个网络适配器，一个适用于面向内部的接口，另一个适用于面向外部的接口。
    
    > [!NOTE]
    > 内部子网和外部子网不得相互路由。 
  
2. 在外部接口上，将配置 **以下项** 之一：
    
   a. 外部外围网络子网上的三个静态 IP 地址。 您还需要在外部接口上配置默认网关，例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。 将适配器 DNS 设置配置为指向外部 DNS 服务器，最好是一对外部 DNS 服务器。
    
   b. 外部外围网络子网上的一个静态 IP 地址。 您还需要在外部接口上配置默认网关，例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。 将适配器 DNS 设置配置为指向外部 DNS 服务器，或最好是一对外部 DNS 服务器。 只有在之前将拓扑配置为在端口分配中具有非标准值时，此配置才可接受，如创建边缘拓扑[Skype for Business Server文章中介绍](create-your-edge-topology.md)。
    
3. 在内部接口上，在内部外围网络子网上配置一个静态 IP，不要设置默认网关。 此外，将适配器 DNS 设置留空。
    
4. 在内部接口上创建到统一消息服务器驻留的客户端、Skype for Business Server Exchange的所有内部 (静态) 路由。
    
5. 编辑每台边缘服务器的 HOST 文件，以包含下一个跃点服务器或虚拟 IP (VIP) 。 此记录将是在拓扑Standard Edition中配置为边缘服务器下一跃点地址的控制器、服务器或前端池。 如果使用的是 DNS 负载平衡，请为下一个跃点池的每个成员包括一行。
    
## <a name="installation"></a>安装

若要成功完成这些步骤，你将需要遵循创建边缘拓扑以使用[Skype for Business Server中的步骤](create-your-edge-topology.md)。
  
1. 使用本地管理员组的帐户登录到为边缘服务器角色配置的服务器。
    
2. 您需要在此计算机上边缘服务器拓扑文档末尾复制的拓扑配置文件。 访问你放置该配置文件的外部媒体， (USB 驱动器或共享) 。
    
3. 启动部署 **向导**。
    
4. 打开向导后，单击"**安装或更新Skype for Business Server系统"。**
    
5. 向导将运行检查以查看是否已安装任何内容。 由于这是第一次运行向导，因此你需要从步骤 **1 开始。安装本地配置存储。**
    
6. 将显示 **"配置中央管理存储的本地副本** "对话框。 You need to click **Import from a file (Recommended for Edge Servers)**.
    
7. 从此处浏览到之前导出的拓扑的位置，选择.zip文件，单击"打开"，然后单击"下一步 **"。** 
    
8. 部署向导将读取配置文件，将 XML 配置文件写入本地计算机。
    
9. “正在执行命令”过程完成后，单击“完成”。
    
10. 在部署向导中，单击"**步骤 2"。安装或删除Skype for Business Server组件**。 然后，该向导Skype for Business Server存储在本地计算机的 XML 配置文件中指定的边缘组件。
    
11. 安装完成后，可以继续下面的证书 **部分中** 的步骤。
    
## <a name="certificates"></a>证书

边缘服务器的证书要求可在边缘证书规划文档中找到。 以下是设置证书的步骤。
  
> [!NOTE]
> 在运行证书向导时，您需要以帐户身份登录，该帐户对将使用的证书模板类型具有正确的权限。 默认情况下，Skype for Business Server证书请求将使用 Web 服务器证书模板。 如果使用 RTCUniversalServerAdmins 组的成员帐户登录，以通过此模板请求证书，请仔细检查以确保该组已分配有使用该模板的注册权限。 
  
### <a name="internal-edge-interface-certificates"></a>内部边缘接口证书

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. 下载或导出 CA 证书链

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. 使用 certsrv 网站下载

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. 以本地Skype for Business Server成员登录到内部网络中管理员组。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. 打开"**开始**"， ("**搜索**"或"运行) "，然后键入以下内容： 
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. 在颁发 CA 的 certsrv 网页上的"选择任务"**下**，单击"下载 CA 证书、证书链 **或 CRL"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. 在 **"下载 CA 证书、证书链或 CRL"** 下，单击"**下载 CA 证书链"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. 在"**文件下载"框中**，单击"保存 **"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. 将 .p7b 文件保存到服务器的硬盘驱动器，然后将它复制到每台边缘服务器的文件夹中。
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. 使用 MMC 导出

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. 可以使用 MMC 从加入域的任何计算机导出 CA 根证书。 转到"开始 **"** 和"**运行**"，或打开 **"搜索"，****然后键入 MMC** 以打开。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. 在 MMC 控制台中，单击 **"文件**"，然后单击"**添加/删除管理单元"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. 从"**添加或删除管理单元"对话框** 列表中，选择"**证书**"，然后单击"添加 **"。** 当系统提示时，选择 **"计算机帐户"，** 然后选择"下一 **步"。** 在“选择计算机”对话框中，选择“本地计算机”。 单击 **"完成**"，然后单击"**确定"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. 展开 **"证书 (本地计算机) "**。 展开 **“受信任的根证书颁发机构”**。 选择 **"证书"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. 单击由 CA 颁发的根证书。 右键单击证书 **，在菜单** 上选择"所有任务"，然后选择"导出 **"。**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. 将 **打开证书导出向导** 。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;。 在" **导出文件格式"** 对话框中，选择要导出到的格式。 我们的建议是 **加密消息语法 Standard - PKCS #7 Certificates (P7b)**。 如果这也是你的选择，请记住还要选中"如果可能，请在证书路径中包括所有证书"复选框，因为此操作还将导出证书链，包括根 CA 证书和任何中间证书。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;功能。 在" **要** 导出的文件"对话框的文件名条目中，键入路径和文件名 (导出证书的默认扩展名为 .p7b) 。 If it's easier on you， choose the **Browse** button to go to the location you want to save the exported certificate to， and name the exported certificate here. 准备就绪 **后****，单击"** 保存"，然后单击"下一步"。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix。 查看操作摘要，然后单击" **完成** "完成证书导出。 单击“确定”确认导出成功。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. 将 .p7b 文件复制到每台边缘服务器。
    
### <a name="2-import-the-ca-certification-chain"></a>2. 导入 CA 证书链

&nbsp;&nbsp;&nbsp;a. 在每台边缘服务器上，打开 MMC **(选择"** 开始 **"和"** 运行"或"搜索"，然后键入 **MMC** 以打开) 。
    
&nbsp;&nbsp;&nbsp;b. 在"**文件"** 菜单上，单击 **"添加/删除管理单元"，** 然后选择"添加 **"。**
    
&nbsp;&nbsp;&nbsp;c. 在"**添加或删除管理单元"框中，单击**"**证书"，** 然后单击"添加 **"。**
    
&nbsp;&nbsp;&nbsp;d. 在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。
    
&nbsp;&nbsp;&nbsp;e. 在 **"选择计算机**"对话框中，确保选中"本地计算机 **： (** 运行此控制台的计算机) 复选框，然后单击"完成 **"。**
    
&nbsp;&nbsp;&nbsp;f. 单击 **"关闭**"，然后单击"**确定"。**
    
&nbsp;&nbsp;&nbsp;g. 在控制台树中，展开"证书 (**本地** 计算机) ，右键单击"受信任的根证书颁发机构"，转到"**所有** 任务"，然后单击"导入 **"。**
    
&nbsp;&nbsp;&nbsp;h. 在出现的向导中的"要导入的文件"文本框中，指定证书的文件名 (在上一部分中为 .p7b 文件指定的名称) 。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;i. 将单选按钮保留为" **将所有证书放在以下存储中"，** 因为应选择"受信任的根证书颁发机构"。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;j. 查看摘要，然后单击" **完成** "完成导入。
    
&nbsp;&nbsp;&nbsp;k. 需要为要部署的每台边缘服务器完成此操作。
    
### <a name="3-create-the-certificate-request"></a>3. 创建证书请求

&nbsp;&nbsp;&nbsp;a. 登录到其中一台边缘服务器，启动部署向导，在"步骤 **3：** 请求、安装或分配证书"上，单击"运行 **("** 或"再次运行"（如果已在) 中运行此向导）。
    
&nbsp;&nbsp;&nbsp;b. 在"**证书请求"** 页上，确保 **选择"内部边缘证书**"，然后单击"请求 **"。**
    
&nbsp;&nbsp;&nbsp;c. 在"**延迟的请求**"或"即时请求"页上，选择"如果可以从边缘环境访问联机证书颁发机构，则立即将请求发送到联机证书颁发机构"，或"立即准备请求，但 **稍后** 发送其他请求"。
    
&nbsp;&nbsp;&nbsp;d. 在" **证书请求文件** "页上，输入文件将在其中保存的完整部分和文件名 (例如 c：\SkypeInternalEdgeCert.cer) 。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;e. 在" **指定备用证书** 模板"页上，若要使用默认 WebServer 模板外的其他模板，请选中"使用所选证书颁发机构的替代证书 **模板"复选框** 。 否则，不执行任何操作。
    
&nbsp;&nbsp;&nbsp;f. 在“名称和安全设置”页上，执行以下操作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. 在 **"友好名称**"中，显示名称内部边缘 (输入证书) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. 在 **"** 位长度"中，选择位长度 (默认值为 2048，您可以更高，更安全，但会使性能降低) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. 如果需要可导出的证书，必须选中"将 **证书私钥标记为可导出** "复选框。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;g. 在" **组织信息** "页上，输入组织单位和组织单位的名称 (OU) 。 你可以向 IT 部门 (部门，例如) 。
    
&nbsp;&nbsp;&nbsp;h. 在" **地理信息"** 页上，输入您的位置信息。
    
&nbsp;&nbsp;&nbsp;i. 在" **主题名称/主题替代** 名称"页上，向导应自动填充此名称。
    
&nbsp;&nbsp;&nbsp;j. 在 **"配置其他主题替代** 名称"页上，需要添加所需的任何其他主题替代名称。
    
&nbsp;&nbsp;&nbsp;k. 在 **"请求摘要** "页上，查看将用于生成请求的证书信息。 如果需要进行更改，请返回并现在就进行更改。
    
&nbsp;&nbsp;&nbsp;l. 然后单击 **"下** 一步"以生成需要向 CA 提供的 CSR 文件 (还可以单击"查看日志"查看证书请求日志) 。
    
&nbsp;&nbsp;&nbsp;m. 生成请求后，可以单击"查看"查看证书，然后单击"完成"关闭窗口。 CSR 文件的内容需要给予 CA，以便他们可以生成证书，以便您可以在下一节中导入到此计算机。
    

### <a name="4-import-the-certificate"></a>4. 导入证书

&nbsp;&nbsp;&nbsp;a. 以本地证书颁发机构管理员组登录到上一过程中您提出证书请求的边缘服务器。
    
&nbsp;&nbsp;&nbsp;b. 在部署向导中，在步骤 **3 旁边。"请求、安装或分配证书"，** 单击"**再次运行"。**
    
&nbsp;&nbsp;&nbsp;c. 在" **可用证书任务** "页上，单击 **"从 导入证书"。P7b、.pfx 或 .cer 文件**。
    
&nbsp;&nbsp;&nbsp;d. 在"**导入** 证书"页上，键入在上一部分 (中获得证书的完整路径和文件名，也可以单击"浏览"查找并选择该文件，) 。
    
&nbsp;&nbsp;&nbsp;e. 如果要为边缘池的其他成员导入证书，并且证书包含私钥，请务必选中包含证书私钥的证书文件复选框，并指定密码。 单击“下一步”即可继续操作。
    
&nbsp;&nbsp;&nbsp;f. 在"**摘要"页上**，确认信息后单击"下一步"，在成功导入证书后单击"完成"。
    
 
### <a name="5-export-the-certificate"></a>5. 导出证书

&nbsp;&nbsp;&nbsp;a. 确保你已以本地证书管理员身份登录到之前将证书导入到的边缘管理员组。
    
&nbsp;&nbsp;&nbsp;b. 单击 **"开始****"， (** 或打开 **"** 搜索) ，然后键入 **MMC。**
    
&nbsp;&nbsp;&nbsp;c. 在 MMC 控制台中，单击 **"文件**"，然后单击"**添加/删除管理单元"。**
    
&nbsp;&nbsp;&nbsp;d. 在"**添加或删除管理单元"框中，单击**"**证书"，** 然后单击"添加 **"。**
    
&nbsp;&nbsp;&nbsp;e. 在"**证书管理** 单元"对话框中，选择"计算机 **帐户"。** 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;f. 在" **选择计算机** "对话框中，选择"本地计算机 **： (** 运行此控制台的计算机) " 。 单击“完成”。 单击 **"** 确定"，MMC 控制台的配置即已完成。
    
&nbsp;&nbsp;&nbsp;g. 双击“证书(本地计算机)”扩展证书存储。 双击"个人 **"，** 然后单击"证书 **"。**
    
  > [!NOTE]
  > 你可能在这里，并且在本地计算机的证书个人存储中看不到任何证书。 如果密钥不存在，则无需四处寻找，导入的证书没有与之关联的私钥。 再尝试一次上述请求和导入步骤，如果确定一切正确，请与 CA 管理员或提供商联系。 
  
&nbsp;&nbsp;&nbsp;h. 在本地 **计算机的证书** 个人存储中，右键单击要导出的证书。 从 **生成的菜单中** 选择"所有任务"，然后单击"导出 **"。**
    
&nbsp;&nbsp;&nbsp;i. 在“证书导出向导”中，单击“下一步”。 选择“是，导出私钥”。 单击“下一步”。
    
&nbsp;&nbsp;&nbsp;j. 在"**导出文件格式"** 对话框中，选择"个人信息"Exchange **- PKCS#12 (。PFX)**，然后选择以下选项：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. 如果可能，在证书路径中包括所有证书。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. 导出所有扩展属性。
    
   > [!NOTE]
   > **如果** 导出 **成功，切勿选择"删除私钥"。** 这意味着您必须将证书和私钥重新导入回此边缘服务器。
  
&nbsp;&nbsp;&nbsp;k. 如果要分配密码来保护私钥，可以键入私钥的密码。 重新输入密码以确认，然后单击下一 **步**。
    
&nbsp;&nbsp;&nbsp;l. 使用文件扩展名 **.pfx** 键入导出证书的路径和文件名。 该路径需要可由池中的其他边缘服务器访问，或者您需要通过外部媒体传输（如 USB 驱动器 (移动) 。 做出 **选择** 后，单击"下一步"。
    
&nbsp;&nbsp;&nbsp;m. 查看"正在完成 **证书导出** 向导"对话框上的摘要，然后单击"完成 **"。**
    
&nbsp;&nbsp;&nbsp;n. 在成功导出对话框中单击“确定”。
    
 
### <a name="6-assign-the-certificate"></a>6. 分配证书

&nbsp;&nbsp;&nbsp;a. 在每台边缘服务器的部署向导中，在步骤 **3 旁边。请求、安装或分配证书，** 单击再次 **运行**。
    
&nbsp;&nbsp;&nbsp;b. 在"**可用证书任务**"页上，单击 **"分配现有证书"。**
    
&nbsp;&nbsp;&nbsp;c. 在“证书分配”页上，选择列表中的“边缘内部”。
    
&nbsp;&nbsp;&nbsp;d. 在" **证书存储** "页上，选择从上一部分中为内部边缘 (导入的证书) 。
    
&nbsp;&nbsp;&nbsp;e. 在"**证书分配摘要"** 页上，查看设置，然后单击"下一步"分配证书。
    
&nbsp;&nbsp;&nbsp;f. 在向导完成页上，单击 **“完成”**。
    
&nbsp;&nbsp;&nbsp;g. 完成此过程后，真正好办法在每个边缘服务器上打开证书 MMC 管理单元，展开证书 (本地计算机 **) ，** 展开个人，单击证书，并确认详细信息窗格中列出了内部边缘证书。  
    
### <a name="external-edge-interface-certificates"></a>外部边缘接口证书

 
### <a name="1-create-the-certificate-request"></a>1. 创建证书请求

&nbsp;&nbsp;&nbsp;a. 登录到其中一台边缘服务器，启动部署向导，在"步骤 **3：** 请求、安装或分配证书"上，单击"运行 ("或"再次运行"（如果已运行此向导) ）。
    
&nbsp;&nbsp;&nbsp;b. 在“可用的证书任务”页上，单击“创建新的证书请求”。
    
&nbsp;&nbsp;&nbsp;c. 在"**证书请求"** 页上，确保 **已选择"外部边缘证书**"，然后单击"下一 **步"。**
    
&nbsp;&nbsp;&nbsp;d. 在“延迟的请求或即时请求”页上，单击“现在准备请求，但稍后发送”。
    
&nbsp;&nbsp;&nbsp;e. 在" **证书请求文件** "页上，输入文件将在其中保存的完整部分和文件名 (例如 c：\SkypeInternalEdgeCert.cer) 。 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;f. 在" **指定备用证书** 模板"页上，若要使用默认 WebServer 模板外的其他模板，请选中"使用所选证书颁发机构的替代证书 **模板"复选框** 。
    
&nbsp;&nbsp;&nbsp;g. 在“名称和安全设置”页上，执行以下操作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. 在 **"友好名称**"中，显示名称外部边缘 (，例如外部边缘) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. 在 **"** 位长度"中，选择位长度 (默认值为 2048，您可以更高且更安全，但会使性能降低) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. 如果需要可导出的证书，必须选中"将 **证书私钥标记为可导出** "复选框。
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;h. 在" **组织信息** "页上，输入组织单位和组织单位的名称 (OU) 。 你可以向 IT 部门 (部门，例如) 。
    
&nbsp;&nbsp;&nbsp;i. 在" **地理信息"** 页上，输入您的位置信息。
    
&nbsp;&nbsp;&nbsp;j. 在 **"主题名称/主题替代** 名称"页上，向导应自动填充所需信息。
    
&nbsp;&nbsp;&nbsp;k. 在" **主题备用名称上的 SIP** 域设置" (") "页面上，选中"域"复选框以添加 sip。\<sipdomain> 条目。
    
&nbsp;&nbsp;&nbsp;l. 在 **"配置其他主题替代** 名称"页上，需要添加所需的任何其他主题替代名称。
    
&nbsp;&nbsp;&nbsp;m. 在 **"请求摘要** "页上，查看将用于生成请求的证书信息。 如果需要进行更改，请返回并现在就进行更改。
    
&nbsp;&nbsp;&nbsp;n. 准备好后，单击"下一步"生成需要向 CA (还可以单击"查看日志"查看证书请求请求日志) 。 
    
&nbsp;&nbsp;&nbsp;o. 生成请求后，可以单击"查看"查看证书，然后单击"完成"关闭窗口。 CSR 文件的内容需要给予 CA，以便他们可以生成证书，以便您可以在下一节中导入到此计算机。
    
&nbsp;&nbsp;&nbsp;p.  (可选) 在提交 CSR 的内容时，可能会要求你提供某些信息，如下所示 (AA 会有很大差异，因此在提交时可能) ：
    
  - **Microsoft** 作为服务器平台
    
  - **IIS** 作为版本
    
  - **Web 服务器** 作为使用类型
    
  - **PKCS7** 作为响应格式
    
 
### <a name="2-import-the-certificate"></a>2. 导入证书

&nbsp;&nbsp;&nbsp;a. 以本地证书颁发机构管理员组登录到上一过程中您提出证书请求的边缘服务器。
    
&nbsp;&nbsp;&nbsp;b. 在部署向导中，在步骤 **3 旁边。"请求、安装或分配证书"，** 单击"**再次运行"。**
    
&nbsp;&nbsp;&nbsp;c. 在" **可用证书任务** "页上，单击 **"从 导入证书"。P7b、.pfx 或 .cer 文件**。
    
&nbsp;&nbsp;&nbsp;d. 在"**导入** 证书"页上，键入在上一部分 (中获得证书的完整路径和文件名，也可以单击"浏览"查找并选择该文件，) 。 如果证书包含私钥，请确保选择"证书文件 **包含** 证书的私钥"，然后输入私钥的密码。 准备就绪 **后，** 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;e. 在"**导入证书摘要"页上**，查看摘要信息，然后单击"下一步 **"。**
    
&nbsp;&nbsp;&nbsp;f. 在 **"正在执行命令** "页上，可以在导入完成后通过单击"查看日志"查看 **导入结果**。 单击 **"** 完成"完成证书导入。
    
&nbsp;&nbsp;&nbsp;g. 如果池中还有其他边缘服务器，则还需要执行接下来的两个过程。 如果这是独立边缘服务器，则使用外部证书完成。
    
 
### <a name="3-export-the-certificate"></a>3. 导出证书

&nbsp;&nbsp;&nbsp;a. 确保以本地管理员身份登录到将证书导入到的边缘服务器。
    
&nbsp;&nbsp;&nbsp;b. 单击 **"开始****"， (** 或打开 **"** 搜索) ，然后键入 **MMC。**
    
&nbsp;&nbsp;&nbsp;c. 在 MMC 控制台中，单击 **"文件**"，然后单击"**添加/删除管理单元"。**
    
&nbsp;&nbsp;&nbsp;d. 在"**添加或删除管理单元"框中，单击**"**证书"，** 然后单击"添加 **"。**
    
&nbsp;&nbsp;&nbsp;e. 在"**证书管理** 单元"对话框中，选择"计算机 **帐户"。** 单击"下一步"。
    
&nbsp;&nbsp;&nbsp;f. 在" **选择计算机** "对话框中，选择"本地计算机 **： (** 运行此控制台的计算机) " 。 单击“完成”。 单击 **"** 确定"，MMC 控制台的配置即已完成。
    
&nbsp;&nbsp;&nbsp;g. 双击“证书(本地计算机)”扩展证书存储。 **双击"个人"，** 然后单击"证书 **"。**
    
   > [!NOTE]
   > 你可能在这里，并且在本地计算机的证书个人存储中看不到任何证书。 如果密钥不存在，则无需四处寻找，导入的证书没有与之关联的私钥。 再尝试一次上述请求和导入步骤，如果确定一切正确，请与 CA 管理员或提供商联系。 
  
&nbsp;&nbsp;&nbsp;h. 在本地 **计算机的证书** 个人存储中，右键单击要导出的证书。 **从生成的菜单中** 选择"所有任务"，然后单击"导出 **"。**
    
&nbsp;&nbsp;&nbsp;i. 在“证书导出向导”中，单击“下一步”。 选择“是，导出私钥”。 单击“下一步”。
    
   > [!NOTE]
   > 如果 **"是"，则** 导出私钥不可用，那么在获得此证书之前，该证书的私钥未标记为导出。 您需要再次向提供程序请求证书，同时将私钥设置为导出，然后才能成功执行此操作。
  
&nbsp;&nbsp;&nbsp;j. 在"导出文件格式"对话框中，选择"个人信息"Exchange - PKCS#12 (。PFX) ，然后选择以下选项：
    
 &nbsp;&nbsp;&nbsp;  i. 如果可能，在证书路径中包括所有证书。
    
 &nbsp;&nbsp;&nbsp;  ii. 导出所有扩展属性。
    
   > [!NOTE]
   > **如果** 导出 **成功，切勿选择"删除私钥"。** 这意味着您必须将证书和私钥重新导入回此边缘服务器。
  
&nbsp;&nbsp;&nbsp;k. 如果要分配密码来保护私钥，可以键入私钥的密码。 重新输入密码以确认，然后单击下一 **步**。
    
&nbsp;&nbsp;&nbsp;l. 使用文件扩展名 **.pfx** 键入导出证书的路径和文件名。 该路径需要可由池中的其他边缘服务器访问，或者你需要通过外部媒体传输（如 USB 驱动器 (移动) 。 做出 **选择** 后，单击"下一步"。
    
&nbsp;&nbsp;&nbsp;m. 查看"正在完成 **证书导出** 向导"对话框上的摘要，然后单击"完成 **"。**
    
&nbsp;&nbsp;&nbsp;n. 在成功导出对话框中单击“确定”。
    
&nbsp;&nbsp;&nbsp;o. 现在，你需要返回到之前导入证书部分，并将证书导入到所有剩余的边缘服务器，然后继续分配，如下所示。
    
 
### <a name="4-assign-the-certificate"></a>4. 分配证书

&nbsp;&nbsp;&nbsp;a. 在 **每台** 边缘服务器的部署向导中，在步骤 **3 旁边。请求、安装或分配证书，** 单击再次 **运行**。
    
&nbsp;&nbsp;&nbsp;b. 在"**可用证书任务**"页上，单击 **"分配现有证书"。**
    
&nbsp;&nbsp;&nbsp;c. 在" **证书分配"** 页上， **选择列表中的"边缘外部** "。
    
&nbsp;&nbsp;&nbsp;d. 在" **证书存储** "页上，从上一部分选择为外部边缘 (导入的证书) 。
    
&nbsp;&nbsp;&nbsp;e. 在"**证书分配摘要"** 页上，查看设置，然后单击"下一步"分配证书。
    
&nbsp;&nbsp;&nbsp;f. 在向导完成页上，单击 **“完成”**。
    
&nbsp;&nbsp;&nbsp;g. 完成此过程后，在每个服务器上打开"证书 MMC"管理单元，展开"证书 (本地计算机 **) "，** 展开"个人"，单击"证书"，并确认详细信息窗格中列出了内部边缘证书，这是一个不错的主意。
    
   > [!NOTE]
   > 您还需要为反向代理服务器设置证书。 
  
## <a name="starting-the-edge-servers"></a>启动边缘服务器

设置完成后，需要在部署中的每台边缘服务器上启动服务：
  
1. 在每台边缘服务器的部署 **向导中**，单击"步骤 **4： 启动服务"旁边的**"运行 **"。**
    
2. 在"**启动Skype for Business Server服务**"页上，查看服务列表，然后单击"下一步"以启动服务。
    
3. 启动服务后，可以单击" **完成"** 关闭向导。
    
4.  (可选 **) "步骤 4：启动服务**"下，单击"**服务状态"。**
    
5.  在 **每台服务器的"服务 MMC"** 中，验证所有Skype for Business Server服务是否正在运行。
    


---
title: 为反向 HTTP 代理请求和配置证书
description: 为反向 HTTP 代理请求和配置证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579038"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-14_

您需要在运行 Microsoft Forefront 威胁管理网关2010或 IIS ARR 的服务器上为运行 Microsoft Lync Server 2013 的内部服务器上的根证书颁发机构) 证书安装 (CA 证书。

此外，还必须在反向代理服务器上安装公用 web 服务器证书。 此证书的主题备用名称应包含已发布的外部完全限定域名 (Fqdn) 对于为其启用远程访问的用户的每个池，以及将在该边缘基础结构中使用的所有控制器或控制器池的外部 Fqdn。 主题备选名称还必须包含会议简单 URL、拨入简单 URL，并且如果要部署移动应用程序和计划使用自动发现，那么还有外部自动发现服务 URL（如下表所示）。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>值</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者名称</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>使用者替代名称</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> 主题名称还必须存在于使用者备用名称中。

</td>
</tr>
<tr class="odd">
<td><p>使用者替代名称</p></td>
<td><p>如果部署了控制器，则 (可选的控制器 Web 服务) </p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>使用者替代名称</p></td>
<td><p>会议简单 URL</p>



> [!NOTE]
> 所有会议简单 URL 都必须位于使用者替代名称中。每个 SIP 域必须至少有一个活动会议简单 URL。

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>使用者替代名称</p></td>
<td><p>拨入简单 URL</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>使用者替代名称</p></td>
<td><p>Office Web Apps Server</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>使用者替代名称</p></td>
<td><p>外部自动发现服务 URL</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> 如果还使用 Microsoft Exchange Server，则还需要为 Exchange 自动发现和 web 服务 Url 配置反向代理规则。

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 如果内部部署包含多个 Standard Edition Server 或前端池，则必须为每个外部 Web 场 FQDN 配置 Web 发布规则，并且还需为其配置证书和 Web 侦听器，或者获取使用者替代名称包含所有池使用的名称的证书，将其分配给 Web 侦听器，并在多个 Web 发布规则中共享。



</div>

<div>

## <a name="create-a-certificate-request"></a>创建证书请求

在反向代理上创建证书请求。 您在另一台计算机上创建一个请求，但您必须使用私钥导出签名证书，并在从公共证书颁发机构收到该证书后将其导入到反向代理。

<div>


> [!NOTE]
> 证书请求或证书签名请求 (CSR) 是对受信任的公共证书颁发机构 (CA) 的请求，用于对请求的计算机的公钥进行验证和签名。 在生成证书时，将创建公钥和私钥。 只有公钥是共享和签名的。 顾名思义，公钥可用于任何公用请求。 公钥供客户端、服务器和需要安全地交换信息并验证计算机标识的其他请求者使用。 私钥保持安全，并且只能由创建密钥对的计算机使用，以解密用其公钥加密的邮件。 专用密钥可用于其他用途。 出于反向代理目的，数据加密是主要用途。 Secondarily，证书密钥级别的证书身份验证是另一种用途，仅限于请求者拥有计算机公钥的验证，或者您拥有其公钥的计算机实际上是它所声明的计算机。



</div>

<div>


> [!TIP]
> 如果同时规划边缘服务器证书和反向代理证书，应注意两种证书要求之间有很大的相似性。 配置和请求边缘服务器证书时，请结合边缘服务器和反向代理使用者备用名称。 如果导出证书和私钥并将导出的文件复制到反向代理，然后导入证书/密钥对并在即将进行的过程中根据需要对其进行分配，可以对反向代理使用相同的证书。 请参阅 lync server 2013 中的边缘服务器计划边缘服务器证书的证书要求 &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A>以及 lync server 2013 中的反向代理<A href="lync-server-2013-certificate-summary-reverse-proxy.md">证书摘要-反向</A>代理。 请确保使用可导出的私钥创建证书。 为池边缘服务器创建具有可导出私钥的证书和证书请求是必需的，因此这是一种正常实践，而在 "Lync Server 部署向导" 中，边缘服务器的 "证书向导" 将允许您设置 "设置 <STRONG>私钥可导出</STRONG> " 标志。 从公共证书颁发机构收到证书请求后，将导出证书和私钥。 有关如何使用私钥创建和导出证书的详细信息，请参阅主题 "为 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部边缘接口设置</A> 证书" 中的 "导出证书的私钥与池中的边缘服务器" 部分。 证书的扩展名应为 <STRONG>.pfx</STRONG>的类型。



</div>

若要在将为其分配证书和私钥的计算机上生成证书签名请求，请执行以下操作：

**创建证书签名请求**

1.  打开 Microsoft 管理控制台 (MMC) 并添加 "证书" 管理单元，然后选择 " **计算机**"，然后展开 " **个人**"。 有关如何在 Microsoft 管理控制台 (MMC) 中创建证书控制台的详细信息，请参阅 [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) 。

2.  右键单击 " **证书**"，单击 " **所有任务**"，单击 " **高级操作**"，然后单击 " **创建自定义请求**"。

3.  在 " **证书注册** " 页上，单击 " **下一步**"。

4.  在 " **选择证书注册策略** " 页的 " **自定义请求**" 下，选择 " **继续，不进行注册策略**"。 单击“**下一步**”。

5.  在 " **自定义请求** " 页上，选择 " **模板** ** (不) 旧版密钥中的任何模板**"。 除非您的证书提供商另有指示，否则请保留**取消选中默认分机**和**PKCS \# 10**上的**请求格式**选择。 单击“**下一步**”。

6.  在 " **证书信息** " 页上，单击 " **详细信息**"，然后单击 " **属性**"。

7.  在 "**证书属性**" 页上的 "**友好名称**" 字段中的 "**常规**" 选项卡上，键入此证书的名称。 （可选）在 " **说明** " 字段中键入说明。 管理员通常使用友好名称和说明来标识证书用途，如 **Lync Server 的反向代理侦听器**。

8.  选择 "**主题**" 选项卡。在 "**类型**的**主题名称**" 下，选择 "使用者名称类型的**公用名称**"。 对于 " **值**"，键入将用于反向代理的主题名称，然后单击 " **添加**"。 在本主题的表中提供的示例中，使用者名称为 webext.contoso.com，并将在 "值" 字段中键入主题名称。

9.  在 "**其他名称**" 下的 "**主题**" 选项卡中，从 "类型" 下拉**类型**中选择 " **DNS** "。 对于您在证书上所需的每个已定义的主题替代名称，请键入完全限定的域名，然后单击 " **添加**"。 例如，在表中有三个使用者可选名称、meet.contoso.com、dialin.contoso.com 和 lyncdiscover.contoso.com。 在 " **值** " 字段中，键入 meet.contoso.com，然后单击 " **添加**"。 对需要定义的每个使用者可选名称重复上述步骤。

10. 在 " **证书属性** " 页上，单击 " **扩展** " 选项卡。在此页面上，将定义 **密钥用法** 中的加密密钥用途，以及扩展密钥用法中扩展密钥用法 ** (应用程序策略) **。

11. 单击 " **密钥用法** " 箭头以显示 **可用选项**。 在 "可用选项" 下，单击 " **数字签名**"，然后单击 " **添加**"。 单击 " **密钥译码**"，然后单击 " **添加**"。 如果未选中 " **将这些密钥用法设为关键** " 复选框，请选中该复选框。

12. 单击 " ** (应用程序策略) 箭头的" 扩展密钥用法 ** "以显示 **可用选项**。 在 "可用选项" 下，单击 " **服务器身份验证**"，然后单击 " **添加**"。 单击 " **客户端身份验证**"，然后单击 " **添加**"。 如果选中 " **使扩展密钥用法为关键"** 的复选框，请取消选中该复选框。 与 "密钥用法" 复选框相反 (必须选中该复选框) 必须确保未选中 "扩展密钥用法" 复选框。

13. 在 " **证书属性** " 页上，单击 " **私钥** " 选项卡。单击 " **密钥选项** " 箭头。 对于 " **密钥大小**"，从下拉菜单中选择 " **2048** "。 如果要在此证书所针对的反向代理之外的计算机上生成此密钥对和 CSR，请选择 " **使密钥可导出**"。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" />安全说明：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果服务器场中有多个反向代理，则通常会建议选择 " <strong>使私钥可导出</strong> "，因为您会将证书和私钥复制到服务器场中的每台计算机。 如果你确实允许可导出的私钥，则必须对证书及其生成时所用的计算机额外关注。 如果泄露私钥，则会将证书变得无用，并可能会将计算机暴露给外部访问和其他安全漏洞。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. 在 " **私钥** " 选项卡上，单击 " **键类型** " 箭头。 选择 " **Exchange** " 选项。

15. 单击 **"确定"** 以保存已设置的 **证书属性** 。

16. 在 " **证书注册** " 页上，单击 " **下一步**"。

17. 在 "**您希望将脱机请求保存在什么位置？** " 页上，系统会提示**File Name**您输入文件名和**文件格式**以保存证书签名请求。

18. **在 "文件名条目"** 字段中，键入请求的路径和文件名，或者单击 "**浏览**" 以选择文件的位置，并键入请求的文件名。

19. 对于 **文件格式**，请单击 " **Base 64** " 或 " **二进制**"。 选择 " **基本 64** "，除非您的证书的供应商向您提供其他指示。

20. 找到您在上一步中保存的请求文件。 提交到公共证书颁发机构。
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft 已识别出满足统一通信需求的公共 Ca。 下面的知识库文章中维护了一个列表。 <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


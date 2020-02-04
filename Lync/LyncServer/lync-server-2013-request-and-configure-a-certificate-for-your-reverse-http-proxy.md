---
title: 为 HTTP 反向代理请求和配置证书
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
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中为 HTTP 反向代理请求和配置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-14_

对于向运行 Microsoft Lync 的内部服务器颁发服务器证书的 CA 基础结构，您需要在运行 Microsoft Forefront 威胁管理网关2010或 IIS ARR 的服务器上安装根证书颁发机构（CA）证书服务器2013。

您还必须在反向代理服务器上安装公共 web 服务器证书。 此证书的主题备用名称应包含为用户启用远程访问的每个池的已发布外部完全限定的域名（Fqdn），以及将在其中使用的所有控制器或控制器池的外部 Fqdn。该 Edge 基础结构。 主题备用名称还必须包含会议简单 URL、拨入式简单 URL，如果你要部署移动应用程序并计划使用自动发现，请按下表所示使用 "外部自动发现服务" URL。


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
<td><p>主题名称</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>使用者替代名称</p></td>
<td><p>池 FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> 主题名称还必须存在于 "主题备用名称" 中。

</td>
</tr>
<tr class="odd">
<td><p>使用者替代名称</p></td>
<td><p>可选的主管 Web 服务（如果已部署 Director）</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>使用者替代名称</p></td>
<td><p>会议简单 URL</p>



> [!NOTE]
> 所有会议简单 Url 必须位于主题备用名称中。 每个 SIP 域必须至少有一个活动会议简单 URL。

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
> 如果你还在使用 Microsoft Exchange Server，你还需要为 Exchange 自动发现和 web 服务 Url 配置反向代理规则。

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 如果内部部署包含多个标准版服务器或前端池，则必须为每个外部 web 场 FQDN 配置 web 发布规则，并且每个外部 web 场 FQDN 都需要一个证书和 web 侦听器，或者必须获取证书其主题备用名称包含所有池使用的名称，将其分配给 web 侦听器，并在多个 web 发布规则之间共享。



</div>

<div>

## <a name="create-a-certificate-request"></a>创建证书请求

在反向代理服务器上创建证书请求。 在另一台计算机上创建一个请求，但必须使用私钥导出签名的证书，并在从公共证书颁发机构收到该证书后将其导入到反向代理。

<div>


> [!NOTE]
> 证书申请或证书签名请求（CSR）是对受信任的公共证书颁发机构（CA）的请求，用于验证和签名请求计算机的公共密钥。 当生成证书时，将创建一个公钥和一个私钥。 仅共享和签名公钥。 正如名称所示，公钥可用于任何公共请求。 公钥供客户、服务器和其他申请者使用，这些申请者需要安全地交换信息并验证计算机的标识。 私钥保持安全，并且仅由创建密钥对的计算机使用，用于解密使用其公钥加密的消息。 私钥可用于其他用途。 对于反向代理目的，数据加密是主要用途。 Secondarily，证书密钥级别的证书身份验证是另一种用途，仅限于验证请求者拥有计算机的公钥，或者你拥有公钥的计算机实际上是它所声明的计算机。



</div>

<div>


> [!TIP]
> 如果同时计划 Edge 服务器证书和反向代理证书，应注意两种证书要求之间有很大的相似性。 配置和请求 Edge 服务器证书时，请结合边缘服务器和反向代理主题备用名称。 如果你导出证书和私钥并将导出的文件复制到反向代理，然后导入证书/密钥对并在即将进行的过程中根据需要分配证书/密钥对，则可以为反向代理使用相同的证书。 请参阅 lync server 2013 中的边缘服务器&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">计划</A>和反向代理<A href="lync-server-2013-certificate-summary-reverse-proxy.md">证书摘要-lync server 2013 中的反向</A>代理服务器证书的证书要求。 请确保使用可导出的私钥创建证书。 使用池边缘服务器创建证书和证书请求时需要具有可导出的私钥，因此这是一种正常做法，在 "Lync Server 部署向导" 中，边缘服务器的证书向导将允许你设置 "设置<STRONG>私钥可导出</STRONG>" 标志。 从公共证书颁发机构收到证书申请后，您将导出证书和私钥。 有关如何使用私钥创建和导出您的证书的详细信息，请参阅主题为<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部边缘界面设置</A>证书中的 "导出证书并为该池的私钥" 部分。 证书的扩展名应为<STRONG>.pfx</STRONG>。



</div>

若要在将分配证书和私钥的计算机上生成证书签名请求，请执行以下操作：

**创建证书签名请求**

1.  打开 Microsoft 管理控制台（MMC）并添加 "证书" 管理单元，然后选择 "**计算机**"，然后展开 "**个人**"。 有关如何在 Microsoft 管理控制台（MMC）中创建证书控制台的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)。

2.  右键单击 "**证书**"，单击 "**所有任务**"，单击 "**高级操作**"，然后单击 "**创建自定义请求**"。

3.  在 "**证书注册**" 页面上，单击 "**下一步**"。

4.  在 "**选择证书注册策略**" 页面的 "**自定义请求**" 下，选择 "**继续，不包含注册策略**"。 单击" **下一步**"。

5.  在 "**自定义请求**" 页面上，对于**模板**选择 " **（无模板）旧版密钥**"。 除非您的证书提供商另有通知，否则请保留**取消选中默认扩展名**和**PKCS \#10**上的**请求格式**选择。 单击" **下一步**"。

6.  在 "**证书信息**" 页面上，单击 "**详细信息**"，然后单击 "**属性**"。

7.  在 "**证书属性**" 页面上 "**常规**" 选项卡上的 "**友好名称**" 字段中，键入此证书的名称。 （可选）在 "**说明**" 字段中键入说明。 管理员通常使用友好名称和描述来标识证书用途，例如**Lync Server 的反向代理侦听器**。

8.  选择 "**主题**" 选项卡。在**类型**的 "**主题名称**" 下，选择 "主题名称" 类型的 "**公用名**"。 对于 "**值**"，请键入将用于反向代理的主题名称，然后单击 "**添加**"。 在本主题的表所提供的示例中，主题名称是 webext.contoso.com，并将键入到主题名称的值字段中。

9.  在 "**其他名称**" 下的 "**主题**" 选项卡上，从 "**类型**" 下拉列表中选择 " **DNS** "。 对于证书上所需的每个已定义的主题备用名称，请键入完全限定的域名，然后单击 "**添加**"。 例如，在表中有三个主题可选名称、meet.contoso.com、dialin.contoso.com 和 lyncdiscover.contoso.com。 在 "**值**" 字段中，键入 meet.contoso.com，然后单击 "**添加**"。 对你需要定义的每个主题的备用名称重复上述操作。

10. 在 "**证书属性**" 页面上，单击 "**扩展**" 选项卡。在此页面上，你将定义**密钥用法**中的加密密钥用途以及**扩展密钥用法（应用程序策略）** 中的扩展密钥用法。

11. 单击 "**密钥用法**" 箭头以显示**可用选项**。 在 "可用选项" 下，单击 "**数字签名**"，然后单击 "**添加**"。 单击 "**密钥译码**"，然后单击 "**添加**"。 如果未选中 "**使这些密钥用法关键**" 的复选框处于未选中状态，请选中该复选框。

12. 单击 "**扩展密钥用法" （应用程序策略）** 箭头以显示**可用选项**。 在 "可用选项" 下，单击 "**服务器身份验证**"，然后单击 "**添加**"。 单击 "**客户端身份验证**"，然后单击 "**添加**"。 如果选中 "**使扩展密钥用法为关键"** 的复选框，请取消选中复选框。 与 "密钥用法" 复选框相反（必须选中），必须确保未选中 "扩展密钥用法" 复选框。

13. 在 "**证书属性**" 页上，单击 "**私钥**" 选项卡。单击 "**键选项**" 箭头。 对于**密钥大小**，请从下拉列表中选择**2048** 。 如果你在此证书所针对的反向代理以外的计算机上生成此密钥对和 CSR，请选择 "**使私钥可导出**"。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全说明：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>当在服务器场中拥有多个反向代理时，通常会建议选择 "<strong>使私钥可导出</strong>"，因为你将把证书和私钥复制到服务器场中的每台计算机。 如果你确实允许可导出的私钥，则必须对证书以及生成它的计算机额外小心。 私钥（如受损）将使证书不会被公开，并且可能会将计算机或计算机暴露给外部访问和其他安全漏洞。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. 在 "**专用密钥**" 选项卡上，单击 "**键类型**" 箭头。 选择 " **Exchange** " 选项。

15. 单击 **"确定"** 保存已设置的**证书属性**。

16. 在 "**证书注册**" 页面上，单击 "**下一步**"。

17. 在 "**你想要在何处保存脱机请求？** " 页面上，系统将提示你输入**文件名和用于**保存证书签名请求的**文件格式**。

18. **在 "文件名输入"** 字段中，键入请求的路径和文件名，或单击 "**浏览**" 以选择文件的位置，然后键入请求的文件名。

19. 对于**文件格式**，请单击 "**基本 64** " 或 "**二进制**"。 选择 "**基本 64** "，除非您被您的证书的供应商指示。

20. 找到您在上一步中保存的请求文件。 提交到公共证书颁发机构。
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft 已确定满足统一通信要求的公共 Ca。 以下知识库文章中将保留列表。 <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


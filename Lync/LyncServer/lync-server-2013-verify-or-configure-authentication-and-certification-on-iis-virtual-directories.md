---
title: Lync Server 2013：验证或配置 IIS 虚拟目录上的身份验证和证书
description: Lync Server 2013：验证或配置 IIS 虚拟目录上的身份验证和证书。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4d583eda7f0c7fb32b51dd5df6eb48af9b20d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560208"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-05-25_

使用以下过程可在 Internet Information Services (IIS) 虚拟目录中配置证书，或验证证书是否已正确配置。 在内部 Lync Server 池中运行 IIS 的每台服务器和可选控制器（即控制器池服务器）上执行以下过程。

<div>


> [!NOTE]  
> 以下过程定义了一个过程，该过程将请求用于所有目的 Lync Server、内部网站和 IIS 中的外部网站的组合证书。 Lync Server 2010 引入了一组 Lync Server 命令行管理程序 &nbsp; Windows PowerShell cmdlet，用于管理证书请求、导入和分配的快速目的。 该过程假定存在可以处理该请求的内部部署证书颁发机构 (CA)。 如果您使用公共证书进行 Lync Server 目的，或者您的 CA 需要脱机请求，请参阅本主题中的详细语法，以获取有关– Output 参数的信息。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">请求-Set-cscertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虚拟目录中配置身份验证和证书

1.  若要成功完成以下工作，您必须登录到安装了 web 服务 (前端服务器或控制器) 的计算机，并将其作为本地管理员。 您必须具有将向其请求证书的证书颁发机构的**读取**和**注册**权限（如果该证书颁发机构是贵组织的证书颁发机构）。 如果您配置并发送脱机证书请求，则不需要证书颁发机构的权限。

2.  单击“开始”****，选择“所有程序”****，选择“管理工具”****，然后单击“Internet 信息服务(IIS)管理器”****。

3.  在“Internet 信息服务(IIS)管理器”**** 中，选择“服务器名称”****。在“功能视图”**** 中，选择“服务器证书”****，右键单击并选择“打开功能”****。
    
    <div>
    

    > [!TIP]  
    > 在“服务器证书功能视图”中，如果向服务器分配了证书，则这些证书会显示在此处。如果某证书与 IIS 中外部网站的要求匹配，您可以重新使用该证书。要查看证书，请右键单击相应证书并选择“查看…”<STRONG></STRONG>

    
    </div>

4.  在要为其请求证书的前端服务器或控制器上，单击 " **开始**"，选择 " **所有程序**"，选择 " **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

5.  在 Lync Server 命令行管理程序中，键入以下内容：
    
        Get-CsCertificate
    
    输出是当前位于服务器上计算机个人证书存储中的证书的列表。请注意，在组合证书（即默认情况下，Web 服务内部和 Web 服务外部均使用相同的证书）中，您将看到 Use 属性将由默认值 WebServicesInternal 和 WebServicesExternal 进行填充。另外，Thumbprint 属性对于每种 Use 类型都一样。此示例显示了 Get-CsCertificate 的示例输出：
    
    ![当前 scert 状态的 Set-cscertificate 信息](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "当前 scert 状态的 Get-CsCertificate 信息")

6.  在 Lync Server 命令行管理程序中，键入以下内容：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    其中，完整命令如以下示例所示：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 默认情况下，Request-CsCertificate 将使用服务器或池名称填充使用者名称，使用服务器 FQDN、池 FQDN、简单 URL FQDN 以及内部和外部 Web 服务 FQDN 填充使用者替代名称中的条目。它通过引用您的部署中的拓扑文档来执行此操作。如果缺少值并且您指定了 –Verbose 参数，那么将通知您替代名称的计算值和实际值不同，但不会告知您缺少哪些值。该命令会向您提供 cmdlet 引用的完整计算值。在输出中使用计算的替代名称字符串以重新请求包括所有值的新证书。

    
    </div>
    
    ![使用请求-CsCertifica 的 cert 请求的输出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用 Request-CsCertifica 从证书请求输出")

7.  在 Lync Server 命令行管理程序中，键入以下内容：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    其中，完整命令如以下示例所示：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate cmdlet 的输出将指示为默认 WebServicesExternal 和 WebServicesInternal 用法分配了相同的证书（通过证书的指纹识别）。
    
    ![从 IIS WebExt 上的 Set-CsCertificate 的输出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "从 IIS WebExt 上的 Set-CsCertificate 的输出")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虚拟目录中验证或配置身份验证和证书

1.  单击“开始”****，依次选择“所有程序”****、“管理工具”****，然后单击“Internet 信息服务(IIS)管理器”****。

2.  在 " **Internet 信息服务 (IIS) 管理器**" 中，展开 " **服务器名称**"，然后展开 " **网站**"。

3.  右键单击“Lync Server 外部网站”****，然后单击“编辑绑定”****。

4.  验证 https 是否与端口 4443 关联，然后单击“https”****。

5.  选择 HTTPS 条目，单击 " **编辑**"，然后验证是否已将 Lync Server WebServicesExternalCertificate 绑定到此协议。 比较来自 Set-CsCertificate cmdlet 的指纹以确保所需证书已与 HTTPS 绑定正确关联。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


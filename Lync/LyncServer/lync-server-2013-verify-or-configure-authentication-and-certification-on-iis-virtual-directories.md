---
title: Lync Server 2013：验证或配置 IIS 虚拟目录的身份验证和认证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和认证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-05-25_

使用以下过程在 Internet Information Services (IIS) 虚拟目录上配置证书或验证证书的配置是否正确。 在内部 Lync 服务器池中运行 IIS 的每台服务器以及可选 Director 或控制器池服务器上执行以下过程。

<div>


> [!NOTE]  
> 下面的过程定义一个过程, 用于请求一个用于所有用途的证书的合并证书, 该证书用于所有用途的 Lync Server、内部网站和 IIS 中的外部网站。 Lync Server 2010 引入了一组 Lync Server Management Shell&nbsp;Windows PowerShell cmdlet, 用于管理证书请求、导入和作业的快速目的。 该过程假设有一个内部部署的证书颁发机构 (CA) 可以处理请求。 如果你为 Lync Server 目的使用公共证书, 或者你的 CA 需要脱机请求, 请参阅本主题中的详细语法, 了解有关-Output 参数的信息。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">请求-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虚拟目录上配置身份验证和证书

1.  若要成功完成以下操作, 必须登录到安装了 web 服务的计算机 (前端服务器或控制器), 并且是本地管理员。 如果证书颁发机构是您所在组织的证书颁发机构, 则您必须在您将申请证书的证书颁发机构上拥有 "**读取**" 和 "**注册**" 权限。 如果你要配置和发送脱机证书请求, 则不需要对证书颁发机构的权限。

2.  单击 "**开始**", 选择 "**所有程序**", 选择 "**管理工具**", 然后单击 " **Internet 信息服务 (IIS) 管理器**"。

3.  在 " **Internet 信息服务 (IIS) 管理器**" 中, 选择 "**服务器名**"。 在 "**功能" 视图**中, 选择 "**服务器证书**", 右键单击, 然后选择 "**打开功能**"。
    
    <div>
    

    > [!TIP]  
    > 在 "服务器证书" 功能视图中, 如果有证书分配给服务器, 它们将在此处显示。 如果存在与 IIS 中的外部网站要求相匹配的证书, 则可以重新使用该证书。 要查看证书, 请右键单击证书, 然后选择 "<STRONG>查看 ...</STRONG> "。

    
    </div>

4.  在请求证书的前端服务器或控制器上, 单击 "**开始**", 选择 "**所有程序**", 选择 " **Microsoft lync server 2013**", 然后单击 " **Lync server Management Shell**"。

5.  在 Lync Server 命令行管理器中, 键入以下内容:
    
        Get-CsCertificate
    
    输出是当前在计算机个人证书存储中的服务器上的证书的列表。 请注意, 在合并的证书 (即, 默认情况下, 内部 web 服务内部和 web 服务外部使用相同的证书) 中, 你将看到 Use 属性将使用 Default、WebServicesInternal 和 WebServicesExternal 填充。 此外, 每个使用类型的 Thumbprint 属性都是相同的。 此示例中显示了 CsCertificate 的示例输出:
    
    ![当前 scert 状态的 CsCertificate 信息](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "当前 scert 状态的 CsCertificate 信息")

6.  在 Lync Server 命令行管理器中, 键入以下内容:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    将出现完整命令的位置, 如下面的示例所示:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 默认情况下, 请求-CsCertificate 将使用服务器或池名称填充主题名称, 并使用服务器 FQDN、池 FQDN、简单 URL Fqdn 以及内部和外部 web 服务 Fqdn 填充主题备用名称中的条目。 它通过在你的部署中引用拓扑文档来执行此操作。 如果缺少值, 并且指定了-Verbose 参数, 则系统将通知你替换名称的计算值和实际值不同, 但不会通知你缺少哪些值。 它将为你提供 cmdlet 引用的整个计算值。 使用 "输出" 中的 "计算出的替换名称" 字符串重新请求将包含所有值的新证书。

    
    </div>
    
    ![使用请求-CsCertifica 的证书请求的输出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用请求-CsCertifica 的证书请求的输出")

7.  在 Lync Server 命令行管理器中, 键入以下内容:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    将出现完整命令的位置, 如下面的示例所示:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    CsCertificate cmdlet 的输出将显示相同的证书 (由证书的指纹所标识) 分配给默认、WebServicesExternal 和 WebServicesInternal 用法。
    
    ![IIS WebExt 上的 CsCertificate 设置输出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt 上的 CsCertificate 设置输出")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虚拟目录上验证或配置身份验证和证书

1.  单击 "**开始**", 选择 "**所有程序**", 选择 "**管理工具**", 然后单击 " **Internet 信息服务 (IIS) 管理器**"。

2.  在 " **Internet 信息服务 (IIS) 管理器**" 中, 展开 "**服务器名**", 然后展开 "**网站**"。

3.  右键单击 " **Lync 服务器外部网站**", 然后单击 "**编辑绑定**"

4.  验证 https 是否与端口4443关联, 然后单击 " **https**"。

5.  选择 HTTPS 条目, 单击 "**编辑**", 然后验证 Lync Server WebServicesExternalCertificate 是否绑定到此协议。 比较 CsCertificate cmdlet 中的指纹, 以确保预期的证书与 HTTPS 绑定正确关联。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


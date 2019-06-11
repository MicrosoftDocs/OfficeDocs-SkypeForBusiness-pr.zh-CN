---
title: 'Lync Server 2013: 配置自动发现的证书'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中配置自动发现的证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-12-12_

Director 池、前端池和反向代理的证书需要其他使用者备用名称条目才能支持与 Lync 客户端的安全连接。

<div>


> [!NOTE]  
> 你可以使用<STRONG>CsCertificate</STRONG> cmdlet 查看有关当前已分配证书的信息。 但是, 默认视图将截断证书的属性, 并且不显示 SubjectAlternativeNames 属性中的所有值。 你可以使用<STRONG>CsCertificate</STRONG> 、CsCertificate 和<STRONG>CsCertificate</STRONG> cmdlet 查看某些信息以及申请和分配证书。 <STRONG></STRONG> 但是, 如果不确定当前证书上的主题备用名称 (SAN) 的属性, 则不是最佳方法。 若要查看证书和所有属性成员, 建议使用<EM>Microsoft 管理控制台 (MMC)</EM>中的 "证书" 管理单元, 或使用 Lync Server 部署向导。 在 Lync Server 部署向导中, 可以使用证书向导查看证书属性。 以下过程详细介绍了如何使用 Lync Server 管理外壳和<EM>Microsoft 管理控制台 (MMC)</EM>查看、请求和分配证书的过程。 若要使用 Lync Server 部署向导, 请参阅此处的详细信息如果已部署可选控制器或控制器池, 请执行以下操作:<A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中配置 Director 的证书</A>。 对于前端服务器或前端池, 请参阅此处的详细信息:<A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中配置服务器的证书</A>。<BR>此过程中的初始步骤是准备步骤, 以指导你确定当前证书扮演的角色。 默认情况下, 证书将没有 lyncdiscover。&lt;sipdomain&gt;或 lyncdiscoverinternal。&lt;内部域名&gt;条目, 除非您之前已安装移动服务或事先已准备好您的证书。 此过程使用示例 SIP 域名 "contoso.com" 和示例内部域名 "contoso.net"。<BR>Lync Server 2013 和 Lync Server 2010 的默认证书配置是将单个证书 (名为 "Default") 用作默认值 (对于除 web 服务之外的所有其他用途), WebServicesExternal 和 WebServicesInternal。 可选配置是对每个用途使用单独的证书。 可通过使用 Lync Server Management Shell 和 Windows PowerShell cmdlet, 或使用 Lync Server 部署向导中的证书向导来管理证书。



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序使用新的主题替换名称更新证书

1.  使用具有本地管理员权限和权限的帐户登录到计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  了解已分配给服务器的证书以及使用哪种类型的证书。 在下一步中需要此信息来分配已更新的证书。 在命令行中键入：
    
        Get-CsCertificate

4.  查看上一步骤的输出, 以查看是否为多个用途分配了一个证书, 或者是否为每个使用分配了不同的证书。 查看 "使用" 参数, 了解如何使用证书。 比较所显示的证书的指纹参数, 以查看相同的证书是否有多个用途。

5.  更新证书。 在命令行中键入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如, 如果**CsCertificate** cmdlet 显示了使用默认值的证书, 另一个使用了 WebServicesInternal 的证书, 而另一个使用 WebServicesExternal, 并且它们都具有相同的指纹值, 请在命令行中键入:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要提示：**
    
    如果为每个使用分配了单独的证书 (指纹值对于每个证书而言不同), 请务必不要使用多个类型运行**CsCertificate** cmdlet。 在这种情况下, 为每次使用单独运行**CsCertificate** cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看证书, 请单击 "**开始**", 单击 "**运行 ...**"。 键入 MMC 以打开 Microsoft 管理控制台。

7.  从 MMC 菜单中, 选择 "**文件**", 选择 "**添加/删除管理单元 ...**", 然后选择 "证书"。 单击“添加”****。 出现提示时, 选择 "**计算机帐户**", 然后单击 "**下一步**"。

8.  如果证书位于此计算机上, 请选择 "**本地计算机**"。 如果证书位于另一台计算机上, 请选择 "**另一**台计算机", 键入计算机的完全限定的域名, 或单击 **"在输入要选择的对象名称"** 中的 "**浏览**", 键入计算机的名称。 单击 "**检查姓名**"。 当解析计算机的名称时, 它将带有下划线。 单击 **"确定**", 然后单击 "**完成**"。 单击 **"确定"** 提交选定内容, 然后关闭 "**添加或删除管理单元**" 对话框。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果该证书未显示在控制台中, 请确保您没有选中 "用户或服务"。 您必须选择 "计算机", 否则您将无法找到 probper 证书。

    
    </div>

9.  若要查看证书的属性, 请展开 "**证书**", 展开 "**个人**", 然后选择 "**证书**"。 选择要查看的证书, 右键单击该证书, 然后选择 "**打开**"。

10. 在 "**证书**" 视图中, 选择 "**详细信息**"。 在此处, 你可以通过选择 "**主题**", 然后显示 "分配的主题名称和关联的属性" 来选择证书主题名称。

11. 若要查看分配的主题备用名称, 请选择 "**主题备用名称**"。 显示所有指定的主题备用名称。 默认情况下, 在属性中找到的 "使用者替换名称" 是 " **DNS 名称**" 类型。 你应该会看到以下成员 (所有这些成员都应是在 DNS 主机中表示的完全限定的域名 (A 或 IPv6 AAAA) 记录:
    
      - 此池的池名称, 如果这不是池, 则为单个服务器名称
    
      - 证书分配到的服务器名称
    
      - 简单的 URL 记录, 通常满足和拨入
    
      - Web 服务内部和 Web 服务外部名称 (例如, webpool01.contoso.net、webpool01.contoso.com), 基于在拓扑生成器和 ridden 的 web 服务选择中所做的选择。
    
      - 如果已分配, 则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。
    
    最后一项是你最感兴趣的项-如果存在 lyncdiscover 和 lyncdiscoverinternal SAN 条目。
    
    获得此信息后, 您可以关闭 "证书" 视图和 MMC。

12. 如果自动发现服务, 即 lyncdiscover。\>域名\>和 lyncdiscoverinternal。\<域名\> (基于外部或内部证书) 缺少使用者备用名称, 并且你使用默认、WebServicesInternal 和 WebServiceExternal 类型的单个默认证书, 请执行以下操作:
    
      - 在 Lync Server Management Shell 命令行提示符处, 键入:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是必须使用 DomainName 参数。 使用 DomainName 参数时, 必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要分配证书, 请键入以下内容:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 "指纹" 是为新颁发的证书显示的指纹。

13. 对于在默认、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现主题备用名称, 请执行下列操作:
    
      - 在 Lync Server Management Shell 命令行提示符处, 键入:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是必须使用 DomainName 参数。 使用 DomainName 参数时, 必须为 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 对于缺少的外部自动发现主题备用名称, 请在命令行中键入:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是必须使用 DomainName 参数。 使用 DomainName 参数时, 必须为 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要分配单个证书类型, 请键入以下内容:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 "指纹" 是为新颁发的单个证书显示的指纹。

</div>

</div>

<span> </span>

</div>

</div>

</div>


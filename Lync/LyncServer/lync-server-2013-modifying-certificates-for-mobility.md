---
title: Lync Server 2013：修改证书以实现移动功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bccb901f241089a21fd7428e28b005f46e157300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>在 Lync Server 2013 中修改证书以实现移动功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-20_

为了支持 Lync 环境和移动客户端之间的安全连接, 你的控制器池、前端池和反向代理的安全套接字层 (SSL) 证书需要使用其他一些主题备用名称进行更新 (SAN) 条目。 如果需要查看有关移动性的证书要求的更多详细信息, 请参阅在[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)中的 "证书要求" 部分, 但基本情况下, 您需要获取新证书证书颁发机构, 其中包含额外的 SAN 条目, 然后使用本文的步骤添加这些证书。

当然, 在开始之前, 最好知道您的证书已有哪些主题备用名称。 如果您不确定已配置的内容, 可以通过多种方式来了解。虽然该选项的运行**CsCertificate**和其他 PowerShell 命令可查看此信息 (我们将在下面遍历), 但默认情况下将截断数据, 因此你可能无法看到所需的所有属性。 为了更好地查看证书及其所有属性, 您可以转到 Microsoft 管理控制台 (MMC) 并加载 "证书" 管理单元 (我们还将在下面遍历), 或者只需在 Lync Server 部署向导中进行检查。

如上所述, 以下步骤将指导你使用 Lync Server Management Shell 和 MMC 更新证书。 如果您对使用 Lync Server 部署向导中的 "证书向导" 感兴趣, 则可以在 "为 Director" 或 "控制器池"[配置 Lync server 2013 中的 director 的证书](lync-server-2013-configure-certificates-for-the-director.md), 前提是您配置了一个控制器或控制器池 (您可能不有)。 对于前端服务器或前端池, 你需要[在 Lync server 2013 中查看 "配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)"。

需要记住的最后一件事是, 你可能在 Lync Server 2013 环境中拥有单个默认证书, 或者你可能具有单独的默认证书 (即除 web 服务之外的所有内容)、WebServicesExternal 和 WebServicesInternal。 无论您的配置如何, 这些步骤都应帮助您解决问题。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序使用新的主题替换名称更新证书

1.  您需要使用具有本地管理员权限的帐户登录到您的 Lync Server 2013 服务器。 此外, 如果你在步骤12和更高版本中运行 PowerShell**请求 CsCertificate** , 该帐户需要拥有指定的证书颁发机构 (CA) 的权限。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  在分配已更新的证书之前, 需要了解已分配给服务器的证书以及使用的类型。 在命令行中键入：
    
        Get-CsCertificate

4.  查看上一步的输出以查看是否已为多个使用分配了单个证书, 或者是否为每个使用分配了不同的证书。 查看 "使用" 参数以了解使用证书的方式。 比较所显示的证书的指纹参数, 以查看相同的证书是否有多个用途。 随时关注指纹参数。

5.  更新证书。 在命令行中键入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如, 如果**CsCertificate** cmdlet 显示了使用默认值的证书, 而另一个使用了 WebServicesInternal 的证书, 而另一个使用 WebServicesExternal, 并且它们都具有相同的指纹值, 则应在命令行中处理器类型
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要提示：**
    
    如果为每个使用分配了单独的证书 (因此您在上面检查的指纹值对于每个证书都不同), 请务必**不要**运行具有多个类型的**CsCertificate** cmdlet, 如上述示例中所示。 在这种情况下, 为每次使用单独运行**CsCertificate** cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  要查看证书 (或证书), 请单击 "**开始**", 然后单击 "**运行 ...**"。 键入 MMC 以打开 Microsoft 管理控制台。

7.  从 MMC 菜单中, 选择 "**文件**", 选择 "**添加/删除管理单元 ...**", 然后选择 "证书"。 单击“添加”****。 出现提示时, 选择 "**计算机帐户**", 然后单击 "**下一步**"。

8.  如果这是证书所在的服务器, 请选择 "**本地计算机**"。 如果证书位于另一台计算机上, 你应该选择 "**另一台计算机**", 然后可以键入计算机的完全限定的域名, 或单击 **"在输入对象名称进行****浏览**", 然后键入要选择的对象名称。计算机。 单击 "**检查姓名**"。 当计算机的名称解析时, 它将带有下划线。 单击 **"确定**", 然后单击 "**完成**"。 单击 **"确定"** 提交选定内容, 然后关闭 "**添加或删除管理单元**" 对话框。

9.  若要查看证书的属性, 请展开 "**证书**", 展开 "**个人**", 然后选择 "**证书**"。 选择要查看的证书, 右键单击该证书, 然后选择 "**打开**"。

10. 在 "**证书**" 视图中, 选择 "**详细信息**"。 在此处, 你可以通过选择 "**主题**", 然后显示 "分配的主题名称和关联的属性" 来选择证书主题名称。

11. 若要查看分配的主题备用名称, 请选择 "**主题备用名称**"。 所有指定的主题备用名称都将显示在此处。 此处找到的 "主题备用名称" 默认为 " **DNS 名称**" 类型。 你应该会看到以下成员 (所有这些成员都应是在 DNS 主机中表示的完全限定的域名 (A 或 IPv6 AAAA) 记录:
    
      - 此池的池名称, 如果不是池, 则为单个服务器名称
    
      - 证书分配到的服务器名称
    
      - 简单的 URL 记录, 通常满足和拨入
    
      - Web 服务内部和 Web 服务外部名称 (例如, webpool01.contoso.net、webpool01.contoso.com), 基于在拓扑生成器和 ridden 的 web 服务选择中所做的选择。
    
      - 如果已分配, 则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。
    
    最后一项是你最感兴趣的项-如果存在 lyncdiscover 和 lyncdiscoverinternal SAN 条目。
    
    如果您有多个要检查的证书, 请重复这些步骤。 获得此信息后, 您可以关闭 "证书" 视图和 MMC。

12. 如果缺少自动发现服务使用者备用名称, 并且你对默认、WebServicesInternal 和 WebServiceExternal 类型使用的是单个默认证书, 请执行以下操作:
    
      - 在 Lync Server Management Shell 命令行提示符处, 键入:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是需要使用 DomainName 参数。 使用 DomainName 参数时, 您必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要分配证书, 请键入以下内容:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 "指纹" 是为新颁发的证书显示的指纹。

13. 对于在默认、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现 SAN, 请执行以下操作:
    
      - 在 Lync Server Management Shell 命令行提示符处, 键入:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是需要使用 DomainName 参数。 使用 DomainName 参数时, 您必须为 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 对于缺少的外部自动发现主题备用名称, 请在命令行中键入:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域, 则不能使用新的 AllSipDomain 参数。 而是需要使用 DomainName 参数。 使用 DomainName 参数时, 您必须为 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要分配单个证书类型, 请键入以下内容:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 "指纹" 是为新颁发的单个证书显示的指纹。
    
    <div>
    

    > [!NOTE]  
    > 请注意, 仅当运行步骤12和13的帐户有权访问具有相应权限的证书颁发机构时, 才应运行步骤12和13。 如果无法使用获得这些权限的帐户进行登录, 或者如果你使用的是证书的公共或远程证书颁发机构, 则需要通过 Lync Server 部署向导请求它们, 该向导将在下文.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


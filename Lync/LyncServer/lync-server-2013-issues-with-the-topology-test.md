---
title: 拓扑测试的问题
TOCTitle: 拓扑测试的问题
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205045(v=OCS.15)
ms:contentKeyID: 49313440
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 拓扑测试的问题

 

_**上一次修改主题：** 2012-09-21_

与 **Test-CsTopology** cmdlet 相似，最佳做法分析器提供了验证 Lync Server 2013 是否在全局级别正常运行的方法。默认情况下，最佳做法分析器（如 cmdlet）将检查整个 Lync Server 2013 基础结构，并验证所需服务是否在运行以及是否为这些服务和在安装 Lync Server 2013 时创建的通用安全组设置了适当的用户权限。

除了验证 Lync Server 整体的有效性，**Test-CsTopology** 还将检查特定服务的有效性。有关使用此 cmdlet 测试特定服务的详细信息，请参阅 Lync Server 命令行管理程序文档中的[Test-CsTopology](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTopology)。使用以下信息可帮助解决您的拓扑问题。

> [!NOTE]  
> 最佳做法分析器可能无法访问和扫描您的边缘服务器，具体取决于您的边缘服务器的配置和任何相关外围网络设置（包括防火墙设置和权限）。如果将边缘服务器包含在扫描中并且报告指示访问边缘服务器时出现问题，请清除“边缘服务器”复选框并重新运行扫描以防止报告中出现问题。



## 解决拓扑问题

如果拓扑测试发现您的拓扑有问题，那么这些问题可能由您在发布或启用拓扑时发生的问题导致。

对拓扑进行更改时，仅当发布和启用了这些更改，它们才会生效。您必须使用拓扑生成器进行拓扑更改。做出更改后，您随后可以使用拓扑生成器发布和启用这些更改。

在发布更改时，新信息（例如，新站点或新服务器角色）将写入到中央管理存储。但是，这些新（或最新修改的）对象不会立即加入您的拓扑。仅当启用了已更新的拓扑，对象才会加入您的拓扑。如果您选择拓扑生成器中的“发布”选项，则会同时发生以下两个步骤：发布更改（即写入到中央管理存储），然后启用新拓扑。

默认情况下，RTCUniversalServerAdmins 组的成员有权运行 **Publish-CsTopology** cmdlet 和 **Enable-CsTopology** cmdlet。但是，如果尚未委派安装权限，您必须以域管理员身份登录才能运行 **Publish-CsTopology**。若要为 RTCUniversalServerAdmins 授予实际使用 **Publish-CsTopology** cmdlet 的权限，您必须对每个包含运行 Lync Server 服务的计算机的 Active Directory 容器运行 **Grant-CsSetupPermission** cmdlet。若要为 RTCUniversalServerAdmins 授予使用 **Enable-CsTopology** cmdlet 的权限，您必须针对每个包含运行 Lync Server 服务的计算机的 Active Directory 域服务容器运行 **Set-CsSetupPermission** cmdlet。请注意，这适用于使用拓扑生成器启用和发布拓扑。如果尚未使用 **Set-CsSetupPermission** 委派权限，则只有域管理员能通过拓扑生成器启用和发布拓扑。


---
title: 定义和配置前端池或 Standard Edition 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52b7e4fcbcce1c297036e7b1e2862e680c4d86cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-08_

此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。

如果要部署企业服务器，池中的最少前端服务器数必须始终处于运行状态。 下表总结了这些要求。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端服务器总数</th>
<th>要使池正常工作所必须运行的服务器的数目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>双面</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>第三章</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 对于 Lync Server 2013，无论何时在池中添加或删除前端服务器，都必须重新启动服务。 删除和添加服务器应作为独立操作来完成。 例如，如果您打算添加两台前端服务器并删除两台前端服务器，请使用以下过程： 
> <OL>
> <LI>
> <P>删除两台前端服务器。</P>
> <LI>
> <P>发布并重新激活拓扑。</P>
> <LI>
> <P>重新启动服务</P>
> <LI>
> <P>添加两台前端服务器。</P>
> <LI>
> <P>发布并重新激活拓扑。</P>
> <LI>
> <P>重新启动服务。</P></LI></OL>



</div>

定义拓扑之后，请使用以下过程为您的网站定义前端池。 有关定义拓扑的详细信息，请参阅[在拓扑生成器中定义和配置拓扑以使用 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

<div>

## <a name="to-define-a-front-end-pool"></a>定义前端池

1.  在“定义新的前端池”向导的 **“定义新的前端池”** 页上，单击 **“下一步”**。

2.  在 "**定义前端池 FQDN** " 页上，为要创建的池输入完全限定的域名（FQDN），单击 " **Enterprise Edition 前端池**"，然后单击 "**下一步**"。

3.  在 "**定义此池中的计算机**" 页上，为池中的第一个前端服务器输入计算机 FQDN，然后单击 "**添加**"。 对要添加到池中的任何其他计算机（最多12个）重复此步骤，然后单击 "**下一步**"。

4.  在“选择功能”**** 页上，选中希望此前端池具有的功能的复选框。 例如，如果仅部署即时消息（IM）和状态功能，则应选中 "**会议**" 复选框以允许多方 IM，但不会选择 "**拨入（PSTN）会议**"、"**企业语音**" 或 "**呼叫允许控制**" 复选框，因为它们代表语音、视频和协作会议功能。
    
      - **会议**   此选择启用了一组丰富的功能，包括：
        
          - IM 会话中多于两方的即时消息。
        
          - 包括文档协作、应用程序共享和桌面共享的会议。
        
          - A/V 会议，使用户可以在不需要外部服务（如 Live Meeting 服务或第三方音频网桥）的情况下进行实时音频/视频（A/V）会议。
    
      - **拨入（pstn）会议**   允许用户使用公用电话交换网（pstn）电话加入 Lync Server 2013 会议的音频部分，而无需音频会议提供商。
    
      - **企业语音**   企业语音是 Lync Server 2013 中的 IP 语音（VoIP）解决方案，允许用户拨打和接听电话呼叫。 如果计划将 Lync Server 2013 用于语音呼叫、语音邮件和其他使用硬件设备或软件客户端的功能，则应部署此功能。
    
      - **呼叫允许控制（CAC）**   CAC 根据可用的网络带宽确定是否允许建立实时通信会话（如语音或视频呼叫）。 如果仅部署 IM 和状态，则无需 CAC，因为这两个功能都不使用 CAC。
    
      - **存档**   存档为你提供一种方式来存档 IM 内容、会议（会议）内容，或同时通过 Lync Server 2013 发送这两者。
    
      - **通过监控**   监控服务器，可以收集描述网络和终结点上媒体质量的数字数据、VoIP 呼叫、IM 消息、A/V 对话、会议、应用程序共享和文件传输的使用情况信息，以及失败呼叫的呼叫错误和故障排除信息。
    
    <div>
    

    > [!NOTE]
    > 如果要在部署中启用 CAC，则需要在每个中央站点的一个池中启用 CAC。如果要部署语音功能或 A/V 会议，建议使用 CAC。

    
    </div>
    
    下表显示了可用功能（顶部）和为用户提供的功能（左侧）。表中的选择是为组织启用这些功能所需选择的内容。
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>会议</th>
    <th>电话拨入式会议</th>
    <th>Enterprise Voice</th>
    <th>呼叫允许控制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>即时消息和状态</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>企业语音</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  在 "**选择并置服务器角色**" 页上，您可以在前端服务器上并置中介服务器，也可以将其作为独立服务器进行部署。
    
    您可以在前端池上并置中介服务器。
    
      - 如果打算在 Enterprise Edition 前端池上并置中介服务器，请确保选中 "" 复选框。 将在池服务器上部署服务器角色。
    
      - 如果打算将中介服务器作为独立服务器进行部署，请清除相应的复选框。 在完全部署前端服务器之后，您将在单独的部署步骤中部署中介服务器。
    
    <div>
    

    > [!NOTE]
    > 我们建议在可能时并置中介服务器。 有关并置或独立中介服务器支持的详细信息，请参阅规划文档中的<A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 中的中介服务器组件和拓扑</A>。

    
    </div>

6.  "**将服务器角色与此前端池关联**" 页允许您定义服务器角色并将其与前端池相关联。 以下角色可用：
    
    **启用边缘池**   定义和关联单个边缘服务器或边缘服务器池。 边缘服务器可促进组织内部的用户与组织外部的人员之间的通信和协作，包括联合用户。
    
    您可以使用两种方案来部署和关联服务器角色：
    
    方案一，为新的安装定义新的拓扑。可以使用两种方法之一完成安装：
    
      - 清除相应复选框，然后继续定义拓扑。 在发布、配置并测试了前端和后端服务器角色之后，可以再次运行拓扑生成器以将角色服务器添加到拓扑中。 通过此策略，您可以测试运行 SQL Server 的前端池和服务器，而不会增加其他角色的复杂性。 完成初始测试后，可以再次运行拓扑生成器以选择需要部署的角色。
    
      - 选择需要安装的角色，然后设置硬件以适应所选择的角色。
    
    对于第二种方案，您有现有的部署和基础结构已准备好使用新角色，或者您需要将现有角色与新的前端服务器相关联：
    
      - 在这种情况下，您将选择要部署或与新的前端服务器关联的角色。 无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。

7.  在“定义 SQL 存储”**** 页上，执行下列操作之一：
    
      - 若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“SQL 存储”**** 中的一个实例。
    
      - 若要定义新的 SQL Server 实例以存储池信息，请单击 "**新建**"，然后在 "**定义新的 sql 存储**" 对话框中指定**SQL Server FQDN**。
    
      - 要指定 SQL Server 实例的名称，请选择“命名实例”****，然后指定实例的名称。
    
      - 要使用默认实例，请单击“默认实例”****。
    
      - 若要使用 SQL 镜像，请选择“启用 SQL 镜像”****，选择现有实例或创建一个新实例。

8.  在“定义文件共享”**** 页上，执行以下操作之一：
    
      - 要使用已经在拓扑中定义的文件共享，请选择“使用先前定义的文件共享”****。
    
      - 要定义新文件共享，请选择“定义新的文件共享”****，在“文件服务器 FQDN”**** 框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“文件共享”**** 框中输入文件共享的名称。
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 的文件共享不能位于前端服务器上。 请注意，在此示例中，文件共享位于基于 SQL Server 的后端服务器上。 根据组织要求，这可能不是最佳位置，文件服务器可能是更好的选择。 可以在尚未创建文件共享的情况下定义文件共享。 在发布拓扑之前，您将需要在定义的位置创建文件共享。

    
    </div>

9.  在“指定 Web 服务 URL”**** 页上，执行以下一项或两项操作：
    
    <div>
    

    > [!IMPORTANT]
    > 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net，则基 url 为 pool01.contoso.net。

    
    </div>
    
    <div>
    

    > [!WARNING]
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>，则不能将<STRONG>pool01.contoso.com</STRONG>用于另一个前端池或前端服务器。

    
    </div>
    
    1.  如果要配置 DNS 负载平衡，请选中 "**覆盖内部 Web 服务池 FQDN** " 复选框，输入内部基本 url 中的内部基本 url （该 url 必须与池 FQDN 不同，例如，内部-\<你的基本\>url） **。**
        
        <div>
        

        > [!WARNING]
        > 如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。 定义 Url 或完全限定的域名时，<STRONG>仅使用标准字符</STRONG>（包括 a – z、a – z、0–9和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 Ca 通常不支持 URL 或 FQDN 中的非标准字符（即，在必须将 URL 或 FQDN 分配给证书中的使用者名称或使用者备用名称时）。

        
        </div>
    
    2.  （可选）在“外部基 URL”**** 中输入外部基 URL。 您可以输入外部基 URL 以将其与内部域命名区分开来。 例如，内部域是 contoso.net，但外部域名是 contoso.com。 则可以使用 contoso.com 域名来定义 URL。 如果是反向代理，这也很重要。 外部基 URL 域名应该与反向代理的 FQDN 域名相同。 即时消息和状态确实需要对前端池的 HTTP 访问。
    
    <div>
    

    > [!NOTE]
    > 要使用 DNS 负载平衡，必须创建相应的 DNS 记录。 有关详细信息，请参阅<A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中为负载平衡配置 DNS</A>。

    
    </div>

10. 如果您在 "**选择功能**" 页上选择了 "**会议**"，请在 "**选择 office web apps server** " 页上选择 "**将池与 Office web apps 服务器关联**"，然后单击 "**新建**" （或从下拉列表中选择现有的 Office Web Apps Server）。

11. 在“定义新的 Office Web Apps 服务器”**** 对话框的“Office Web Apps 服务器 FQDN”**** 框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”**** 框中。
    
    如果 Office Web Apps Server 安装在本地和与 Lync Server 2013 位于同一网络区域中，则不应选择在**外部网络（即，外围/Internet）中部署 "Office Web Apps 服务器**" 选项。
    
    如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”****。
    
    <div>
    

    > [!NOTE]
    > 有关详细信息，请参阅<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync Server 2013 的集成</A>。

    
    </div>

12. 在“定义存档 SQL 存储”**** 页上，选择一个现有实例或 SQL Server，或定义新实例来存储与存档数据关联的数据。

13. 在“定义监控 SQL 存储”**** 页上，选择一个现有实例或 SQL Server，或定义新实例来存储与监控数据关联的数据。

14. 单击“下一步”****。 如果在 "**将服务器角色与此前端池关联**" 页上定义了其他角色服务器，则将打开 "单独角色配置向导" 页，以允许您配置服务器角色。 有关详细信息，请参阅下文：
    
    [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)

15. 如果未选择要配置和部署的其他服务器角色，或者已经完成其他角色服务器的配置，请单击“完成”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>


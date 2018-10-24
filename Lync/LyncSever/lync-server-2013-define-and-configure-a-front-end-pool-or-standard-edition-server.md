---
title: Lync Server 2013：定义和配置前端池或 Standard Edition 服务器
TOCTitle: 定义和配置前端池或 Standard Edition 服务器
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398538(v=OCS.15)
ms:contentKeyID: 49313212
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器

 

_**上一次修改主题：** 2015-03-09_

此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。

如果部署企业服务器，则池中必须有最少数量的 前端服务器一直运行。下表总结了这些要求。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中前端服务器的总数</th>
<th>使池发挥作用所必须运行的服务器的数量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 -2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3 -4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5 -6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7 -8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9 -10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11 -12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 对于 Lync Server 2013，无论何时在池中添加或删除前端服务器，均必须重新启动服务。删除和添加服务器应作为独立操作来完成。例如，如果要添加两台前端服务器，并删除两台前端服务器，请使用以下过程：
<ol>
<li><p>删除两台前端服务器。</p></li>
<li><p>发布并重新激活拓扑。</p></li>
<li><p>重新启动服务</p></li>
<li><p>添加两台前端服务器。</p></li>
<li><p>发布并重新激活拓扑。</p></li>
<li><p>重新启动服务。</p></li>
</ol>



定义拓扑之后，请使用以下过程为站点定义 前端池。有关定义拓扑的详细信息，请参阅 [在 Lync Server 2013 拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

## 定义 前端池

1.  在“定义新的前端池”向导的“定义新的 前端池”页上，单击“下一步”。

2.  在“定义 前端池 FQDN”页上，输入要创建的池的完全限定域名 (FQDN)，单击“Enterprise Edition 前端池”，然后单击“下一步”。

3.  在“定义此池中的计算机”页上，输入此池中第一台前端服务器的计算机 FQDN，然后单击“添加”。对要添加到此池中的任何其他计算机（最多 8 台）重复此步骤，然后单击“下一步”。

4.  在“选择功能”页上，选中希望此前端池具有的功能的复选框。例如，如果您仅部署即时消息 (IM) 和状态功能，可以选中“会议”复选框以允许多方 IM，但不能选中“电话拨入式 (PSTN) 会议”、“企业语音”或“呼叫允许控制”复选框，因为它们代表语音、视频和协作会议功能。
    
      - **会议**   此选项启用一组丰富的功能，包括：
        
          - IM 会话中多于两方的即时消息。
        
          - 包括文档协作、应用程序共享和桌面共享的会议。
        
          - A/V 会议，无需外部服务（如 Live Meeting 服务或第三方音频桥）即可使用户进行实时音频/视频 (A/V) 会议。
    
      - **电话拨入式 (PSTN) 会议**   使用户能够通过使用公用电话交换网 (PSTN) 电话来加入 Lync Server 2013 会议的音频部分，而无需音频会议提供商。
    
      - **企业语音**   企业语音是 Lync Server 2013 中的 IP 语音 (VoIP) 解决方案，允许用户发起和接收电话呼叫。如果打算使用 Lync Server 2013 执行语音呼叫、语音邮件以及使用硬件设备或软件客户端的其他功能，则可以部署此功能。
    
      - **呼叫允许控制 (CAC)**   CAC 根据可用网络带宽确定是否允许建立实时通信会话（如语音呼叫或视频呼叫）。如果仅部署 IM 和状态，则无需 CAC，因为这两个功能都不使用 CAC。
    
      - **存档**   存档可让您存档通过 Lync Server 2013 发送的 IM 内容、会议内容或同时存档两者。
    
      - **监控**   通过监控服务器可以收集描述网络和终结点上的媒体质量的数值数据、与 VoIP 呼叫、IM 消息、A/V 对话、会议、应用程序共享和文件传输有关的用法信息，以及失败呼叫的呼叫错误和故障排除信息。
    
    > [!NOTE]  
    > 如果要在部署中启用 CAC，则需要在每个中央站点的一个池中启用 CAC。如果要部署语音功能或 A/V 会议，建议使用 CAC。
    
    
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
    <th>企业语音</th>
    <th>呼叫允许控制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>即时消息和状态</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="even">
    <td><p>会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="odd">
    <td><p>A/V 会议</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>企业语音</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  在“选择并置服务器角色”页上，可在前端服务器上并置中介服务器，或者将其部署为独立服务器。
    
    可在 前端池上并置 中介服务器。
    
      - 如果计划在 Enterprise Edition 前端池上并置 中介服务器，请确保选中相应的复选框。将在池服务器上部署服务器角色。
    
      - 如果计划将 中介服务器部署为独立服务器，则清除相应的复选框。在部署 前端服务器完成之后，将以单独的部署步骤部署 中介服务器。
    
    > [!NOTE]  
    > 我们建议在可能时并置中介服务器。有关对并置或单独的中介服务器的支持的详细信息，请参阅规划文档中的 <a href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync Server 2013 中中介服务器的组件和拓扑</a>。
    


6.  通过“将服务器角色与此前端池关联”页可以定义服务器角色并将服务器角色与 前端池关联。以下角色可用：
    
    **启用 边缘池**   定义并关联单个 边缘服务器或边缘服务器池。 边缘服务器为组织内的用户和组织外的用户（包括联盟用户）进行通信和协作提供方便。
    
    您可以使用两种方案来部署和关联服务器角色：
    
    方案一，为新的安装定义新的拓扑。可以使用两种方法之一完成安装：
    
      - 清除相应复选框，然后继续定义拓扑。在发布、配置、测试前端和后端服务器角色之后，您可以再次运行拓扑生成器以将角色服务器添加到拓扑中。此策略允许您测试前端池和运行 SQL Server 的服务器，而没有其他角色所带来的复杂性。完成初始测试后，可以再次运行拓扑生成器来选择需要部署的角色。
    
      - 选择需要安装的角色，然后设置硬件以适应所选择的角色。
    
    对于方案二，您具有现有的部署，并且您的基础架构已为新角色做好准备，或者，您需要将现有角色与新的 前端服务器关联：
    
      - 在这种情况下，需选择打算部署的角色或要与新的 前端服务器相关联的角色。无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。

7.  在“定义 SQL 存储”页上，执行下列操作之一：
    
      - 若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“SQL 存储”中的一个实例。
    
      - 若要定义新的 SQL Server 实例来存储池信息，请单击“新建”，然后在“定义新的 SQL 存储”对话框中指定“SQL Server FQDN”。
    
      - 要指定 SQL Server 实例的名称，请选择“命名实例”，然后指定实例的名称。
    
      - 要使用默认实例，请单击“默认实例”。
    
      - 若要使用 SQL 镜像，请选择“启用 SQL 镜像”，选择现有实例或创建一个新实例。

8.  在“定义文件共享”页上，执行以下操作之一：
    
      - 要使用已经在拓扑中定义的文件共享，请选择“使用先前定义的文件共享”。
    
      - 要定义新文件共享，请选择“定义新的文件共享”，在“文件服务器 FQDN”框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“文件共享”框中输入文件共享的名称。
    
    > [!IMPORTANT]
    > Lync Server 2013 的文件共享不能位于 前端服务器上。请注意，在此示例中，文件共享位于基于 SQL Server 的后端服务器上。根据组织要求，这可能不是最佳位置，文件服务器可能是更好的选择。可以在尚未创建文件共享的情况下定义文件共享。在发布拓扑之前，您将需要在定义的位置创建文件共享。


9.  在“指定 Web 服务 URL”页上，执行以下一项或两项操作：
    
    > [!IMPORTANT]
    > 基 URL 指的是 URL 的 Web 服务标识减去 https://。例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。
    
    > [!WARNING]
    > 如果您拥有多个 前端池或 前端服务器，则外部 Web 服务 FQDN 必须是唯一的。例如，如果将 前端服务器的外部 Web 服务 FQDN 定义为 <strong>pool01.contoso.com</strong>，则不能将 <strong>pool01.contoso.com</strong> 用于另一个 前端池或 前端服务器。
    
    1.  如果要配置 DNS 负载平衡，请选中“覆盖内部 Web 服务池 FQDN”复选框，在“内部基 URL”中输入内部基 URL（必须不同于池 FQDN，例如，“internal-\<基 URL\>”）。
        
        > [!WARNING]  
		> 如果决定使用自定义的 FQDN 替代内部 Web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池的不同。定义 URL 或完全限定的域名时<strong>仅使用标准字符</strong>（包括 A–Z、a–z、0–9 和连字符）。不要使用 Unicode 字符或下划线。外部 DNS 和公共 CA 通常不支持在 URL 或 FQDN 中使用非标准字符（即，当必须向证书中的使用者名称或使用者替代名称分配 URL 或 FQDN 时）。
    
    2.  （可选）在“外部基 URL”中输入外部基 URL。您可以输入外部基 URL 以将其与内部域命名区分开来。例如，内部域是 contoso.net，但外部域名是 contoso.com。则可以使用 contoso.com 域名来定义 URL。如果是反向代理，这也很重要。外部基 URL 域名应该与反向代理的 FQDN 域名相同。即时消息和状态需要对前端池的 HTTP 访问。
    
    > [!NOTE]  
    > 要使用 DNS 负载平衡，必须创建相应的 DNS 记录。有关详细信息，请参阅 <a href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中配置 DNS 负载平衡</a>。
    


10. 如果在“选择功能”页上选择“会议”，请在“选择 Office Web Apps 服务器”页上选择“将池与 Office Web Apps 服务器关联”，然后单击“新建”（或从下拉列表中选择现有 Office Web Apps Server）。

11. 在“定义新的 Office Web Apps 服务器”对话框中，在“Office Web Apps 服务器 FQDN”框中键入 Office Web Apps Server 计算机的完全限定域名 (FQDN)；执行此操作时，会将 Office Web Apps Server 发现 URL 自动输入“Office Web Apps 服务器发现 URL”框中。
    
    如果本地安装 Office Web Apps Server 且位于 Lync Server 2013 所在的同一网络区域中，则不应选择选项“在外部网络(即外围/Internet)中部署 Office Web Apps 服务器”。
    
    如果在内部防火墙的外部部署 Office Web Apps Server，则选择选项“在外部网络（即外围/Internet）中部署 Office Web Apps 服务器”。
    
    > [!NOTE]  
    > 有关详细信息，请参阅 <a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps Server 和 Lync Server 2013 的集成</a>。
    


12. 在“定义存档 SQL 存储”页上，选择一个现有实例或 SQL Server，或定义新实例来存储与存档数据关联的数据。

13. 在“定义监控 SQL 存储”页上，选择一个现有实例或 SQL Server，或定义新实例来存储与监控数据关联的数据。

14. 单击“下一步”。如果在“将服务器角色与此前端池关联”页上定义了其他角色服务器，将打开单独的角色配置向导页，以使您能够配置服务器角色。有关详细信息，请参阅下文：
    
    [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)

15. 如果未选择要配置和部署的其他服务器角色，或者已经完成其他角色服务器的配置，请单击“完成”。


---
title: 创建用户和联系人
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a911124af0ac4dc57eca01e0ef6e2a801a61caa5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505219"
---
# <a name="create-users-and-contacts"></a>创建用户和联系人

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

您必须使用 Lync Server 2013 用户预配工具 ( # A0) 在准备压力和性能负载测试的过程中创建用户和联系人。

下面是您在阅读本主题时可能会用到的术语和定义的列表。

  - 组织单位– Active Directory 域服务组织单位 (OU) 。

  - 联合/跨池–将启用的用户通过其他即时消息 (IM) 服务（如 Internet 服务的 MSN 网络、AOL®和 Yahoo®）与用户进行通信 \! 。

  - 通讯组列表–包含 Active Directory 域服务用户列表的 Active Directory 域服务中的对象，用于启动与一组用户的通信。

  - Location Info Service – Lync Server 2013 服务，在每个电话启用和配置该服务后，可以检索增强 9-1-1 (E9-1-1) 服务的物理位置。

  - 美国电话号码–分配给用户的电话号码，以及用于路由入站和出站呼叫和反向号码查找 (RNL) 的 SIP URI。

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>使用 UserProvisioningTool.exe 创建用户和联系人

必须使用 Lync Server 用户预配工具为负载模拟创建用户和联系人。 Lync Server 用户预配工具随 Lync Server 压力和性能工具包一起安装。 请确保已在前端服务器或 Standard Edition server 上运行 ( # A0) 的程序包安装程序。 在 \\ 前端服务器或 Standard Edition 服务器上运行文件 UserProvisioningTool.exe (位于% InstalledDirectory% LyncStressAndPerfTool LyncStress) ，启动 Lync Server 用户预配工具。

<div>


> [!IMPORTANT]  
> 您必须以域管理员安全组成员的身份登录才能运行 UserProvisioningTool.exe。 由于 UserProvisioningTool.exe 将创建和配置新的 Active Directory 域服务用户，因此需要从该上下文运行此上下文。



</div>

<div>


> [!NOTE]  
> 当您创建大量 (10000 或更多) 的用户时，请从高端计算机运行 UserProvisioningTool.exe。 请注意，在创建用户时，域控制器也会遇到负载较高的情况。



</div>

当 Lync Server 用户预配工具打开时，单击 " **配置** "，然后选择 " **加载配置**"。 若要开始配置用户和联系人，请加载程序包中包含的默认文件 SampleData.xml。 这将预填充包含您的系统需要修改的示例数据的字段。 如果已预配置的 XML 文件已包含自定义设置，则改为加载该文件。 填写 Lync Server 用户预配工具中的字段，如以下各节所述。

!["用户创建" 选项卡。](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg ""用户创建" 选项卡。")

若要配置服务器选项，请按照以下步骤操作。

1.  在 " **前端池 FQDN**" 中，键入要在其中承载用户的 Standard Edition Server 或前端池 (FQDN) 的完全限定的域名称。

2.  在 " **用户名前缀**" 中，键入要用于出于测试目的生成用户名的前缀。

3.  在 " **密码**" 中，指定将应用于所有测试用户帐户的密码。

4.  在 " **SIP 域**" 中，键入要用于测试用户的 SIP Uri (统一资源标识符 ") 的域名。

5.  在 " **帐户域**" 中，键入您要在其中创建测试用户的当前 Active Directory 域服务域的域名。

6.  在 " **组织单位**" 中，键入要在其中创建用户对象的 Active Directory 域服务 OU 的名称。 如果 OU 不存在，则会创建它。

7.  在 " **电话区号**" 中，键入将用于测试用户帐户的三位数区域代码。 确保电话区号不会与 Active Directory 域服务中的任何其他用户的区号发生冲突。

8.  如果要为测试用户启用企业语音，请选中 " **已启用语音** " 复选框。

9.  在 " **用户数**" 中，指定要创建的测试用户的总数。

10. 在 " **起始索引**" 中，指定将用作用户名前缀的后缀的起始编号。

<div>

## <a name="create-users-button"></a>"创建用户" 按钮

当您单击 "创建用户" 按钮时，它将验证所有输入参数。

  - 如果存在任何验证错误，它将提示您更正这些输入值。

  - 如果所有输入值都是正确的，则会开始在 Active Directory 域服务中创建用户。 将在此窗体的底部显示一个进度栏。 我们建议您不要在进度栏处于活动状态时关闭应用程序。

用户创建过程较慢。 可能需要几分钟的时间。 如果用户数量非常大，该过程甚至可能需要几个小时的时间。 如果用户已存在，则会使用任何更改对其进行更新。 您可以通过登录为范围中的用户之一来验证用户是否已创建。 使用用户前缀、用户号和 @sipDomain 作为用户名 (例如，LyncUser10@contoso.net) ，以及指定的密码。

</div>

<div>

## <a name="delete-users-button"></a>"删除用户" 按钮

当您单击 "删除用户" 按钮时，它将验证所有输入参数。

  - 如果存在任何验证错误，它将提示您更正这些输入值。

  - 如果所有输入值都是正确的，它将在 Active Directory 域服务中开始禁用和删除用户。 将在此窗体的底部显示一个进度栏。 我们建议您不要在进度栏处于活动状态时关闭应用程序。

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>仅支持美国格式的电话号码。 始终将电话号码分配给用户，并且由 UserProvisioningTool.exe 创建的所有用户均可为企业语音启用。 任何使用电话号码的方案（如会议自动助理或 UC-PSTN 呼叫），都可以使用此电话号码正确路由呼叫。 因此，每个用户必须具有唯一的电话号码。 如果您必须创建两次用户，则该命令将失败，除非您使用不同的区号，或者以前的用户已通过使用 <STRONG>get-csuser</STRONG> cmdlet 禁用。</P>
> <LI>
> <P>在创建联系人之前，必须首先完成从 "用户" 选项卡执行的用户复制。如果你刚刚创建了用户，则必须等到 Lync Server 复制完成，并填充数据库中的用户帐户。 如果用户尚未完成复制，您将看到错误。 如果安装了 Lync Server 2013 前端服务，或者在最后一个用户上成功运行 <STRONG>get-csuser</STRONG> cmdlet，您将知道用户何时完成复制。</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>联系人创建选项卡

通过 "联系人创建" 选项卡，可以指定用户联系人的详细信息。

!["联系人创建" 选项卡。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg ""联系人创建" 选项卡。")

若要配置用户的联系人，请执行以下步骤。

1.  在 "每个用户的平均联系人" 中，指定要在联系人列表中为每个用户填充的平均联系人数。

2.  如果要为每个用户创建相等数量的联系人，请选中 "固定" 复选框。 如果要改变为用户创建的联系人数量，请清除该复选框。

3.  在 "每个用户的平均联系人组" 中，指定每个用户的联系人组数。 此数字必须小于每个用户的平均联系人数。

4.  在 "联合/跨池联系人百分比" 中，指定一个介于0和100之间的数字。 将使用联合用户创建此联系人百分比。

5.  在 "联合/跨池用户前缀" 中，指定将添加到本地用户的联系人列表中的联盟用户的用户名。

6.  在联合/跨池用户 SIP 域中，指定联盟用户的 SIP 域名称。
    
    <div>
    

    > [!NOTE]  
    > 创建联系人时不应登录任何用户。

    
    </div>

7.  在 "用户创建" 选项卡中，验证参数是否正确。 将为其创建联系人的用户的范围是从 "用户创建" 选项卡获取的。

8.  单击 "创建联系人" 以开始创建联系人。 此过程可能需要几分钟时间。 完成后，将显示一个对话框，其中包含 "操作已成功完成" 的消息。 您可以通过以用户创建选项卡上创建的用户的登录方式来验证所创建的联系人。
    
    <div>
    

    > [!NOTE]  
    > 创建联系人后，此工具将重新启动目标池中的所有前端服务器。 它可能需要更长时间 (2 小时) 才能启动前端服务器，具体取决于此操作创建的联系人数量。

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>通讯组列表

Lync Server 2013 压力和性能工具的功能之一是在 Lync 2013 中模拟通讯组列表 (DL) 扩展功能。 如果您不打算在 UserProvisioningTool 中启用 DL 扩展，则可以跳过此步骤。

!["通讯组列表创建" 选项卡。](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg ""通讯组列表创建" 选项卡。")

通过 "通讯组列表" 选项卡，您可以创建压力和性能工具将用于通讯组列表扩展功能的 DLs。 在创建 Dl 之前，必须已安装 Lync Server 2013。 您必须已运行 Lync Server 2013 ForestPrep。 否则，在 Active Directory 域服务架构中不存在 DL 属性，并且该工具将无法创建 Dl。

若要配置通讯组列表，请执行以下步骤。

1.  在 "通讯组列表数" 中，指定要创建的 Dl 的总数。  (建议您从) 的用户数中启动两次。 它们的编号从0到 n-1。

2.  在 "通讯组列表前缀" 中，指定 Dl 将具有的前缀。 例如，如果您指定 100 Dl 和 testDL 的前缀，则 Dl 将通过 testDL99 命名为 testDL0、testDL1 等。

3.  在 Dist 的最小成员中，指定每个通讯组列表中要添加的最小用户数。

4.  在 "Dist 的最大成员数" 列表中，指定每个通讯组列表中要添加的最大用户数。

<div>

## <a name="create-distribution-lists-button"></a>"创建通讯组列表" 按钮

当您单击 "创建通讯组列表" 按钮时，该工具会查询 Active Directory 域服务，以查看与已存在的前缀和号码相匹配的通讯组列表。 该工具将仅创建尚不存在的工具。 将成员添加到这些新创建的通讯组列表时，将从 "用户创建" 选项卡上指定的区域中选择用户。

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>位置信息服务配置选项卡

Lync Server 2013 压力和性能工具的功能之一是为 Location 信息服务生成虚拟配置文件。 位置信息服务通常不会对服务器产生显著的性能影响。

![Location Info Service Config 选项卡。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config 选项卡。")

如果选择测试此功能，则可以填写表单中提及的值，然后单击 "生成 IIS 配置文件" 按钮。 它将生成名为 .LIS \_Subnet.csv、iis \_Switches.csv、.Lis \_Ports.csv 和 .LISWAP.csv \_ 的 CSV 文件。 然后，您可以分别使用 **CsLisSubnet** Cmdlet、 **CsLisSwitch** cmdlet、 **CsLisPort** CMDLET 和 **CsWirelessAccessPoint** CMDLET 将这些 CSV 文件导入到 .lis 数据库中。

</div>

</div>

<span> </span>

</div>

</div>

</div>


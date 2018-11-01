---
title: 在运行 Microsoft Exchange Server 统一消息的服务器上配置证书
TOCTitle: 在运行 Microsoft Exchange Server 统一消息的服务器上配置证书
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398564(v=OCS.15)
ms:contentKeyID: 49313266
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在运行 Microsoft Exchange Server 统一消息的服务器上配置证书

 

_**上一次修改主题：** 2016-12-08_

如果已按照规划文档中的[在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)所述部署了 Exchange 统一消息 (UM)，并且您需要向组织中的企业语音用户提供 Exchange UM 功能，您可以使用以下过程在运行 Exchange UM 的服务器上配置证书。

> [!IMPORTANT]  
> 对于内部证书，运行 Lync Server 2013 的服务器和运行 Microsoft Exchange 的服务器都必须具有互相信任的受信任的根证书颁发机构证书。证书颁发机构 (CA) 可以是同一个证书颁发机构，也可以是其他的证书颁发机构（只要两台服务器都具有已在其信任的根证书颁发机构证书存储中注册的由证书颁发机构颁发的根证书）。


Exchange Server 必须配置了服务器证书，才能连接到 Lync Server 2013：

1.  为 Exchange Server 下载 CA 证书。

2.  为 Exchange Server 安装 CA 证书。

3.  确保该 CA 在 Exchange Server 的受信任的根 CA 列表中。

4.  为 Exchange Server 创建证书请求并安装该证书。

5.  为 Exchange Server 分配证书。

## 下载 CA 证书

1.  在运行 Exchange UM 的服务器上，单击“开始”，再单击“运行”，键入 **http://\<发证 CA 服务器的名称\>/certsrv**，然后单击“确定”。

2.  在“选择任务”下，单击“下载 CA 证书、证书链或 CRL”。

3.  在“下载 CA 证书、证书链或 CRL”下，选择“Base 64 编码方式”，然后单击“下载 CA 证书”。
    
    > [!NOTE]  
    > 在此步骤还可以指定可分辨编码规则 (DER) 编码。如果选择 DER 编码，则本过程的下一步中和“安装 CA 证书”的步骤 10 中的文件类型为 .p7b，而非 .cer。
    


4.  在“文件下载”对话框中单击“保存”，然后将文件保存到服务器上的硬盘中。（文件的扩展名将为 .cer 或 .p7b，具体取决于在上一步中选择的编码。）

## 安装 CA 证书

1.  在运行 Exchange UM 的服务器上，打开 Microsoft 管理控制台 (MMC)，方法是依次单击“开始”、“运行”，在“打开”框中键入 **mmc**，然后单击“确定”。

2.  在“文件”菜单上，单击“添加/删除管理单元”，然后单击“添加”。

3.  在“添加独立管理单元”框中，单击“证书”，然后单击“添加”。

4.  在“证书管理单元”对话框中，单击“计算机帐户”，然后单击“下一步”。

5.  在“选择计算机”对话框中，确认已选中“本地计算机: (运行此控制台的计算机)”复选框，然后单击“完成”。

6.  单击“关闭”，然后单击“确定”。

7.  在控制台树中，展开“证书(本地计算机)”，展开“受信任的根证书颁发机构”，然后单击“证书”。

8.  右键单击“证书”，单击“全部任务”，然后单击“导入”。

9.  单击“下一步”。

10. 单击“浏览”找到文件，然后单击“下一步”。（文件的扩展名将为 .cer 或 .p7b，具体取决于在“下载 CA 证书”的步骤 3 中选择的编码。）

11. 单击“将所有证书放入下列存储区”。

12. 单击“浏览”，然后选择“受信任的根证书颁发机构”。

13. 单击“下一步”以验证设置，然后单击“完成”。

## 确认该 CA 在受信任的根 CA 列表中

1.  在运行 Exchange UM 的服务器上的 MMC 中，展开“证书(本地计算机)”，展开“受信任的根证书颁发机构”，然后单击“证书”。

2.  在详细信息窗格中，验证您的 CA 是否位于受信任的 CA 列表中。

## 使用 Lync Server 配置 Exchange Server 2013 UM

1.  有关详细信息，请参阅 Exchange Server 文档中的“将 Exchange 2013 UM 与 Lync Server 集成”，网址为 [http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0x804)。

## 创建证书请求并在 Exchange Server 2007 (SP1) 中安装证书

1.  在运行 Exchange UM 的服务器上，单击“开始”，再单击“运行”，键入 **http://\<***发证 CA 服务器的名称***\>/certsrv**，然后单击“确定”。

2.  在“选择任务”下，单击“请求证书”。

3.  在“请求证书”下，单击“高级证书申请”。

4.  在“高级证书申请”下，单击“创建并向此 CA 提交一个请求”。

5.  在“高级证书申请”下，选择“Web 服务器”或为服务器身份验证配置的其他服务器证书模板。

6.  在“标识脱机模板的信息”下，在“名称”框中键入 Exchange Server 的完全限定域名 (FQDN)。
    
    > [!NOTE]  
    > 必须输入 Exchange Server 的 FQDN 才能进行通信。
    


7.  在“密钥选项”下单击“将证书保存在本地计算机证书存储中”复选框。

8.  单击网页底部的“提交”按钮。

9.  此时将打开一个要求确认的对话框，从中单击“是”。

10. 在“证书已颁发”页上的“证书已颁发”下单击“安装此证书”。

11. 此时将打开一个要求确认的对话框，从中单击“是”。

12. 确认显示了消息“您的新证书已经成功安装”。

## 在 Exchange Server 2010 中创建证书

1.  以适当的用户权限登录运行 Exchange UM 的服务器。有关详细信息，请参阅“客户端访问权限”，网址为 [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x804)。

2.  参考以下过程创建证书：
    
    1.  “创建新的 Exchange 证书”，网址为 [http://go.microsoft.com/fwlink/?linkid=195494\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=195494%26clcid=0x804)
    
    2.  “导入 Exchange 证书”，网址为 [http://go.microsoft.com/fwlink/?linkid=195496\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=195496%26clcid=0x804)
    
    > [!NOTE]  
    > 对于证书“使用者名称”，必须输入 Exchange Server 的 FQDN 才能进行通信。
    


## 在 Exchange Server 2007 (SP1) 中分配证书

1.  在运行 Exchange UM 的服务器上，打开 MMC。

2.  在控制台树中，展开“个人”并单击“证书”。

3.  在详细信息窗格中，验证个人证书是否已显示。

4.  双击该证书以阅读其详细信息并验证该证书是否有效。
    
    > [!NOTE]  
    > 在证书作为有效证书显示之前，可能需要花费几分钟。
    


5.  重新启动 Microsoft Exchange 统一消息服务。
    
    > [!NOTE]  
    > 运行 Exchange Server 2007 SP1 统一消息的服务器将自动检索正确的证书。
    


6.  打开事件查看器并查找事件 ID 1112，该事件指定运行 Exchange Server 2007 SP1 统一消息的服务器已检索到什么证书。

## 在 Exchange Server 2010 中分配证书

1.  以适当的用户权限登录运行 Exchange UM 的服务器。有关详细信息，请参阅“客户端访问权限”，网址为 [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x804)。

2.  有关分配证书的过程，请参阅“为证书分配服务”，网址为 [http://go.microsoft.com/fwlink/?linkid=195497\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=195497%26clcid=0x804)。


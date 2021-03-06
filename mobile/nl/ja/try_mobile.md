---

copyright:
  years: 2016
lastupdated: "2016-10-19"

---

# {{site.data.keyword.mobilefirstbp}} Starter ボイラープレートからのモバイル・アプリの作成
{: #try_mobile}

最終更新日: 2016 年 10 月 19 日
{: .last-updated}

{{site.data.keyword.Bluemix}} Mobile サービスはそれぞれ独立して使用できます。{{site.data.keyword.mobilefirstbp}} Starter ボイラープレートと一緒に使用することもでき、そうすることで最大の利点を得ることができます。

始めに、{{site.data.keyword.mobilefirstbp}} Starter を使用してアプリを作成します。このボイラープレートによって、以下のアクションを実行することが可能になります。

* テンプレート・アプリケーションを使用して Node.js ランタイムを作成する。このアプリケーションを使用して、RESTful API や静的ファイルなどのサーバー・サイド機能を提供することができます。<!-- You can read more about operating this application in the Developing Mobile Backend section.-->
* 各 {{site.data.keyword.Bluemix_notm}} モバイル・サービスのインスタンスをプロビジョンし、そのサービスを Node.js アプリケーションにバインドする。

<!--
<img src="images/mf_boiler_icon.png" alt="Bluemix mobile services" width="500"> {{site.data.keyword.mobilefirstbp}} Starter boilerplate
-->

{{site.data.keyword.mobilefirstbp}} Starter ボイラープレートを使用してアプリを作成したら、各サービス用の Hello Bluemix サンプルを入手したり、既存アプリを装備して {{site.data.keyword.Bluemix_notm}} サービスの使用を開始したりすることができます。


## サービスの概要
{: #services-overview}
{{site.data.keyword.Bluemix_notm}} {{site.data.keyword.mobilefirstbp}} Starter ボイラープレートを使用してすべての {{site.data.keyword.Bluemix_notm}} モバイル・サービスを一緒に使用することも、{{site.data.keyword.Bluemix_notm}} カタログから個々のサービスを使用することもできます。以下の図は、{{site.data.keyword.Bluemix_notm}} モバイル・サービスのコンポーネントの概略を示しています。

![{{site.data.keyword.Bluemix_notm}} モバイル・サービスのアーキテクチャー](images/bms_architecture.jpg)

<table summary="この表は、{{site.data.keyword.Bluemix_notm}} モバイル・サービスの説明を示します">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} とエンタープライズ・システム</caption>
<th>{{site.data.keyword.Bluemix_notm}}</th>
<th>エンタープライズ・システム</th>
<tr>
<td> <img src="images/i_js_64.png" alt="Node.js ランタイム・アイコン"><b>Node.js</b> <br/> テンプレート・アプリをホストする Node.js ランタイムは、{{site.data.keyword.mobilefirstbp}} Starter ボイラープレートの一部として提供されます。このテンプレート・アプリケーションを使用して、RESTful API や静的ファイルなどのサーバー・サイド機能を提供することができます。
<br/>例えば、カスタム・ロジック処理のために Node.js アプリケーションを拡張したり、既存の社内インフラストラクチャー内の REST API に接続したりすることができます。{{site.data.keyword.Bluemix_notm}} で作成する各アプリには固有の アプリ ID が付きます。モバイル・アプリは SDK でこの ID を使用して、そのアプリケーションに関連付けられたサービスにアクセスします。アプリ ID は、課金やロギングなど、一般的な機能のコンテキストとして、プラットフォームが使用します。
<!--You can read more about operating this application in the "Developing Mobile Backend" section.--></td>
<td valign="top"><b>情報プロバイダー</b> <br/>{{site.data.keyword.Bluemix_notm}} でホストされる Node.js ランタイムを使用して、以下のどの情報プロバイダーにでも接続できます。
<ul>
	<li>エンタープライズ・バックエンド</li>
	<li>データベース</li>
	<li>ホストされた別のサード・パーティー・サービス</li>
</ul>
</td>
</tr>
<tr>
<td><img src="images/catalog_icons-05.png" alt="{{site.data.keyword.amashort}} サービス・アイコン"> <b>{{site.data.keyword.amashort}}</b><br/>{{site.data.keyword.amafull}} サービスを使用して、{{site.data.keyword.Bluemix_notm}} でホストされる Node.js アプリケーションおよび Java for Liberty アプリケーションを保護します。{{site.data.keyword.amashort}} SDK を使用してモバイル・アプリを装備することによって、Node.js または {{site.data.keyword.Bluemix_notm}} モバイル・サービスにアクセスするユーザーにログインを要求することができます。{{site.data.keyword.amashort}} は、セキュリティー機能に加えて、分析データの収集機能も提供するので、モバイル・アプリケーションのパフォーマンスをモニターし、クライアント・ログと使用統計を収集することができます。</td>
<td valign="top"><b>ユーザー ID プロバイダー</b> <br/>以下の ID プロバイダーを使用できます。<ul><li>Facebook</li><li>Google</li></ul></td>
</tr>
<tr>
<td><img src="images/catalog_icons-09.png" alt="プッシュ通知サービスのアイコン"> <b>{{site.data.keyword.mobilepushshort}}</b><br/>{{site.data.keyword.mobilepushfull}} サービスは、モバイル (iOS & Android) プラットフォームおよび Web ブラウザー・アプリケーションをターゲットとしたプッシュ通知を送信および管理するための統合プラットフォームを提供します。このサービスは、デバイス、デバイス・プラットフォーム、およびブラウザーへのアプリケーション・ユーザーのマッピングを管理し、サブスクライバーへのプッシュ通知のディスパッチを処理します。このサービスを使用して、ブロードキャスト、ユニキャスト (ユーザー ID、デバイス ID に基づく)、およびタグ (またはトピック) をプッシュ通知に基づいてカスタマーに送信することができます。</td>
<td valign="top"><b>プッシュ・サービス・プロバイダー</b><ul><li>Apple プッシュ通知サービス</li><li>Firebase Cloud Messaging</li></ul></td>
</tr>
<tr>
<td><img src="images/cloudant64.png" alt="Cloudant サービス・アイコン"><b>Cloudant NoSQLDB</b><br/> Cloudant は NoSQL の Database as a Service (DBaaS) です。これは積み上げ方式で構築してグローバルに拡大され、ノンストップで稼働し、JSON、フル・テキスト、地理情報などの多種多様なデータ・タイプを処理します。</td>
<td>Cloudant.com</td>
</tr>
</table>

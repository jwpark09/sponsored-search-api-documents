# CampaignExportService
CampaignExportServiceでは、キャンペーン、広告グループ、キーワード、広告に関する情報の取得を一括で行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/CampaignExportService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/CampaignExportService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201808/CampaignExport

#### サービス概要
キャンペーン、広告グループ、キーワード、広告に関する情報の取得を一括で行います。

#### 操作
CampaignExportServiceで提供される操作を説明します。

+ [addJob](#addjob)
+ [get](#get)
+ [getExportFields](#getexportfields)

#### オブジェクト
[CampaignExport](../data/CampaignExport)

#### 注意事項
・過去にリクエストしたaddJobの詳細は、getにて確認できます。作成したジョブの有効期限は、addJobのリクエストから30日間です。<br>
・エクスポート結果は、getレスポンスのダウンロードURLから確認できます。ダウンロードURLの有効期限は、JobStatusがCOMPLETEDになってから15分間です。<br>

## addJob
エクスポートの登録を実施します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| setting | ○ | [ExportSetting](../data/CampaignExport/ExportSetting.md) | エクスポートする条件の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <addJob xmlns="http://ss.yahooapis.jp/V201808/CampaignExport">
      <setting>
        <accountId>111111</accountId>
        <campaignIds>2222222</campaignIds>
        <adGroupIds>33</adGroupIds>
        <adGroupIds>444</adGroupIds>
        <adIds>555</adIds>
        <adIds>666</adIds>
        <adGroupCriterionIds>777</adGroupCriterionIds>
        <adGroupCriterionIds>8888</adGroupCriterionIds>
        <campaignUserStatuses>ACTIVE</campaignUserStatuses>
        <campaignUserStatuses>PAUSED</campaignUserStatuses>
        <adGroupUserStatuses>ACTIVE</adGroupUserStatuses>
        <adGroupUserStatuses>PAUSED</adGroupUserStatuses>
        <adGroupAdUserStatuses>ACTIVE</adGroupAdUserStatuses>
        <adGroupAdUserStatuses>PAUSED</adGroupAdUserStatuses>
        <adGroupCriterionUserStatuses>ACTIVE</adGroupCriterionUserStatuses>
        <adGroupCriterionUserStatuses>PAUSED</adGroupCriterionUserStatuses>
        <adGroupAdApprovalStatuses>APPROVED</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>APPROVED_WITH_REVIEW</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>REVIEW</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>PRE_DISAPPROVED</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>POST_DISAPPROVED</adGroupAdApprovalStatuses>
        <adGroupCriterionApprovalStatuses>APPROVED</adGroupCriterionApprovalStatuses>
        <adGroupCriterionApprovalStatuses>APPROVED_WITH_REVIEW</adGroupCriterionApprovalStatuses>
        <adGroupCriterionApprovalStatuses>REVIEW</adGroupCriterionApprovalStatuses>
        <adGroupCriterionApprovalStatuses>PRE_DISAPPROVED</adGroupCriterionApprovalStatuses>
        <adGroupCriterionApprovalStatuses>POST_DISAPPROVED</adGroupCriterionApprovalStatuses>
        <entityTypes>ALL</entityTypes>
        <jobName>TestJob</jobName>
        <lang>JA</lang>
        <encoding>UTF-8</encoding>
        <exportFields>CAMPAIGN_NAME</exportFields>
        <exportFields>AD_GROUP_NAME</exportFields>
        <exportFields>AD_NAME</exportFields>
      </setting>
    </addJob>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignExportReturnValue](../data/CampaignExport/CampaignExportReturnValue.md) | 操作結果を含むエクスポートに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignExport</ns2:service>
      <ns2:requestTime>1523506331925</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:addJobResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignExport">
      <ns2:rval>
        <ListReturnValue.Type>CampaignExportReturnValue</ListReturnValue.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:jobId>1998</ns2:jobId>
            <ns2:userName>1111-2576-2222-6847</ns2:userName>
            <ns2:startDate>2017-11-28T10:31:24+09:00</ns2:startDate>
            <ns2:status>IN_PROGRESS</ns2:status>
            <ns2:progress>0</ns2:progress>
            <ns2:exportFields>CAMPAIGN_NAME</ns2:exportFields>
            <ns2:exportFields>AD_GROUP_NAME</ns2:exportFields>
            <ns2:exportFields>AD_NAME</ns2:exportFields>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:addJobResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## get
登録したジョブに関するステータス情報を取得します。<br>

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [JobSelector](../data/CampaignExport/JobSelector.md) | 登録したエクスポート情報を検索する条件の情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>100000001</accountId>
        <jobIds>1111</jobIds>
        <jobIds>1112</jobIds>
        <statuses>SYSTEM_ERROR</statuses>
        <statuses>COMPLETED</statuses>
        <statuses>IN_PROGRESS</statuses>
        <statuses>TIMEOUT</statuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignExportPage](../data/CampaignExport/CampaignExportPage.md) | 取得される登録済のエクスポート情報に関する内容です。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignExport</ns2:service>
      <ns2:requestTime>1523506331905</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignExport">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>CampaignExportPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>11000000</ns2:accountId>
            <ns2:jobId>1999</ns2:jobId>
            <ns2:userName>2843-2576-6539-6847</ns2:userName>
            <ns2:startDate>2017-11-28T10:31:24+09:00</ns2:startDate>
            <ns2:endDate>2017-11-28T10:31:25+09:00</ns2:endDate>
            <ns2:status>COMPLETED</ns2:status>
            <ns2:progress>100</ns2:progress>
            <ns2:downloadUrl>https://ss.yahooapis.jp/export/V201808/download/Cwb66zoaz1qr0HD6DlPq3Xca8LRUODnBWLcEeT64WuhhLrCf507Jo3v5FmZ6fGvm3k0YqbjOu9XBqkkZVCBWrhb0wtuAuxVbg35S_HPGxfCg9gxq5qabtwPblcRmp7LzlvEedZzaczG.g7wrgliey93KdGob8adSnhGNol0PZfJ8UBeAaBJ7zjjS010XmqJe8u0XMYpS7DqKlFe4REWkLAX293y8E1hUhRckDiul3awJBlqAQdnR9s2BRmMsznRPMxp85v2OXQm_onO79tN6lY7CXWNOzd3enyxllUXPmAwL4Ey8ciV01Ku3cBYh08RiIqBwV5TDJf4-</ns2:downloadUrl>
            <ns2:exportFields>CAMPAIGN_NAME</ns2:exportFields>
            <ns2:exportFields>AD_GROUP_NAME</ns2:exportFields>
            <ns2:exportFields>AD_NAME</ns2:exportFields>
          </ns2:job>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>11000000</ns2:accountId>
            <ns2:jobId>1998</ns2:jobId>
            <ns2:userName>2843-2576-6539-6847</ns2:userName>
            <ns2:startDate>2017-11-28T10:31:24+09:00</ns2:startDate>
            <ns2:status>IN_PROGRESS</ns2:status>
            <ns2:progress>20</ns2:progress>
            <ns2:exportFields>CAMPAIGN_NAME</ns2:exportFields>
            <ns2:exportFields>AD_GROUP_NAME</ns2:exportFields>
            <ns2:exportFields>AD_NAME</ns2:exportFields>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getExportFields
エクスポートできるフィールドを照会します。



##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getExportFields xmlns="http://ss.yahooapis.jp/V201808/CampaignExport"/>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
getExportFieldsメソッドの実行結果(エクスポート可能なフィールドのリスト)を保持します。

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignExportFieldValue](../data/CampaignExport/CampaignExportFieldValue.md) | getExportFieldsメソッドの実行結果(エクスポート可能なフィールドのリスト)を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignExport" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignExport</ns2:service>
      <ns2:requestTime>1523506331914</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getExportFieldsResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignExport">
      <ns2:rval>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Name</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_GROUP_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループ名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group Name</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ENTITY_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>コンポーネントの種類</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Component Type</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ENTITY_STATUS</ns2:fieldName>
          <ns2:displayFieldNameJA>配信設定</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Display Settings</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DISPLAY_STATUS</ns2:fieldName>
          <ns2:displayFieldNameJA>配信状況</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Display Status</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>BULK_MATCH_TYPE</ns2:fieldName>
          <ns2:displayFieldNameJA>マッチタイプ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Match Type</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>TERM</ns2:fieldName>
          <ns2:displayFieldNameJA>キーワード</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Keyword</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MANU_OPT_BID</ns2:fieldName>
          <ns2:displayFieldNameJA>入札価格</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Bid</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>広告名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Name</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>BULK_AD_TYPE</ns2:fieldName>
          <ns2:displayFieldNameJA>広告タイプ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Type</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>HEADLINE</ns2:fieldName>
          <ns2:displayFieldNameJA>タイトル</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Title</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DESCRIPTION</ns2:fieldName>
          <ns2:displayFieldNameJA>説明文1</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Description1</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DESCRIPTION2</ns2:fieldName>
          <ns2:displayFieldNameJA>説明文2</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Description2</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DISPLAY_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>表示URL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Display URL</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>HEADLINE_1</ns2:fieldName>
          <ns2:displayFieldNameJA>タイトル1</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Title1</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>HEADLINE_2</ns2:fieldName>
          <ns2:displayFieldNameJA>タイトル2</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Title2</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DESCRIPTION_ETA</ns2:fieldName>
          <ns2:displayFieldNameJA>説明文</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Description</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PATH_1</ns2:fieldName>
          <ns2:displayFieldNameJA>ディレクトリ1</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Directory1</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PATH_2</ns2:fieldName>
          <ns2:displayFieldNameJA>ディレクトリ2</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Directory2</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADVANCED_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>最終リンク先URL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Landing Page URL</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADVANCED_MOBILE_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>スマートフォン向けURL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Mobile Landing Page URL</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>TRACKING_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>トラッキングURL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Tracking URL</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CUSTOM_PARAMETER</ns2:fieldName>
          <ns2:displayFieldNameJA>カスタム パラメータ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Custom Parameters</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>BUDGET_AMOUNT</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン予算（日額）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Daily Budget</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>START_YMD</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン開始日</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Start Date</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PLATFORM_BID_MULTIPLIER</ns2:fieldName>
          <ns2:displayFieldNameJA>スマートフォン入札価格調整率（%）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Smartphone Bid Adjustment (%)</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>BULK_DEVICE_PREFERENCE</ns2:fieldName>
          <ns2:displayFieldNameJA>優先デバイス</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Focus Device</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign ID</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_GROUP_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group ID</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CRITERION_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>キーワードID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Keyword ID</ns2:displayFieldNameEN>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad ID</ns2:displayFieldNameEN>
        </ns2:fields>
      </ns2:rval>
    </ns2:getExportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

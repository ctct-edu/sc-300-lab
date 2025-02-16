---
lab:
  title: 27 - Microsoft Entra データ ソースの Microsoft Sentinel Kusto クエリ
  learning path: '04'
  module: Module 04 - Plan and Implement and Identity Governance Strategy
---

# ラボ 127 - Microsoft Sentinel Kusto Queries for Microsoft Entra data sources（Microsoft Entra データ ソースの Microsoft Sentinel Kusto クエリ）

### ログインの種類 = Azure リソース ログイン

## ラボのシナリオ

Microsoft Sentinel は、スケーラブルでクラウドネイティブの SIEM および SOAR ソリューションです。  Microsoft とサードパーティのセキュリティ ソリューションからデータ ソースを接続すると、セキュリティ操作タスクを実行できます。  このラボ演習では、Kusto 照会言語 (KQL) を使用してハンティング クエリを実行するための Microsoft Entra ID へのデータ コネクタを備えた Microsoft Sentinel ワークスペースを作成します。 

#### 予想所要時間: 30 分

### 演習 1 - Kusto クエリ用に Microsoft Sentinel を構成する

※ Skillable環境では、本演習に必要な権限がIDにないため、タスク2手順5がエラーとなります。そのため手順の参考程度にとどめてください。

#### タスク 1 - Microsoft Sentinel ワークスペースを作成する

1. グローバル管理者として、 [https://portal.azure.com](https://portal.azure.com)  にサインインします。

1. **Microsoft Sentinel** を検索して選択します。 

1. 左上隅にある **[+ 作成]** を選択します。

1. **[ワークスペースへの Microsoft Sentinel の追加]** タイルで、**[+ 新しいワークスペースの作成]** を選択します。

1. **[リソース グループ]** で、「**Sentinel-RG**」を選択します。

1. ワークスペースに **SentinelLogAnalyticsXXXXXXXX** と名前を付けます。  

1. **East US** リージョンを選択します。

1. **[確認と作成]** 、 **[作成]** の順に選択します。

1. Log Analytics ワークスペースのデプロイが完了した後「ワークスペースへの Microsoft Sentinel の追加」ウィンドウに戻ります。  **SentinelLogAnalyticsXXXXXXXX** ワークスペース(表示されていない場合は、画面を更新してください)を選択し、 画面下にある **[追加]** をクリックします。  これにより、ワークスペースが Microsoft Sentinel に追加され、Microsoft Sentinel が開きます。

1. Microsoft Sentinel の無料試用版をアクティブ化されたダイアログが表示されたら、 **[OK]** を選択して閉じます。

#### タスク 2 - Microsoft Entra ID をデータ ソースとして追加する

1. **Microsoft Sentinel** で、メニューの **[コンテンツ管理]** カテゴリの、**[コンテンツ ハブ]** を選択します。

1. 検索ボックスを使用してコネクタの一覧で **[Entra]** を検索し、**[Microsoft Entra ID]** を見つけてチェックボックスをオンにします。

1. 右側にプレビュー タイルが開きます。  **[インストール]** を選択します。

1. インストールが完了したら、メニューの [構成] カテゴリにある **[データ コネクタ]** メニュー項目を選択します。

    **注** - インストールされている 1 つのコネクタが表示され、**Microsoft Entra ID** が一覧に表示されます。

1. **[Microsoft Entra ID]**、**[Open connector page]** の順に選択します。

1. コネクタ ページに、データ コネクタの手順と次のステップが提供されます。 **構成**を続行するための各**前提条件**の横にチェック マークがあることを確認します。

1. **[構成]** で、 **[サインイン ログ]** と **[監査ログ]** のチェック ボックスをオンにします。 追加のログ ソースを利用できますが、現在**プレビュー**段階であり、このコースの対象外です。

1. **[変更の適用]** を選択します。 

1. 変更が正常に適用されたことを示す通知が表示されます。 コネクタ ページの右上にある **[X]** を選択して、**Microsoft Sentinel** ワークスペースに移動します。

1. **[Microsoft Sentinel | データ コネクタ]** タイルで **[更新]** を選択すると、数値 1 が **[接続済み]** の数に表示されます。

   **注** - Microsoft Entra ID データ コネクタがアクティブな数に表示されるまでに数分かかる場合があります。 

#### タスク 3 - ユーザー アクティビティで Kusto クエリを実行する

1. **Microsoft Sentinel** で、 **[全般]** メニュー見出しの下にある **[ログ]** に移動します。

1. **[Log Analytics へようこそ]** ウィンドウを閉じます。

1. サンプル クエリが表示されているウィンドウが開いたら、**[監査]** を選択し、**[ユーザー ID]** を検索します。

1. **[実行]** を選択します。 

1. Microsoft Entra ID のユーザー ID の一覧が表示されます。  ワークスペースを作成したばかりのため、結果が表示されない場合があります。  クエリの形式に注意してください。

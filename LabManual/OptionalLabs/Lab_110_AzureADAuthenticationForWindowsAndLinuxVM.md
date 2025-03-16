---
lab:
  title: 10 - Windows および Linux Virtual Machines に対する Microsoft Entra ID 認証
  learning path: '02'
  module: Module 02 - Implement an Authentication and Access Management Solution
---

# ラボ 110 - Microsoft Entra Authentication for Windows and Linux Virtual Machines

## ラボのシナリオ

会社は、リモート アクセス用の仮想マシンへのログインに Microsoft Entra ID を使用することを決定しました。  このラボでは、Windows 仮想マシンに対してこれをセットアップする方法について示します。

#### 予想所要時間: 25 分

### 演習 1 - Microsoft Entra ID を使用して Azure の Windows Virtual Machines にログインする

#### タスク 1 - Microsoft Entra ID ログインを有効にして Windows 仮想マシンを作成する

1. [https://portal.azure.com](https://portal.azure.com) を参照します

1. **[+ リソースの作成]** を選択します。

1. [サービスとマーケットプレースを検索してください] 検索バーに「**Windows 11**」と入力し、Enterキーを押下します。

1. **[Windows 11]** のタイルの下の方にある、[作成] の右のドロップダウンを展開し、 **[Windows 11 Enterprise、version 22H2]** を選択します。

1. **[基本]** タブで次の値を使用して VM を作成します。

| フィールド | 使用する値 |
| :-- | :-- |
| サブスクリプション | 既定値をそのまま使用します |
| リソース グループ | 「rgEL」を選択 |
| 仮想マシン名 | elvmXXXXXXXX |
| リージョン | East US                                                      |
| 可用性のオプション | インフラストラクチャ冗長は必要ありません |
| セキュリティの種類 | Standard |
| サイズ | Standard DC1s_v3 - 1 vCPU、8 GiB メモリ　（「すべてのサイズを表示」をクリックして、「VMサイズの選択」ウィンドウに移動。検索欄に「DC1s_V3」等入力して検索し、見つけたものをクリックし、「選択」ボタンをクリックします。） |
| 管理ユーザー名 | vmEntraAdmin |
| 管理者パスワード | Pa55w.rdXXXXXXXX |
| ライセンス | 「マルチテナントをホストする権利を持つ有効な Windows 10/11 ライセンスを所有しています。」のチェックをオンにします。 |

1. **[ディスク]** または **[ネットワーク]** タブでは何も変更する必要はなく、値を確認できます。

1. **[管理]** タブで、[Microsoft Entra ID] セクションの **[Microsoft Entra ID でログイン]** のボックスをオンにします。

1. **[確認および作成]**、**[作成]** の順に選択します。

1. 、**[リソースに移動]** をクリックします。

#### タスク 2 - 既存の Azure Virtual Machines に対して Microsoft Entra ID でログインする

1. メニューの **[アクセス制御 (IAM)]** を選択します。
1.  **[Role Assignments]** タブを選択します。
1. 「名前または電子メールで検索する」欄にて、 **User2** で 一覧を検索し、User2 に「仮想マシンの管理者ログイン」ロールが割り当てられていることを確認します。

#### タスク 3 - Microsoft Entra ID ログインを許可するように仮想マシンを更新する

1. メニューの **[接続]** を選択します。
1. **[RDP]** タブで、 **[RDP ファイルのダウンロード]** を選択します。  メッセージが表示されたら、ファイルの **[保持(keep)]** オプションを選びます。  Downloadフォルダーに保存されます。
1. ブラウザーに表示される **[Open file]**  をクリックするか、あるいは Downloadフォルダーにある～.rdpファイルを開きます。
1.  **[Connect]** をクリックします。
1. 仮想マシンの作成時に設定した管理者 (vmEntraAdmin) ユーザー名とパスワードを使用して接続します。
   - メッセージが表示されたら、[Yes] と答え、仮想マシンまたは RDP セッションへのアクセスを許可します。
1. 「Choose privacy settings for your device」画面で  **[Next]** を数回選択後、 **[Accept]** を選択して終了します。
1. 仮想マシンで **[スタート] ボタン(Windows アイコン)** を選択します。
1. 「**Control Panel**」と入力し、コントロール パネル アプリを起動します。
1. 設定のリストから **[System and Security]** を選択します。
1. **[System]** 設定にある **[Allow remote access]** を選択します。
1. 開いたダイアログ ボックスの下部に、 **[Remote Desktop]** セクションが表示されます。
1. **[Allow connections only from computers running Remote Desktop with Network Level Authentication (recommended)]** というラベルのチェックボックスを**オフ**にします。
1. **[Apply]**  、 **[OK]** の順に選択します。
1. 仮想マシンの RDP セッションを**サインアウト**します。

#### タスク 4 - Microsoft Entra ID ログインをサポートするように RDP ファイルを変更する

1. notepad コマンドを実行するなどの方法で、メモ帳を起動します。

1. ラボ環境のファイルエクスプローラーでDownloadフォルダーを開きます。RDPファイル(～.rdp)があります。

1. RDP ファイルをメモ帳にドラッグ&ドロップするなどで開いて編集します。 これらの 2 行のテキストをファイルの下部に追加します。

      ```
      enablecredsspsupport:i:0
      authentication level:i:2
      ```

 1. RDP ファイルを**保存**し、メモ帳を閉じます。  

#### タスク 5 - Microsoft Entra ID ログインを使って Windows 仮想マシンに接続する

1. RDP ファイルをダブルクリックします

1. ダイアログが開いたら、 **[Connect]** を選択します。

1. 画面の下部で、 **[Yes]** を選択します。

1. ログイン ダイアログで、次の情報を入力し、ログインします。

   - ユーザー名 = **AzureAD\User2-XXXXXXXX@LODSPRODMCA.onmicrosoft.com**　（XXXXXXXX はご自身の番号に置き換えてください）
   - パスワード = ラボ プロバイダーによって提供されるパスワードを入力します。

   ※ User2-～とパスワードは、ラボの右側の 「Resources」タブに表示された文字をクリックすると、ラボ内に転記されます。

   ※ 英語キーボードのため \  は「む」のキーで入力できます。


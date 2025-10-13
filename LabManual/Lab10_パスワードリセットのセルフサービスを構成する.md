---
lab:
    title: '11 - パスワードリセットのセルフサービスを構成する'
    learning path: '02'
---

# ラボ 10：パスワードリセットのセルフサービスを構成する
#### 推定時間: 15 分

### タスク 1 - SSPR を割り当てるグループを作成する

1. [Microsoft Entra ID]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

2. 左側のナビゲーション メニューの「グループ」を選択し「+ 新しいグループ」を選択します。

2. 次の情報を使用し「作成」をクリックします。

    > 注:指定の無い項目は、「空欄」または「デフォルト値」で結構です。
    
    | 設定 | 値 |
    | :--- | :--- |
    | グループの種類| セキュリティ |
    | グループ名| SSPRTesters |
    | グループの説明| SSPR のロールアウトのテスター |
    | メンバーシップの種類| 割り当て済み |
    | メンバー| Alex Wilber |
    | | Allan Deyoung |
    | | Bianca Pisani |



### タスク 2 - テスト グループの SSPR を有効にする

1. Micrsoft Entra IDのトップ画面へ戻ります。

    > 注:「Contosoマーケティング | 概要」ブレードです。

2. 左側のナビゲーション メニューの「パスワード リセット」 を選択します。

3. 「パスワード リセット | プロパティ」ブレードで、「SSPRSecurityGroupUsers」 をクリックします。

5. 「既定のパスワード リセット ポリシー」ウィンドウで、「SSPRTesters」 グループのチェックボックスをオンにし、「選択」をクリックします。

6. 「保存」 をクリックします。

    

### タスク 3 - Alex Wilber 自身が多要素認証の設定をする

1. 新しい InPrivate ブラウザー ウィンドウを開きます。
2. [[Azure Portal]( https://portal.azure.com)]に`AlexW@XXXXXXXXXXX.onmicrosoft.com` でサインインします。（初期パスワードは初日朝にSkillableから取得した User Password です)
4. Microsoft Authenticator による多要素認証を設定します。
7. そのままサインインを継続し、Azure Portalが表示されたら、いったんブラウザーを閉じます。



### タスク 4 - SSPR をテストする

1. 新しい InPrivate ブラウザー ウィンドウを開きます。

2. [Azure Portal]( https://portal.azure.com) に`AlexW@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

3. 「パスワードの入力」ページで、「パスワードを忘れた場合」 を選択します。

4. 「アカウントの復元」ページで、要求された情報を入力し、「次へ」 を選択します。

    ![「メールまたはユーザー名」、入力ボックス、「次へ」ボタンが強調表示された「アカウントの復元」ページが表示されている画面イメージ](./media/lp2-mod2-get-back-into-your-account-page.png)

5. 「確認ステップ 1」 タスクで、「認証アプリで通知を承認する」 を選択し、「通知の送信」 をクリックします。

6.  画面に表示された2桁の番号を Microsoft Authenticator に入力して承認します。

7. 「新しいパスワードの選択」ステップで、パスワード を「Pa55w.rd1234」 で設定します。

9. 「パスワードがリセットされました」と表示されます。

10. 「新しいパスワードでサインインするには、ここをクリックします。」を使用し、AlexWとしてサインインします。

11. 完了したら、ブラウザーを閉じます。

      

### タスク 5 - SSPRTesters グループに属していないユーザーを検証する

1. 新しい InPrivate ブラウザー ウィンドウを開きます。

   1. [Azure Portal]( https://portal.azure.com) に`GradyA@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

2. 「パスワードの入力」ページで、「パスワードを忘れた場合」 を選択します。

3. 「アカウントの復元」ページで、要求された情報を入力し、「次へ」 を選択します。

4. 画面内に「申し訳ございません。ご使用のアカウントでパスワードのリセットが有効になっていないため、自分でパスワードをリセットすることはできません。」と表示されSSPRが実施できないことを確認します。

   

この演習では、SSPRの実装とテストを実施しました。

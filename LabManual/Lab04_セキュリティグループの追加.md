---
lab:
    title: '05 - セキュリティグループの追加とライセンスの割り当て'
    learning path: '01'
---

# ラボ 04：セキュリティグループの追加

#### 推定時間: 5 分

### タスク1 - Microsoft Entra ID でセキュリティ グループを作成する

1. [Microsoft Entra ID]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

2. 左側のナビゲーション メニューの「グループ」 を選択します。

3. 「グループ」ブレードのメニューで、「新しいグループ」 を選択します。

4. 次の情報を使用し「作成」をクリックします。

    > 注:指定の無い項目は、「空欄」または「デフォルト値」で結構です。

    | 設定 | 値 |
    | :--- | :--- |
    | グループの種類| セキュリティ |
    | グループ名| sg-SC300-O365 |
    | メンバーシップの種類| 割り当て済み |
    | 所有者| `MOD Administrator(admin@XXXXXXXXXXX.onmicrosoft.com)` |
    | メンバー | Delia Dennis |

    ![「グループの種類」、「グループ名」、「所有者」、「メンバー」が強調表示された「新しいグループ」ブレードが表示されている画面イメージ](./media/lp1-mod2-create-group.png)

5. 「作成」ボタンをクリックします。

6. 完了したら、sg-SC300-O365 という名前のグループが 「グループ | すべてのグループ」 ブレード内のリストに表示されていることを確認します。


---
lab:
    title: '06 - Microsoft365グループの追加とライセンスの割り当て'
    learning path: '01'
---

# ラボ 05：Microsoft365グループの追加

#### 推定時間: 5分

### タスク1 - Azure Active Directory で Microsoft 365 グループを作成する

1. [Microsoft Entra ID]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

1. 左側のナビゲーション メニューの「グループ」 を選択します。

1. 「グループ」ブレードのメニューで、「新しいグループ」 を選択します。

1. 次の情報を使用し「作成」をクリックします。

    > 注:指定の無い項目は、「空欄」または「デフォルト値」で結構です。

    | 設定 | 値 |
    | :--- | :--- |
    | グループの種類| Microsoft 365 |
    | グループ名| Northwest Sales |
    | メンバーシップの種類| 割り当て済み|
    | 所有者| `MOD Administrator(admin@XXXXXXXXXXX.onmicrosoft.com)` |
    | メンバー| Alex Wilber と Bianca Pisani |

    ![「グループの種類」、「グループ名」、「所有者」、「メンバー」が強調表示された「新しいグループ」ブレードが表示されている画面イメージ](./media/lp1-mod2-create-o365-group.png)

1. 完了したら、「Northwest sales」 という名前のグループが 「すべてのグループ」 リストに表示されていることを確認します。



この演習では、Microsoft365グループを作成しました。

---
lab:
    title: '20 - Entraロール用に PIMを構成する'
    learning path: '04'
---

# ラボ19：Entra ロール用に PIMを構成する

#### 推定時間: 10 分

### タスク 1 - Entra ロールの設定を構成する

1. [Microsoft Entra ID]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

1. 左側のナビゲーション メニューの 「Identity Governance」 をクリックします。

1. 「Privileged Identity Management」を展開し、「Azure AD ロール」 をクリックします。

1. 「Contosoマーケティング | クイック スタート」ブレード左側のナビゲーションツリーより 「設定」 をクリックします。

    ![「設定」メニューが強調表示された 「Azure AD ロール」ページを表示している画面イメージ](./media/lp3-mod3-pim-ad-roles-settings.png)

1. ロールの一覧を確認してから、「ロール名による検索」 に 「コンプライアンス」 と入力します。

1. 結果から 「コンプライアンス管理者」 をクリックします。

1. 「ロール設定の詳細 - コンプライアンス管理者」ブレードより 「編集」 をクリックします。

    ![ロール設定の詳細 - コンプライアンス管理者ページの上部の「編集」が強調表示されている画面イメージ](./media/lp4-mod3-pim-edit-compliance-role.png)

1. 「アクティブにするには承認が必要です」 チェック ボックスをオンにします。

1. 承認者に「Chris Green」を選択します。

1. 最後に「更新」をクリックします。

![ロール設定の編集ブレードと、クリックしたメンバーが強調表示されたメンバーのクリックウィンドウを表示している画面イメージ](./media/lp4-mod3-pim-add-approver.png)



この演習では、Privileged Identity Managementを使ってAzureADロールの承認者を設定しました。


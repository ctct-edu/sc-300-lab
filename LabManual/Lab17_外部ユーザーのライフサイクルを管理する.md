---
lab:
    title: '19 - 外部ユーザーのライフサイクルを管理する'
    learning path: '04'
---

# ラボ17：外部ユーザーのライフサイクルを管理する  

#### 推定時間: 5 分

## タスク 1 - Identity Governance の設定で外部ユーザーのライフサイクルを管理する

1. [Microsoft Entra ID]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@XXXXXXXXXXX.onmicrosoft.com`でサインインします。

1. 左側のナビゲーション メニューの 「Identity Governance」 をクリックします。

1. 「エンタイトルメント管理」を展開し、「Control configurations」 を選択します。

1. 「View settings」 をクリックします。

1. 「Lifecycle of external users」ウィンドウで、次の情報を使用し「Save」をクリックします。

    > 注:指定の無い項目は、「空欄」または「デフォルト値」で結構です。

    | 設定                                                        | 値   |
    | :---------------------------------------------------------- | ---- |
    | Remove external user                                        | オン |
    | Block external user from signing in to directory            | オフ |
    | Number of days before removing external user from directory | 30   |



この演習では、外部ユーザーのライフサイクルに関する設定について確認しました。


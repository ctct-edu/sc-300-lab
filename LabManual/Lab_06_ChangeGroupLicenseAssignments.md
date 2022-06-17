---
lab:
    title: '06 - グループ ライセンス割り当てを変更する'
    learning path: '01'
    module: 'モジュール 02 - ID の作成、構成、管理を行う'
---

# ラボ 06: グループ ライセンス割り当てを変更する

## ラボ シナリオ

時折、Azure AD Microsoft365グループで使用されているライセンスの割り当てを変更する必要があります。

グループのライセンス割り当てを変更する手順を確実に理解しておく必要があります。

#### 推定時間: 5 分

### タスク1 - グループ ライセンス割り当てを変更する

1. [Azure Active Directory]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@ctcXXXX.onmicrosoft.com`でサインインします。
1. 左側のナビゲーション メニューの「グループ」 を選択します。
1. 前の演習で作成した 「Northwest Sales」 を選択します。
1. 左側のナビゲーション メニューの 「ライセンス」 を選択します。
1. 「+ 割り当て」 を選択します。
1. 「ライセンス割り当ての更新」ブレードの 「ライセンスの選択」 で、「Office 365 E3」 のチェック ボックスをオンにします。
1. 「ライセンスオプションの確認」は「Office365 E3」を選択し、「保存」をクリックします。
1. 完了したら、「保存」 を選択します。
1. グループの「ライセンス」ページで、「Office365 E3」が追加されたことを確認します。



### タスク2 - グループの所有者アカウントでサインインし、Teamsのチャネルを作成

> 注:このタスクはスキップしてもOKです。
>
> 注:ここからの操作は、以下の事象が発生する場合があるため、「Microsoft Edge」で操作することを推奨します。
>
> 　 [Teams Web クライアントがログイン ループでスタックする](https://docs.microsoft.com/ja-jp/microsoftteams/troubleshoot/teams-sign-in/sign-in-loop#resolution)

1. 新しい InPrivate ブラウザー ウィンドウを開きます。

2. [https://www.office.com](https://www.office.com) に`admin@ctcXXXX.onmicrosoft.com`でサインインします。

3. 「新しい Office へようこそ」のガイドが表示されます。確認し、進めてください。

4. 画面右側の「Teams」をクリックします。

5. 「Teams デスクトップ アプリを入手して、チームワークをさらに充実させましょう。」と表示されます。

   「代わりに Web アプリを使用」をクリックします。

6. 「チームをまとめましょう」のガイドが表示されます。確認し、進めてください。

7. 画面右下の「チームに参加、またはチーム作成」をクリックします。

8. 「チームを作成」をクリックします。

9. 「グループまたはチームから」をクリックします。

10. 「Microsoft365グループ」をクリックします。

11. 「Northwest Sales」を選択し、「作成」をクリックします。

    > 注:Microsoft TeamsのチームまたはチャネルはMicrosoft365グループのみサポートされています。
    >
    > 　そのため、セキュリティグループを使用することは出来ません。
    >
    > 　ただし、チャネルのメンバーには「セキュリティグループ」を迎え入れることは可能です。

12. 作成したグループの「一般」チャネルを選択し、「ユーザーを追加」をクリックします。

13. 「名前またはグループを入力してください」に「Alex Wilber 」と「Bianca Pisani」「Chris Green」を入力し、追加します。

    > 注:Chris Greenはグループのメンバーではありませんが、追加できます。

14. Teamsの画面を閉じます。

    

### タスク3 - Teams上で追加されたユーザーを確認する

> 注:このタスクはスキップしてもOKです。
>
> 新しい InPrivate ブラウザー ウィンドウを開きます。
>

1. [Azure Active Directory]( https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview) に`admin@ctcXXXX.onmicrosoft.com`でサインインします。

1. 左側のナビゲーション メニューの「グループ」 を選択します。

1. 前の演習で作成した 「Northwest Sales」 を選択します。

1. 左側のナビゲーション メニューの「メンバー」をクリックします。

1. メンバーの一覧に「Chris Green」が追加されたことを確認します。

   

この演習では、Microsoft365グループにライセンスを付与し、Microsoft365グループの機能について確認しました。

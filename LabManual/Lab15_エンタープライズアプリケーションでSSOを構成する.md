---
lab:
    title: '16 - エンタープライズアプリケーションでSSOを構成する'
    learning path: '03'
---

# ラボ 15：エンタープライズアプリケーションでSSOを構成する

#### 推定時間: 40 分

### タスク 1 - Salesforceの利用を開始する

このタスクではSalesforceの無償アカウントを作成します。

1. [https://developer.salesforce.com/signup](https://developer.salesforce.com/signup)にアクセスします。

2. 「Sign up for your Salesforce Developer Edition」が表示されます。次の項目を入力し、チェックボックスにすべてチェックを入れ、「Sign me Up」をクリックします。

     > 注: XXXXはご自身のTenant Prefixになります。

     | 項目           | 値                                                           |
     | -------------- | ------------------------------------------------------------ |
     | First Name     | XXXXXXXXXXX                                                  |
     | Last Name      | ctc                                                          |
     | Email          | `admin@XXXXXXXXXXX.onmicrosoft.com` (ラボ 準備で作成したユーザーを指定) |
     | Role           | Developer                                                    |
     | Company        | XXXXXXXXXXX                                                  |
     | Country/Region | Japan                                                        |
     | State/Province | 任意(Tokyo等)                                                |
     | Postal Code    | XXXXXXXXXXX.portal                                           |
     | Username       | `admin@XXXXXXXXXXX.onmicrosoft.com` (ラボ 準備で作成したユーザーを指定) |

     ![aad-sso-008](./media/aad-sso-008.BMP)

     

3. 「Please check your email to confirm your account.」と表示されます。登録したメールアドレスに確認メールが送信されます。

     ![aad-sso-009](./media/aad-sso-009.BMP)

     

4. 届いたメールを確認します。[https://outlook.live.com/](https://outlook.live.com/)にアクセスし、サインインします。

     | 項目                      | 値                                                           |
     | ------------------------- | ------------------------------------------------------------ |
     | メール、電話、またはskype | `admin@XXXXXXXXXXX.onmicrosoft.com` (ラボ 準備で作成したユーザーを指定) |
     | パスワード                | ラボで使用しているパスワードと同じ                                                 |

     ![aad-sso-010](./media/aad-sso-010.BMP)

     

5. 受信トレイにある「Salesforce へようこそ: アカウントを確認してください」というメールを開き、「アカウントを確認」をクリックします。

     ![aad-sso-011](./media/aad-sso-011.BMP)

     

6. Salesforceの「パスワードを変更する (Ready for a new password?)」ページにリダイレクトされます。次の項目を入力し、「パスワード変更」をクリックします。

     | 項目                   | 値           |
     | ---------------------- | ------------ |
     | 新しいパスワード       | ラボで使用しているパスワードと同じ |
     | 新しいパスワードの確認 | ラボで使用しているパスワードと同じ |
     | セキュリティの質問     | 出生地は? |
     | 回答                   | 日本         |

     ![aad-sso-012](./media/aad-sso-012.BMP)

     

7. 「セールス|ホーム」画面にリダイレクトされます。画面右上の「歯車」をクリックし、「設定」をクリックします。

8. 「設定|ホーム」画面にジャンプされます。

     ![aad-sso-013](./media/aad-sso-013.BMP)



### タスク 2 - SalesforceでSAML認証を有効化する

Azure ADとSalesforce間ではSAMLによってに認証を連携することが可能になります。ここでは、SalesforceのSAML認証を有効にします。

1. 「設定|ホーム」画面の左側ツリーにあるIDを展開し、「シングルサインオン設定」をクリックします。

     ![aad-sso-014](./media/aad-sso-014.BMP)

     

2. 「シングルサインオン設定」画面にて、画面中央にある「編集」をクリックします。

     ![aad-sso-015](./media/aad-sso-015.BMP)

     

3. 「SAML を使用した統合シングルサインオン」の項目にある「SAMLを有効化」のチェックボックスにチェックを入れ、「保存」をクリックします。

     ![aad-sso-016](./media/aad-sso-016.BMP)

     

4. 画面が切り替わり、再び「シングルサインオン設定」画面で「SAML を有効化」にチェックがあれば完了です。

![aad-sso-017](./media/aad-sso-017.BMP)



### タスク 3 -Azure のエンタープライズアプリケーションでSalesforceを登録する。

Azure ADをクラウドアプリケーションと連携する場合、エンタープライズアプリケーションで登録を行います。

1. Webブラウザを開き、「[https://portal.azure.com](https://portal.azure.com)」へアクセスします。

2. サインインが求められます。以下のユーザー名とパスワードを入力し、サインインしてください。

     > 注:XXXXはご自身のメールアドレス番号になります。

     | 項目                      | 値                                  |
     | ------------------------- | :---------------------------------- |
     | メール、電話、またはskype | `admin@XXXXXXXXXXX.onmicrosoft.com` |
     | パスワード                | ラボで使用しているパスワードと同じ                        |

     

3. 上部検索バーに「エンタープライズ アプリケーション」と入力し、該当サービスをクリックします。

     ![aad-sso-018](./media/aad-sso-018.BMP)

     

4. 「エンタープライズ アプリケーション | すべてのアプリケーション」ブレードが表示されます。

5. 一覧上にある「Salesforce」をクリックします。

6. 作成をクリック後、画面が遷移され「Salesforce | 概要」ブレードが表示されます。画面左側の「管理」カテゴリにある「シングルサインオン」をクリックします。

     ![aad-sso-022](./media/aad-sso-022.BMP)

     

7. 「Salesforce | シングル サインオン」ブレードが表示されます。シングルサインオン方式の選択で「SAML」をクリックします。

     ![aad-sso-023](./media/aad-sso-023.BMP)

     

8. 「Salesforce | SAML ベースのサインオン」画面が表示されます。画面中央の必須項目を埋める必要があります。画面はこのままにし、次のタスクへ進みます。

![aad-sso-024](./media/aad-sso-024.BMP)



### タスク 4 -SSOに必要な情報をSalesforceのプロパティから取得する

1. Webブラウザを開き「[https://login.salesforce.com/](https://login.salesforce.com/)」へアクセスします。

2. サインインが求められます。以下のユーザー名とパスワードを入力し、サインインしてください。

     > 注:XXXXはご自身のメールアドレス番号になります。

     | 項目       | 値                   |
     | ---------- | :------------------- |
     | ユーザー名 | `admin@XXXXXXXXXXX.onmicrosoft.com` |
     | パスワード | ラボで使用しているパスワードと同じ |

     ![aad-sso-025](./media/aad-sso-025.BMP)

     

3. サインイン前に電話番号を登録する画面が表示される場合があります。その場合はご自身の電話番号を登録するか「後で知らせる」または「電話を登録しません」のいずれかを選択してください。

     > 注:必ずしも表示されるとは限りません。

     ![aad-sso-026](./media/aad-sso-026.BMP)

     

4. 「設定|ホーム画面」が表示されます。画面左側のツリーより「会社の設定」を展開し、「私のドメイン」をクリックします。

     ![aad-sso-027](./media/aad-sso-027.BMP)

     

5. 「私のドメイン」画面が表示されます。画面中央にある「現在の [私のドメイン] の URL」に記載あるドメインをメモします。

     > 例：ctcXXXX-dev-ed.my.salesforce.com

     ![aad-sso-028](./media/aad-sso-028.BMP)

     

6. 情報の取得は以上です。一度画面を最小化してください。



### タスク 5 -エンタープライズアプリケーションのSSO設定を行い検証する

エンタープライズアプリケーションのSSO設定に必要項目を入力し、SalesforceとAzureADユーザーがSSOできるか検証をします。

1. Azure Portalの「Salesforce | SAML ベースのサインオン」を再び表示します。

     > 注:Webブラウザと閉じた場合は、上部検索バーに「エンタープライズアプリケーション」と入力し、サービスをクリックします。
     >
     > 　 その後「エンタープライズ アプリケーション | すべてのアプリケーション」ブレードより「Salesforce」をクリックします。
     >
     > 　 さらに「Salesforce | 概要」ブレードから左側ツリーにある「シングルサインオン」をクリックします。

     ![aad-sso-029](./media/aad-sso-029.BMP)

     

2. 「Salesforce | SAML ベースのサインオン」ブレードの画面中央にある「基本的なSAML構成」の「編集」をクリックします。

3. 「基本的な SAML 構成」画面が表示されます。次の項目を入力し「保存」をクリックします。

     > 注:XXXXはご自身のメールアドレス番号になります。

     > 注:[あなたがメモしたURL]はタスク4-5でメモしたURLです。

     | 項目                   | 値                                                           |
     | ---------------------- | ------------------------------------------------------------ |
     | 識別子(エンティティID) | `https://あなたがメモしたURL`　　　例:`https://ctcXXXX-dev-ed.my.salesforce.com` |
     | 応答 URL               | `https://あなたがメモしたURL`　　　例:`https://ctcXXXX-dev-ed.my.salesforce.com` |
     | サインオン URL         | `https://あなたがメモしたURL`　　　例:`https://ctcXXXX-dev-ed.my.salesforce.com` |

     ![aad-sso-030](./media/aad-sso-030.BMP)

     

4. 一度、「基本的な SAML 構成」の画面を閉じます。「Salesforce でシングル サインオンをTest」というメッセージでテストが要求されたら「いいえ、あとでtestします」を選択してください。

5. 「Salesforce | SAML ベースのサインオン」ブレードに戻り、画面中央にある「SAML署名証明書」項目の「フェデレーション メタデータ XML」をダウンロードします。

     > 注:ダウンロードしたデータは、次のタスクで使用します。

     ![aad-sso-035](./media/aad-sso-035.BMP)

     

6. 「Salesforce.xml」が自身のPCにダウンロードされたことを確認します。

     ![aad-sso-036](./media/aad-sso-036.BMP)

     

7. この後の操作で再びAzure Portalを使用します。一度画面を最小化してください。



### タスク 6 -Salesforce上でフェデレーションメタデータを登録する

検証が完了したため、別ユーザーでも恒久的にサインインできるようAzure上で生成されたフェデレーションメタデータをSalesforceへアップロードします。

1. SalesforceのWebブラウザ画面に戻ります。

     ![aad-sso-037](./media/aad-sso-037.BMP)

     

2. 画面右側のツリーから「ID」を展開し、「シングルサインオン設定」を表示します。

     ![aad-sso-038](./media/aad-sso-038.BMP)

     

3. 「SAML シングルサインオン構成」の「メタデータファイルから新規作成」をクリックします。

4. 「SAML シングルサインオン構成」画面の中央にある「ファイルを選択」をクリックし、前の手順でダウンロードした「Salesforce.xml」をアップロードします。アップロード後に「作成」をクリックします。

     ![aad-sso-040](./media/aad-sso-040.BMP)

     

5. 「SAML シングルサインオン構成」画面が切り替わります。次の項目を入力し「保存」をクリックします。

     | 項目      | 値      |
     | --------- | ------- |
     | 名前      | EntraID |
     | API参照名 | EntraID |

     > 下記の画面キャプチャは「AzureAD」と古い内容になっています。

     ![aad-sso-041](./media/aad-sso-041.BMP)

     

6. 「SAML シングルサインオン構成」が表示されます。

     ![aad-sso-042](./media/aad-sso-042.BMP)

     

7. 画面左側ツリーにある「会社の設定」を展開し、「私のドメイン」を選択します。

     ![aad-sso-043](./media/aad-sso-043.BMP)

     

8. 「私のドメイン」画面の下部に「認証設定」があります。編集をクリックします。

     ![aad-sso-044](./media/aad-sso-044.BMP)

     

9. 「認証設定」画面で「認証サービス」があります。「EntraID」にチェックを入れて「保存」をクリックします。

     > 画面キャプチャは「AzureAD」と古い内容になっています。

     ![aad-sso-045](./media/aad-sso-045.BMP)

     

10. これでSalesforce側の設定は終わりです。一度画面を最小化してください。



### タスク 7 -エンタープライズアプリケーションでSSOさせたいユーザーを設定する

AzureADユーザーでSalesforceにSSOする場合、ユーザーと役割を設定する必要があります。

1. Azure Portalの画面に戻ります。

   > 注:Webブラウザと閉じた場合は、上部検索バーに「エンタープライズアプリケーション」と入力し、サービスをクリックします。
   >
   > 　 その後「エンタープライズ アプリケーション | すべてのアプリケーション」ブレードより「Salesforce」をクリックします。
   >
   > 　 さらに「Salesforce | 概要」ブレードから左側ツリーにある「シングルサインオン」をクリックします。

   ![aad-sso-046](./media/aad-sso-046.BMP)

   

2. 画面左側ツリーにある「所有者」をクリックします。その後、「+追加」をクリックします。

   ![aad-sso-047](./media/aad-sso-047.BMP)

   

3. 「所有者の選択」画面が表示されます。`admin@XXXXXXXXXXX.onmicrosoft.com`のユーザーをクリックし、「選択」をクリックします。

   ![aad-sso-048](./media/aad-sso-048.BMP)

   

4. 「Salesforce | 所有者」ブレードの一覧に選択したユーザーが表示されたことを確認します。

5. 画面左側ツリーにある「ユーザーとグループ」をクリックします。その後「+ユーザーまたはグループの追加」をクリックします。

   ![aad-sso-049](./media/aad-sso-049.BMP)

   

6. 「割り当ての追加」画面で、次の項目を入力し「割り当て」をクリックします。

   > 注:XXXXはご自身のメールアドレス番号になります。

   > 参考:ここで指定している「ロール」はSalesforceに登録してあるユーザーの「プロファイル」と一致させています。
   >
   > 　　  Salesforceの画面で[管理]→[ユーザ]より確認できます。

   | 項目                     | 値                                  |
   | ------------------------ | ----------------------------------- |
   | ユーザー                 | `admin@XXXXXXXXXXX.onmicrosoft.com` |
   | ロールを選択してください | System Administrator                |

   ![aad-sso-050](./media/aad-sso-050.BMP)

   

7. 「Salesforce | ユーザーとグループ」ブレードの一覧に選択したユーザーが表示されたことを確認します。

8. これで、SSOさせるユーザーの登録が完了しました。一度画面を最小化してください。

   > 参考:この手順ではAzureADにあるadminユーザーとSalesforceのユーザーが一致していたため、
   >
   > 　　 ユーザーとグループの追加でSSOを構成することができます。
   >
   > 　　 別途ユーザーをSSOさせたい場合、AzureADユーザーとSalesforceの両方で
   >
   > 　　 同一のサインインIDと役割(プロファイル)を構成しないとSSOは成功しません。
   >
   > 　　ユーザーを自動同期させる場合は、別途「プロビジョニング」の設定が必要になります。



### タスク 8 -SalesforceにSSOでサインインする

1. Webブラウザで「`https://あなたがメモしたURL`」にアクセスします。

   > 例:`https://ctcXXXX-dev-ed.my.salesforce.com`

   > 注:タスク5-3で入力したURLです。

2. サインイン画面の下部にある「次を使用してログイン EntraID」をクリックします。

   ![aad-sso-052](./media/aad-sso-052.BMP)

   

3. Microsoftのサインイン画面が表示されます。次の項目を入力し「割り当て」をクリックします。

   > 注:XXXXはご自身のメールアドレス番号になります。

   | 項目                | 値                                |
   | ------------------- | --------------------------------- |
   | メール、電話、Skpye | admin@XXXXXXXXXXX.onmicrosoft.com |
   | パスワード          | ラボで使用しているパスワードと同じ                      |

   

4. Salesforceの画面が表示されました。これでEntraIDユーザーを使用してSalesforceにSSOすることが可能になります。

   ![aad-sso-053](./media/aad-sso-053.BMP)



この演習では、エンタープライズアプリケーションを使用して、Salesforceとシングルサインオンを構成しました。




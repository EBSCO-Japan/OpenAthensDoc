| ソース | 翻訳元 URL | 翻訳日 |
| ---- | ---- | ---- |
| OpenAthens Docs | [Access URLs](https://docs.openathens.net/libraries/Access-URLs.11305260.html) | 2022-05-23 |

# アクセスURL

OpenAthensは[いくつかのタイプのリソース](https://docs.openathens.net/libraries/What-are-the-differences-between-federated-and-proxied-resources%3F.10847272.html)に接続でき、すべての人に役立つアクセスURLをリソースカタログに含めることができない場合があります。場合によっては、事前構成されたアクセスURLがまったくないことがあります。これはカタログカードのアイコンで示され、通常、OpenAthensフェデレーションではないリソースに適用されます:

![icon](https://docs.openathens.net/libraries/11305260/URL.Icon.png?inst-v=f79effe0-b2fa-4160-b4b6-3b5d44ab3470)

OpenAthensリソースには、ほとんどの場合、アクセスURLがあります。他のフェデレーションのリソースでは、問題が発生します。初期のフェデレーションが計画および実装された方法により、フェデレーションのメタデータを介してアクセスURLを提供する標準的な方法がなく、データが無いためです。 

これが意味することは、新しいリソースをパーミッション・セットに割り当てる前に、アクセスURLを確認し、必要に応じて追加して（リソースプロバイダーに「WAYFlessURL」を要求する）、リソースをユーザーに割り当てる前にテストする必要があるということです。

リソースのアクセスURLは、順次追加できますが、OpenAthens フェデレーション外のリソースについては、プロバイダと直接の関係がないため、どのようなアクセス URL になるのか見当がつくかもしれませんが、私たち自身がアクセスできるわけではないので、テストすることはできません。アクセスURLを追加する必要がある場合は、サービスプロバイダーから提供された、アクセス可能なURLをお伝えいただくと、お役に立てるかもしれません。私たちのサービスデスクはそれをチェックし、カタログのリソースに追加し、すべての人が利用できるようにします。

Redirectorリンクがユーザーに表示される場合、通常、アクセスURLは指定されたターゲットURLにバイパスされます。

## URL フォーマット: 
フェデレーションのリソースのアクセスURLには、一般的に2つのタイプがあります（Where Are You Fromページでユーザーが組織を選択するステップを回避できるため、WAYFless URLと呼ばれることもあります）。

サービスのサインオンポイントにentityIDと、場合によってはターゲットのページを渡すのが主要なタイプです：

https\://sp.resource.example/oa/signin?entityID=https://idp.eduserv.org.uk/openathens または

https\://sp.resource.example/oa/signin?entityID=https://idp.eduserv.org.uk/openathens&target=https://sp.resource.example/content

これらのリンクには、ご自身のentityIDをお使いください。

2つ目のタイプは、サービスのentityIDと、時には自分のログインページへのターゲットページを渡すような場合です。

https\://login.test.openathens.net/saml/1/sso/yourdomain.tld/c/ukfed?providerId=https\://sp.resource.example/entity&shire=https\://sp.resource.example/rcv/saml1/POST または

https\://login.test.openathens.net/saml/1/sso/yourdomain.tld/c/ukfed?providerId=https\://sp.resource.example/entity&shire=https\://sp.resource.example/rcv/saml1/POST&target=https\://sp.resource.example/content

この2番目のタイプは、2005年にSAML2に取って代わられたSAML1標準に基づいているため、稀であるだけでなく、可能な限り避けるべきです。

その他のタイプは...予測できず、一貫性もありません。このような場合、適切なアクセスURLをベンダーに問い合わせ、手動で適用する必要があります。
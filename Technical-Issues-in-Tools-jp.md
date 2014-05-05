# Technical Issues in Tools (Day 1)

Posted on March 19, 2014 by Geoff Evans  
The Technical Issues in Tools Development Roundtables continue to be one of the most popular roundtable sessions at GDC. Below are Aaron's updated and expanded notes from the Day 1 session.  
2014/3/19 のゴフ エヴァンスの投稿  
ツール開発ラウンドテーブルはGDCで最もポピュラーなラウンドテーブルの１つとして続いています。  
下記は、1日目のセッションのAaronの議事録です。

## How do you develop or transition to new tools or frameworks?
新しいツールやフレームワークをどのように開発・導入するか

* Requirements gathering was reinforced as a primary need. We touched on the time-worn topic of goal vs. feature requests.  
要件の収集が主要な必要性と補強された。「ゴール達成VS機能追加」という時代的に使い古された話題に触れた
* It appears that while may people still have tools and engine code running together (editor in runtime) many people have moved away from this. In a nutshell, the lack of abstraction between source data and runtime data that many engines suffer from is seen as a failure.  
多くの人々は離れてきたが、人々しばらくは、まだツールとエンジンコードを（ランタイムにエディタで）一緒に利用するようである。
一言で言えば、多くのエンジンが苦しんでいる元データとランタイムデータの間の抽象化の欠落は失敗と見なされている。
* People encouraged developing your tools as close to your existing pipelines as possible. If it make sense for data to be edited in Maya, for example, you should write your tools there.  
人々は、可能な限り既存のパイプラインにあなたのツールが近づくように開発を促す。たとえば、データはMayaで編集されているのであれば、Maya上のツールを書くべきです。
* Usability continues to be a primary concern from our users. Click reduction and other ways of reducing friction in your tools is more important with each iteration.  
使いやすさは、ユーザーからの主要な関心事であり続けている。クリック数の削減や、それ以外でもツール内のストレスを減らす方法は、各イテレーションでより重要となっている。
* Teams that have good relationships with their users express developing better tools through this interaction. Developers need to “eat their own dog food”.  
ユーザーとの良好な関係を持っているチームは、対話を通してより良いツールを開発し届けます。開発者は、「自分でドッグフードを食べる」必要があります。 
訳注：ツールを実際に使用してユーザビリティをテストする事を、ドッグフーディングと呼ぶ表現からきています
* Larger teams with more open tools are starting to employ TechArt and users to create tools. This can be accomplished though extensibility points like “scripting” or plugin based solutions. I thought of the macro recording system in VS as an example and something that could be accomplished with a well defined command architecture at the base level of the tools.  
オープンなツールを多く使用する大規模なチームはテクニカルアーティストをツールの作成に採用し始めています。
「スクリプト」やプラグインなどをベースにしたソリューションの拡張点を通して、ツールを作成します。
私は、VSの中のマクロ記録システムがこの例であると考えますし、ツールの基本レベルで明確に定義されたコマンドアーキテクチャを達成できるものもあるでしょう。
* When teams allow for user created tools, there is no expectation of support, although there is consideration for useful tools and promoting them to fully supported versions.  
チームはユーザーが作成したツールを導入する場合、使い勝手の良いツールで、充分なサポートされたバージョンを推し進めたと考えても、サポートは期待できません。
* Automation came up in this topic (more on it below), but design your tool with automation in mind from the ground up. Command line driving (for batch/script files) or being able to launch tools to specific configurations (open a tool with a specific document or screen up) were given as examples.  
自動化をこのトピックで扱いましたが（下記で、より詳しく説明します）、ツールをゼロから設計する際は自動化を念頭に置いてください。（バッチ/スクリプトファイルの場合）コマンドライン実行や、（特定のドキュメントを読み込んでツールを立ち上げたり、起動時の）特別の設定でツールを起動することができることが例として挙げられた。

## Automation
自動化

* Using automation to reduce redundancy in testing was called out as a win for some studios.  
いくつかのスタジオでは、テストで冗長性を減らすために自動化を利用するのは、勝利の方程式と呼ばれた。
* When automating tests, target low-hanging fruit (game won't launch) first. This reduces your overall testing overhead.  
自動化テストをする際は、最初に(ゲームは開始しない)簡単な仕事をターゲットとしてください。これによって、全体的なテストのオーバーヘッドが削減されます。
* With properly automated tests, your QA focus can be on breaking the tool or game, not smoke testing.  
適切に自動化されたテストでは、あなたのQAの焦点が、スモークテストでなく、ツールやゲームが壊れることにあてられます。
訳注：スモークテストとは、修正した点に関しての検証のことです。
* Unit tests are employed, but mostly at the system library level. Mixed bag on if this is “Test First” development or validation testing.  
ユニットテストを採用したものの、大部分はシステム・ライブラリ・レベルにとどまっています。これを「テストファースト」開発や検証テストと寄せ集めてください。
* One large studio ran into an issue where their testing data piled up before users were able to start analysis. This led to problems in responding to the testing and they recommended getting eyes on test data as soon as it is available to avoid piling up.  
ある大手スタジオは、ユーザーが分析を開始できるようにする前のテストデータを積み上げたところで問題に遭遇しました。
これは、テストへ対応する際に問題が多く出ました。テストデータをすぐに積み上げないように目を慣らすのを推奨しました。
* If your tool support automation, good user feedback is essential. Automating a dozen steps only to have it crap out on the end with a generic failure message is not productive.  
あなたのツールが自動化をサポートするには、優れたユーザーからのフィードバックが不可欠です。一般的な失敗メッセージを最後に機能しなくなる1ダース(12)もの工程を自動化することは生産が高くありません。
* While it may initially introduce multiple steps to accomplish an action, it is best practice not to overload functionality (big-red button). You can always automate multiple steps together later if necessary.  
自動化しようとすることは、最初にアクションを達成するために多数のステップを導入しているかもしれませんが、機能を詰め込みすぎない(大きな１つの赤いボタンにしない)ようお勧めします。必要ならば常に後で一緒に多数のステップを自動化することができます。
* Most studios appear to be using a hybrid homegrown/3rd-party automation solution. Python->RPC was one solution. One studio is using Jenkins CI to schedule the automation testing.  
ほとんどのスタジオは、内製/3rd-partyの自動化ソリューションを混ぜて使用しているようです。Python->RPCは一つのソリューションです。あるスタジオは、自動テストのスケジューリングにJenkins CIを使用しています。

## Build It or Buy It?
作るか買うか

* As an industry we are still struggling to justify investment in tools development.  
業界として、我々は、まだ、ツール開発への投資を正当化するために苦労している。
* Communication and commitment scheduling are important as we scale to support multiple teams.  
複数のチームをサポートするように拡大する為に、コミュニケーションとコミットメントのスケジューリングは重要です。
* More testing and support were called out as pros for licensing software.  
より多くのテストやサポートは、ソフトウェアをライセンス販売することの良い点のように呼ばれていました。
* Bloat and stuff you don't need were called out as cons.  
肥大化して、必要のない機能が積み上がることは、欠点のように呼ばれていました。
* One question presented that I thought was thought provoking was “Is your pipeline so unique as to necessitate custom tools?”  
示唆に富んでいると思える質問は、「カスタムツールを必要とするほど、あなたのパイプラインはとても特別ですか？」というものです。
* If you license code, it is important to socialize the understanding of the code to avoid problems using unfamiliar code.  
コードのライセンスを取得した場合には、なじみのないコードを使用したことによる問題を回避するために、コードの理解をグループで行うのが重要である
* Studios that did not have buy in from the top on either side of this question encountered issues when problems arose.  
問題が生じた際に、この質問のいずれかの側の最善案（カスタムしないかコードを理解する）を持たなかったスタジオは、問題が発生しました。
* You must understand the complete cost of licensing a solution when committing to it. Integration, maintenance, extensibility, are all aspects of development that must be accounted for.  
あなたは採用するときにソリューションのライセンスの完全なコストを理解する必要があります。統合、保守、拡張性は、開発の上で考慮すべきすべての側面である。

## Interop
相互運用

* 80% of attendees commented on having to deal with some level of interop.  
参加者の80%いくつかのレベルの相互運用を扱っているとコメントした
* You have to be very mindful at design time (architecture level) of the performance implications of interop as well as have a good strategy to deal with it.  
あなたは、設計する際に、それを取り扱うための良い戦略を持っていると同様に、相互運用の（アーキテクチャレベルでの）パフォーマンスへの影響について非常に気に留めなくてはなりません。
* Some studios are doing automation assisted interop either with automation code generation for marshalling or some other approach like runtime reflection.  
いくつかのスタジオでは、マーシャリング(データ項目を集めて, 受け取り側の仕様に合った形式に変換して, メッセージバッファに詰め込むプロセス)やランタイムリフレクションのようなアプローチによる自動コード生成で自動化支援される相互運用を行っている。
* A few studios called out using sockets or RPC for interop. WCF has also been used. Most are doing some kind of C++/CLI with parallel interfaces. When I asked about orthoginal interfaces to abstract a different interface on the tools side from the runtime side, there were a lot of strange looks.  
少数のスタジオは、相互運用のためにソケットやRPCを使用しているそうです。 WCF(Windows Communication Foundation)も使用されている。ほとんどは、パラレルインタフェースを備えたC++/CLIの様なものを使っている。私はランタイム側とツール側の異なるインターフェイスを抽象化する直交インタフェースについて尋ねたところ、奇妙な見た目のものがたくさんありました。

## Unit Testing
ユニットテスト

* 40% of attendees were doing some kind of unit testing.  
40% の参加者が何らかのユニットテストをしている
* 20% were using it for compliance testing.  
20%がコンプライアンステストに使っている
* NUnit, Python and VS Unit testing were called out as things being done.  
NUnit, Python や Visual Studio ユニットテスティングが使われているものとしてあげられた
* A few shops are doing Test First development for tools.  
少数のツール屋はツール開発にテストファースト開発を行っている
* Some do testing on the build server as a commit blocking check.  
何人かは、ビルドサーバーでテストを行い、コミットをブロックするチェックを行っていた

## Build Systems
ビルドシステム

* 40% are using Jenkins.  
40%は Jenkins を使っている
* Team City, Buildforge, Cruise Control, Cruise, Go and homegrown solutions were called out.  
Team City, Buildforge, Cruise Control, Cruise, Goや 内製のソリューションが利用例として挙げられた

## OpenCL and Compute
OpenCLやコンピュートシェーダ

* Limited adoption of these technologies.  
これらの技術は部分的にしか取り入れられていない
* OpenCL is being used by one team in their collision generation pipeline.  
OpenCL は、１つのチームだけで、コリジョン生成パイプラインで使われていた
* When used, it was called out to provide real-time feedback to the user to avoid painful issues during development.  
導入することができれば、リアルタイムフィードバックが得られるようになり、開発中の苦痛が和らいでいくと強く言っていた

## Version Control
バージョン管理

* 80% are using Perforce  
80%は Perforce を使っている
* Some studios are using Git for code.  
いくつかのスタジオは、コード管理にgitを使っている
* Mercurial, SVN, Plastic SCN, Shotgun were called out as other solutions being used.  
他のツールとしては、Mercurial, SVN, Plastic SCN, Shotgun が挙げられた
* Object DBs were inquired about specifically for asset version control.  
他のオブジェクトDBも、特定のアセット管理として聞かれた
* A few shops are still using some form of live data, but this seems to be both smaller shops or studios with a very different deployment methodology.  
少数の会社では、まだライブデータの用紙を使っている。しかし、非常に異なる開発手法をとる会社のようである。
* Bigger studios have started to use CI for their data and using a label or other method to sync last good data. We avoid this by requiring items to build before submit.  
大きなスタジオほど、データにCIを使い始めている。ラベルなどで直前の正常なデータへの同期方法を持っている。我々はsubmitする前にアイテムをビルドすることを強要することで、これらを避けている。

## How do you know when your tools are bad?
使っているツールがイケてないタイミングをどのように知る？

* Question asked at the start of the session but crammed into the last few minutes.  
セッションの最初に質問したが、最後の数分間に詰め込まれた。
* Listen to your users.  
ユーザーに聞く
* Callstacks in all crash reports.  
全てのクラッシュレポートのコールスタック
* Automated bug reporting.  
自動化されたバグレポート
* Office hours to share the love of supporting the tools.  
オフィス時間における、ツールをサポートする愛情の共有
* Eat your own dogfood/Follow your users. Schedule time every iteration to spend time with the users to gather data.  
自分でドッグフードする/ユーザーを追う。データを集めるために各イテレーションでユーザーとして過ごす時間を確保する
* Automatic usage information from tools. Implement a system to record how your users use the tools to find bad practices, features that are not used. Get rid of features that no one uses to reduce maintanance overhead.  
ツールから自動でユーザー情報を取得する。ユーザーがツールをどのように使ってバッドプラクティスを見つけるか・使われない機能は何かを記録するシステムを実装する。メンテナンス負荷を減らすために使われていない機能を削除する。
* Features vs. Goals. Work with your users to solve problems, don't just blindly implement requests.  
機能追加 vs ゴール達成。ユーザの問題を解決するために働いて、やみくもに要求を追加するのはやめよう

#Technical Issues in Tools (Day 2)

Posted on March 23, 2014 by Geoff Evans  
Below are Aaron's expanded notes from the Day 2 roundtable.  
2014/3/23 のゴフ エヴァンスの投稿  
下記は、2日目のラウンドテーブルのAaronの議事録です。

## Dealing Asset Respository Growth
アセットリポジトリの増大の取り扱い

* 85% are using Perforce for dealing with content data.  
85% がコンテンツデータの取り扱いに Perforce を使っている
* Use max revisions to control repository size.  
リポジトリサイズの制御には、最大リビジョン数が使われている。
* Consider using Linux as your Perforce Server platform as it handles scalability concerns better. If using Linux with Windows clients, use case insensitivity from the start to avoid issues.  
Perforce サーバーのプラットフォームにLinuxを使った方が、スケーラビリティの点では良い。Linuxサーバー を Windows クライアントで使う際には、問題を回避するのに最初から大文字と小文字を区別しないで使用しよう。
* Various user stories were presented on repository growth.  
リポジトリの増大にさまざまなユーザーストーリーが披露された
* Offsite locations, forwarding replicas, edge servers are the new Perforce hotness. Proxies have use but are on the decline.  
Perforceの新しい良い機能は、Offsite locations, forwarding replicas, edge serversだ。プロキシーは使われているが、下り坂にある。

## Dealing Asset Respository Growth (Gen4)
アセットリポジトリの増大の取り扱い（第4世代）

* This question was specifically targetted at dealing with the size of assets that are being generated for Gen4 (PS4/XBone) consoles.  
これは、第4世代 (PS4/XBone) コンソールのために作られたアセットのサイズを扱う特別な対象に関する質問だ。
* If using Unreal, keep package sizes as small as possible.  
Unreal を使っているなら、パッケージのサイズをできる限り小さくしよう
* Most people are conditioning as much as possible on the client and not checking in built data.  
ほとんどの人々は、クライアント側でほとんどの条件付けをして、ビルドデータで確認していない。
* 10% check in built data.  
10%がビルドデータでチェックしている
* 30% are doing full nightly cooks of all assets for validation or to prime a cook cache.  
30%が検証やキャッシュを準備するために毎晩全てのアセットを処理している
* Consider pushing cooked data from the client to the cache, but beware of dependency issues!  
処理されたデータをクライアントからキャッシュに送ることを考えよ。ただし、依存性に注意！
* One studio mentioned that it would take them 1 month to clean build the data for their game.  
あるスタジオは、ゲームのデータを一からクリーンビルドするのに1カ月かかると言った。
* Build and keep your dependency tree in memory as much as possible. DB would be an option here.  
依存性ツリーはできる限りメモリ上で構築・維持すべきで、DBはオプションにするべきである。
* Write dependancy data on first build. Be sure to invalidate it appropriately.  
最初のビルドで依存性データを書きだして、適切に無効にせよ

## Build Tools for Data
データのビルドツール

* 10% use 3rd party solution.  
10%が3rdパーティ製品を使っている
* 80% use a home grown solution.  
80%が内部で育ててきたソリューションを使っている
* ANT, Grant/Javascript, CruiseControl with MSBuild, Unity, Incredibuild were called out as solutions being used.  
ANT, Grant/Javascript, CruiseControl with MSBuild, Unity, Incredibuildが使っているソリューションとして挙げられた

## Cross-platform Data
クロスプラットフォームデータ

* 60% say their data build system support multiple platforms as a core concept.  
60% がデータビルドシステムのコアなコンセプトとしてマルチプラットフォームのサポートを言う

## Pipeline “Chugging”
パイプラインの「一気飲み」

* How do you deal with the stalls and other implications of gating based on results of CI?  
どのようにしてCIの結果に基づいて、ストールやゲートを閉じたことによる他の影響に対処しますか？
* 60% or more have someone who wrangles their CIS system.  
60%以上は、それらのCIS（お客さま情報システム）のシステムについて世話をする人を確保しています。
* If your CIS system is crunching on data, make that apparent/inspectable by your users.  
あなたのCISのシステムがデータについてバリバリ壊れている場合は、そのことをあなたのユーザに見える化/検査できるようにしてください。
* Make public or VERY PUBLIC who is breaking your builds.  
あなたのビルド壊している人を公開、または派手に公開してください。
* If you find yourself in situations of repeated breakage, put your senior staff in charge. They can often apply the necessary leverage to communicate the importance of not breaking builds to your staff.  
あなたが自分自身で繰り返して破壊していたのならば、あなたのシニアスタッフを担当として置いてください。彼らは頻繁に、あなたのスタッフにビルドを壊さないことの重要性を伝えるために必要な影響力を行使することができるでしょう。
* Beware of the implications of queuing your submits if you have some kind of automated validation on submit.  
submitする際の自動化されたバリデーションを持っている場合は、サブミットのキューイングへの影響に注意してください。
* Very few teams are using a different data version for development than production. Many support single file loading as an iteration tool to mitigate this.  
非常に少数のチームは、生産よりも開発のために、さまざまなバージョンのデータを使用している。多くのチームでは、これを軽減するために、イテレーションのツールとして、単一のファイルのロードのサポートをしている。
* Reducing the quality of conditioned data was called out as one way to speed up iterative build times.  
条件付きデータの品質を低下させるのは、反復ビルド時間を高速化するための一つの方法として提唱されました。

## Continuous Deployment
継続的開発

* Few do full deployment of tools and game as monolithic installer.  
ほとんど誰も単一のインストーラーとしてツールやゲームを開発していない
* TeamCity generates artifacts that are web accessible.  
TeamCity は、ウェブアクセスできるものとして成果物を作成している
* Minority of teams have beta and release versions of tools.  
少数派が、ツールのベータとリリースのバージョンを作成しています。
* One team does 2 week iterations and no teams indicated that they are on “Live” tools that have not passed some kind of validation.  
あるチームは２週間のイテレーションを行い、どのチームも何らかのバリデーションをパスしないような「生きている」ツールはないと表明した

## Automated Testing
テスト自動化

* Outside of core systems there were some questions related to test falures due to changes to requirements that invalidate tests.  
コア・システムの外であるが、テストを無効にする要件の変更に起因する失敗テストに関していくつかの質問があった。
* Test “things that don't change”. I read into this as “test things that have stable requirements”.  
テストは「変更しないもの」。私は、これを「安定した要求をもつテストの事」としてこれを読みます。
* Make sure that the people writing the code are also maintaining the tests.  
コードを書く人々がテストもメンテナンスしていることを確かめてください。
* Have QA modify test scripts.  
QAにテスト・スクリプトを修正させてください。
* Are issues with test failure an issue with the developer or somewhere else? Make sure that your devs are running your tests.  
失敗テストの原因は、開発者や、どこかにほかに要因がありますか？開発チームがあなたのテストを実行していることを確かめてください。
* Some teams do a pre-submit validation where tests are run and reject on failure. Introduces build queueing!  
いくつかのチームは、テストを実行し、失敗した場合に拒否するsubmitの事前検証を行います。ビルドのキューイングシステムを導入せよ！
* One team locked the entire perforce depot on broken build. They said they had 48 devs. A lot of raised eyebrows and questions on this one.  
あるチームは、ビルドが壊れた場合にPERFORCEデポを完全にロックしています。彼らは開発者は48人と述べた。たくさん眉がつりあがり、チーム内で質問が飛び交った。
* Use staged builds in your CI system.  
CIシステムの中でステージング環境へデプロイするビルドを使ってください
* Make the team responsible for build stability.  
チームにビルド安定性の責任を負わせてください
* Use nightly functionality testing.  
毎夜の機能テストを行ってください
* Block builds when critical path (does game boot?) breaks.  
クリティカルパス（ゲームは起動する？）が壊れたらビルドを止めてください
* How do you deal with non-deterministic systems? Kill non-determinism in your code with fire.  
どのように非決定的なシステムに対処しますか？やばいからコードの中の非決定性を殺せ。
* Use perforce file locks to indicate code that is under test to inform other users and prevent submit contention.  
他のユーザーに通知して、サブミットの競合を防ぐために、コードがテスト中であることを示すためのPERFORCEのファイルロックを使用してください。

## Scaling Automated Testing
テスト自動化の拡張

* What do you do when your platform has expensive dev hardware?  
プラットフォームに高価な開発ハードウェアがあるときはどうしますか？
* Use kits on the floor when they are idle.  
それらが遊んでいて床に置かれているなら使おう
* Use PC build to test bulk of changes and test only what is necessary on target hardware.  
大部分の変更のテストにはPCビルドを使い、ターゲットハードウェアは必要な時だけ使おう。

## Other Topics
その他トピックス

* Large Photoshop files.   
大きなPhotoshopファイル
* Forwarding Replica and Edge servers (Perforce)   
レプリカとエッジサーバーに転送する (Perforce)
* Compress files on server if you have the horsepower.   
処理能力があるなら、サーバー上でファイルを圧縮する
* Use different (smaller) data formats.   
異なる（より小さな）データフォーマットを使う
* Almost 100% of teams store source PSD files despite large sizes.  
ほとんど100%のチームが巨大にも関わらず元のPSDファイルを保存する

# Technical Issues in Tools (Day 3)
Posted on March 23, 2014 by Geoff Evans  
Below are Aaron's expanded notes from the Day 3 roundtable.  
2014/3/23 のゴフ エヴァンスの投稿  
下記は、3日目のラウンドテーブルのAaronの議事録です。

## Content Creation Tools and Usability
コンテンツ生成ツールと使い勝手

* Use controls and metaphors that are familiar to your content creators. For example, if you are a Maya shop, use Maya camera controls and key bindings for the 3D view of you editors.  
コンテンツ作成者によく知られている制御法とメタファーを使用してください。つまり、会社がMayaを使っているのなら、あなたのエディタの3DビューにMayaのカメラコントロールとキーバインディングを使用してください。
* Informal poll indicated that most teams are not creating art tools when they can use an off-the-shelf solution.  
非公式の調査では、既製のソリューションを使用することができるなら、ほとんどのチームはアートツールを作成していないことがわかりました。
* When considering a custom solution, make sure that the productivity gains over an off-the-shelf solution are enough of a win to justify. This may not just be time savings, there are things to consider like interruption to flow where straight time comparisons will not be the correct metric to use.  
独自開発を検討する際に、既製のソリューションに比べて正当化するための生産性上昇が十分勝利できることを確認してください。これは単に時間の節約ではない場合があります、直接的な時間比較が採用するのに正しい計量ではない、開発フローの途切れのようなような考慮すべき点があるかも知れません。
* Considering open sourcing your tools as an attempt to push the industry in the direction of open source solutions.  
オープンソースソリューションの方向に業界を推進する試みとして、あなたのツールをオープンソース化することを考えてください。
* Leverage your core competencies. If you are not a strong tool shop, consider other options like contracting your tool development.  
コアコンピタンスにてこ入れしてください。強いツール屋でないなら、あなたのツール開発を収縮する等の他の選択肢を考えてください。
* Consider proceedural solutions to reduce the need to create content.  
コンテンツを作成する必要性を減らすためにプロシージャル手法を検討してください。
* You have to answer this question for your situation, “When do you make vs. when do you buy?”.  
あなたは自分の状況照らし合わせて、この質問に答える必要があります。「あなたが買う時と作る時はいつですか？」

## Communication Across the Industry
会社をまたがったコミュニケーション

* IGDA Tools SIG. Toolsmiths mailing list and Google group.  
IGDA Tools SIG, Toolsmiths(ツール鍛冶屋)のメーリングリストとグーグルグループ
* Open Source Tools  
オープンソースツール
** Sony ATF -- Sony's internal tools made open. https://github.com/SonyWWS/ATF  
Sony ATF -- ソニーの内部ツールがオープンになった。 https://github.com/SonyWWS/ATF
** Nocturnal Initiative -- Insomniac's tools made open. https://github.com/nocturnal  
Nocturnal Initiative -- Insomniacのツールがオープンになった。 https://github.com/nocturnal
** Helium Project -- Open source tools (Geoff's project). https://github.com/HeliumProject/Helium  
Helium Project -- オープンソースツール（Geoffの project）https://github.com/HeliumProject/Helium
* Seeders vs. Leechers will be something to be aware of. This is probably more of a problem in larger corporate environments that evaluate studio performance on straight ROI which doesn't take into account value of contributions to shared code.  
種をまく人VSダウンロードだけする人は注意すべきものになるでしょう。これはおそらく、共有コードへの貢献の価値を考慮していない直接的なROIでの職場でのパフォーマンスを評価するような、大企業での環境でより問題になるでしょう。
* A Microsoft employee reported a change in Microsoft's position on open source code and is not encouraging it use internally when appropriate.  
マイクロソフト従業員のレポートによれば、マイクロソフトは、オープンソースコードに対する姿勢を変更して、私物化するようであれば内部で使うことは推奨されていない。
* Microsoft codeplex as a place to look for code for tools. https://www.codeplex.com/  
Microsoft codeplex はツールのコードを探すための場である。 https://www.codeplex.com/
* It seems that the sclaing issues of tools development (we need more and better tools to control content costs) is pushing these changes.  
ツール開発のスケーリングの問題（我々には、コンテンツ作成コストを制御するためのよりよいツールが必要である）は、これらの変化を推進するように思う。
* Having a culture of openness and honesty about the state of your tools will motivate investment in improvement.  
あなたのツールに関してオープン性と誠実さの文化を持たせれば、改良への投資を動機づけるでしょう。
* Make Tools part of your studio's story.  
あなたのスタジオの物語の一部としてツールを使おう

## Features vs. Goals
機能追加 対 ゴール達成

* As tool developers we frequently get feature specifications as opposed to a problem statement outlining the problem we are being asked to solve.  
ツール開発者であれば、解決が求められている問題点をまとめた問題提起ではなく、機能仕様書がしばしば与えられるでしょう。
* Keep asking “Why?” to drill down and determine core needs.  
コアのニーズを深堀りし、決定するために「何故」と問い続けよ
* Empathize with your user's workflows to understand what they are trying to accomplish.  
何が彼らが遂行しようとしてるのか理解するために、ユーザーのワークフローに感情移入せよ
* Set reasonalbe per-iteration objectives and execute.  
現実的なイテレーションごとの目的を設定し、実行せよ
* Don't commit to doing the work until you get a goal to reach. Don't give in and just blindly implement a request.  
ゴールにたどり着くまでcommitするな。あきらめて、やみくもに要求を実装するな。

## Referencing Assets
アセットの参照

* Use an asset database to look up unique identitifer to the location of the data you are looking for.  
探しているデータの位置を断定するためにアセットデータベースを使いなさい
* Guid based references allow each machine to generate unique ids without requiring a central repository.  
グローバルユニークIDベースの参照は、中心リポジトリの存在なしに各マシンでユニークなIDを生成できる
* Many studios are doing local syncs and build a local database for query optimization.  
多くのスタジオでは、クエリー最適化のためにローカルマシンでの同期とローカルデータベースを構築している。
* Model your dependencies and allow for reverse depenency inspection to determine if and where something is used.  
依存性をモデル化し、何かが使われた場合や場所を決定するための逆依存性探索ができるようにしよう
* Consider using the file system as the authority and your DB as an optimization.  
信頼性のためにファイルシステムを、最適化としてあなたのDBを使うことを考えよ
* How do you do depenency tracking?  
どのように依存性を追跡しますか？
* Scan changed files.  
変更したファイルを追跡せよ
* Use file System notification to lauch dependency generation.  
依存性生成を立ち上げる時にファイルシステムの通知をつかう
* Use offline automated systems to look for and purge cruft from you system.  
システムのお粗末な部分を探して粛清するためにオフラインの自動化システムを使う
* Model your package dependencies.  
パッケージの依存性をモデル化せよ
* Use a “don't break, don't block” model to keep your users running.  
ユーザーが立ち止まらないように「壊れていないなら、ブロックしない」を使え
* Can you make the game run with no data? This is ideal.  
データなしにゲームを動かすことができますか？これが理想です。
* You can use known-good default assets as stand-ins for broken data as opposed to holding your user's up.  
ユーザーが壊れたデータで万歳しないように、知られた良いディフォルトデータを組み込めるでしょ

## Asset Organization
アセットの組織化

* Organize any way the users want. It is typically not a good idea to enforce an organization strategy.  
ユーザーが好きなように整理します。通常は、組織化の戦略を強制するのは良い考えではありません。
* Implement a tagging system for your assets to allow them to be orgainzed or queried in a logical way based on usage.  
使用法に応じてロジカルな方法で組織化や問い合わせできるようにアセットへのタグ付けを実装せよ
* Beware of chaos in the tagging system.  
タグ付けシステムに潜むカオスに注意せよ
* Use case insensitive tagging and tag synonyms to keep from having data break apart with user generated tags.  
ユーザー生成タグがバラバラになっても大丈夫なように、大文字小文字を区別しないタグ付けおよび、タグ同義語を使用せよ。
* Impelement top-level search criteria to wrangle organization.  
組織化を世話するためにトップレベルの検索基準を実装せよ
* Tag objects with unique identifier like user or machine name. Guids are frequently used in this situation.  
タグは、ユーザー名やマシン名の様なユニークIDを持つオブジェクト。グローバルユニークIDはしばしばこのシチュエーションで使われる
* Implement search tools. Help users find the content they want to use.  
検索ツールを実装せよ。彼らが使いたいコンテンツを見つけるのを助けよ
* Allow the game ot select assets (though some kind of in-game UI like a pointer) and open them in your tool. Think hitting a button while playing a level and this opening the level in your editor.  
（ポインタのようなゲーム内UI等を通して）ゲームでアセットが選択できるようにして、それらをツール内でも開けるようにしなさい。レベルを遊んでいる中でボタンを押せるようにして、エディタ内でレベルを開けるように考えてください。
* Push data form the game into tools. This can be used to identify problems to be fixed. You could have a system that would implement workflows like change requests at the asset level.  
ゲームからツールにデータを送るようにすれば、問題点を特定して修正するために使えるだろう。アセットレベルで修正を要求するようなようなワークフローを実装するシステムが持てるだろう。
* Implement metadata tagging to remove ambiguity on errors.  
エラーにおけるあいまいさを取り除くために、メタデータのタグ付けを実装せよ
* Implement a system to find and remove duplicate assets.  
重複したアセットを見つけて取り除くためのシステムを実装せよ

## Best Practices
ベストプラクティス

* Build in robust and automated crash reporting.  
堅牢で自動化されたクラッシュレポートシステムを構築せよ
* Use Perforce and use it well.  
Perforce を使って使いこなせ
* Support and use branching in both code and data. You have to make that E3 build don't you?  
コードとデータでブランチをサポートし保守せよ。E3ビルドを作らなくてはならないだろ？
* Log4NET as a logging option.  
ログ取得の候補としてLog4NETを考えろ

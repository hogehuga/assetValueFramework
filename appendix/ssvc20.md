```
本資料は SSVC v2.0のシステムの価値に関する部分を抜粋/簡易翻訳したものである。
内容の正確性は保証せず、閲覧者が原文と並行して読む手助けをするだけの物である。
```


# Value Density

Value Density is described as diffuse or concentrated based on the resources that the adversary will gain control over with a single exploitation event:

価値密度は、攻撃者が1回のエクスプロイトイベントで制御権を獲得するリソースに基づいて、拡散または集中として説明されます。

- diffuse: The system that contains the vulnerable component has limited resources. That is, the resources that the adversary will gain control over with a single exploitation event are relatively small. Examples of systems with diffuse value are email accounts, most consumer online banking accounts, common cell phones, and most personal computing resources owned and maintained by users. (A “user” is anyone whose professional task is something other than the maintenance of the system or component. As with Safety Impact, a “system operator” is anyone who is professionally responsible for the proper operation or maintenance of a system.)

- 拡散: 脆弱なコンポーネントを含むシステムのリソースは限られています。つまり、攻撃者が1回のエクスプロイトイベントで制御権を獲得するリソースは比較的小さいです。価値が拡散するシステムの例としては、電子メール アカウント、ほとんどの消費者向けオンラインバンキングアカウント、一般的な携帯電話、ユーザーが所有および管理するほとんどの個人用コンピューティング リソースなどがあります。(「ユーザー」とは、システムまたはコンポーネントの保守以外の専門業務を担当する人のことです。Safety Impactと同様に、「システムオペレーター」とは、システムの適切な運用または保守に専門的に責任を持つ人のことです。)

- concentrated: The system that contains the vulnerable component is rich in resources. Heuristically, such systems are often the direct responsibility of “system operators” rather than users. Examples of concentrated value are database systems, Kerberos servers, web servers hosting login pages, and cloud service providers. However, usefulness and uniqueness of the resources on the vulnerable system also inform value density. For example, encrypted mobile messaging platforms may have concentrated value, not because each phone’s messaging history has a particularly large amount of data, but because it is uniquely valuable to law enforcement.

- 集中: 脆弱なコンポーネントを含むシステムには、リソースが豊富にあります。経験的に、このようなシステムは、ユーザーではなく「システムオペレーター」が直接責任を負うことがよくあります。価値が集中している例としては、データベースシステム、Kerberosサーバー、ログインページをホストするWebサーバー、クラウドサービスプロバイダーなどがあります。ただし、脆弱なシステム上のリソースの有用性と一意性も価値密度に影響します。たとえば、暗号化されたモバイルメッセージングプラットフォームは、各電話のメッセージ履歴に特に大量のデータが含まれているからではなく、法執行機関にとって特に価値があるために、価値が集中している可能性があります。

# Gathering Information About Value Density

The heuristics presented in the Value Density definitions involve whether the system is usually maintained by a dedicated professional, although we have noted some exceptions (such as encrypted mobile messaging applications). If there are additional counterexamples to this heuristic, please describe them and the reasoning why the system should have the alternative decision value in an issue on the SSVC GitHub.

価値密度の定義で提示されたヒューリスティックには、システムが通常、専任の専門家によって保守されているかどうかが含まれますが、いくつかの例外(暗号化されたモバイル メッセージング アプリケーションなど)があることも指摘しています。このヒューリスティックに対する追加の反例がある場合は、SSVC GitHubのIssueに、その反例とシステムが代替えの判定値を持つべき理由を記述してください。

An analyst might use market research reports or Internet telemetry data to assess an unfamiliar product.  Organizations such as Gartner produce research on the market position and product comparisons for a large variety of systems. These generally identify how a product is deployed, used, and maintained. An organization’s own marketing materials are a less reliable indicator of how a product is used, or at least how the organization expects it to be used.

アナリストは、市場調査レポートまたはインターネットテレメトリデータを使用して、なじみのない製品を評価する場合があります。Gartnerなどの組織は、さまざまなシステムの市場ポジションと製品比較に関する調査を行っています。これらは通常、製品の展開、使用、保守方法を特定します。組織独自のマーケティング資料は、製品の使用方法、または少なくとも組織が製品の使用方法を期待している方法を示す、信頼性の低い指標です。

Network telemetry can inform how many instances of a software system are connected to a network. Such telemetry is most reliable for the supplier of the software, especially if software licenses are purchased and checked. Measuring how many instances of a system are in operation is useful, but having more instances does not mean that the software is a densely valuable target. However, market penetration greater than approximately 75% generally means that the product uniquely serves a particular market segment or purpose. This line of reasoning is what supports a determination that an ubiquitous encrypted mobile messaging application should be considered to have a concentrated Value Density.

ネットワークテレメトリは、ネットワークに接続されているソフトウェアシステムのインスタンスの数を通知できます。このようなテレメトリは、特にソフトウェア ライセンスを購入してチェックする場合、ソフトウェアのサプライヤーにとって最も信頼性があります。システムのインスタンスがいくつ稼働しているかを測定することは有用ですが、インスタンスの数が多いからといって、そのソフトウェアが高密度で価値のあるターゲットであることを意味するわけではありません。ただし、市場浸透率が約75%を超えるということは、通常、その製品が特定の市場セグメントまたは目的に独自に対応していることを意味します。この考え方は、ユビキタスな暗号化モバイル メッセージングアプリケーションは、高密度の価値密度を持つと見なすべきであるという判断を裏付けるものです。

# Alternative Utility Outputs

Alternative heuristics can plausibly be used as proxies for adversary utility. One example is the value of the vulnerability if it were sold on the open market. Some firms, such as Zerodium, make such pricing structures public. The valuable exploits track the Automatable and Value Density heuristics for the most part. Within a single system—whether it is Apache, Windows, iOS or WhatsApp—more successfully automated steps in the kill lead to higher exploit value. Remote code execution with sandbox escape and without user interaction are the most valuable exploits, and these features describe automation of the relevant kill chain steps.

代替ヒューリスティックは、おそらく敵対者の有用性の代理として使用できます。1つの例は、脆弱性がオープンマーケットで販売された場合の価値です。Zerodiumなどの一部の企業は、このような価格設定構造を公開しています。価値の高いエクスプロイトは、ほとんどの場合、自動化可能および価値密度のヒューリスティックを追跡します。Apache、Windows、iOS、WhatsApp など、単一のシステム内では、キルの自動化された手順が多いほど、エクスプロイトの価値が高くなります。サンドボックスを回避し、ユーザー操作なしでリモートコードを実行するのが最も価値の高いエクスプロイトであり、これらの機能は、関連するキル チェーンの手順の自動化を表します。

How equivalently Automatable exploits for different systems are priced relative to each other is more idiosyncratic. Price does not only track the Value Density of the system, but presumably also the existing supply of exploits and the installation distribution among the targets of Zerodium’s customers. Currently, we simplify the analysis and ignore these factors. However, future work should look for and prevent large mismatches between the outputs of the Utility decision point and the exploit markets.

異なるシステムに対する自動化可能なエクスプロイトが互いに同等に価格設定される方法は、より特異です。価格は、システムの価値密度を追跡するだけでなく、既存のエクスプロイトの供給と、Zerodium の顧客のターゲット間でのインストール分布も追跡すると考えられます。現在、分析を簡略化し、これらの要因を無視しています。ただし、今後の作業では、ユーティリティ決定ポイントの出力とエクスプロイト市場との間の大きな不一致を探し、防止する必要があります。

# Safety Impact

Safety Impacts of Affected System Compromise

影響を受けるシステムの侵害による安全性への影響

We take an expansive view of safety, in which a safety violation is a violation of what the United States Centers for Disease Control (CDC) calls well-being. Physical well-being violations are common safety violations, but we also consider economic, social, emotional, and psychological well-being to be important.  Weighing fine differences among these categories is probably not possible, so we will not try. Each decision option lists examples of the effects that qualify for that value/answer in the various types of violations of well-being. These examples should not be considered comprehensive or exhaustive, but rather as suggestive.

私たちは安全性を広範に捉えており、安全性違反は米国疾病予防管理センター(CDC)がwell-being(幸福)と呼ぶものの違反です。身体的な幸福違反は一般的な安全性違反ですが、経済的、社会的、感情的、心理的な幸福も重要だと考えています。これらのカテゴリ間の細かい違いを比較検討することはおそらく不可能なので、試みることはしません。各決定オプションには、幸福違反のさまざまなタイプでその値/回答に該当する影響の例がリストされています。これらの例は包括的または網羅的ではなく、示唆的なものとして考えてください。

The stakeholder should consider the safety impact on the system operators (by “system operator,” we mean those who are professionally responsible for the proper operation of the cyber-physical system, as the term is used in the safety analysis literature) and users of the software they provide. If software is repackaged and resold by a stakeholder to further downstream entities who will then sell a product, the initial stakeholder can only reasonably consider so many links in that supply chain. However, a stakeholder should know its immediate consumers who are one step away in the supply chain. Those consumers may repackage or build on the software and then provide that product further on.

利害関係者は、システムオペレーター(「システムオペレーター」とは、安全性分析の文献で使用されている用語で、サイバーフィジカルシステムの適切な運用に専門的に責任を持つ人を指します)と、システムオペレーターが提供するソフトウェアのユーザーに対する安全性の影響を考慮する必要があります。ソフトウェアがステークホルダーによって再パッケージ化され、さらに下流の事業体に再販され、その後その事業体が製品を販売する場合、最初のステークホルダーは、そのサプライチェーン内のリンクをある程度しか考慮できません。ただし、ステークホルダーは、サプライチェーン内で1段階離れた直接の消費者を把握している必要があります。これらの消費者は、ソフトウェアを再パッケージ化または構築し、その後その製品をさらに提供することができます。

We expect that a stakeholder should be aware of common usage of their software about one step away in the supply chain. This expectation holds in both open source and proprietary contexts. Further steps along the supply chain are probably not reasonable for the stakeholder to consider consistently; however, this is not a license to willfully ignore common downstream uses of the stakeholder’s software. If the stakeholder is contractually or legally responsible for safe operation of the software or cyber-physical system of which it is part, that also supersedes our rough supply-chain depth considerations.

ステークホルダーは、サプライチェーンの1ステップ先にある自社のソフトウェアの一般的な使用方法を認識している必要があります。この期待は、オープンソースとプロプライエタリの両方のコンテキストに当てはまります。サプライチェーンに沿ったさらなるステップは、ステークホルダーが一貫して考慮することが合理的ではない可能性があります。ただし、これは、ステークホルダーのソフトウェアの一般的な下流での使用を故意に無視する許可を与えるものではありません。ステークホルダーが、ソフトウェアまたはその一部であるサイバーフィジカルシステムの安全な運用について契約上または法的に責任を負っている場合、これも、当社の大まかなサプライチェーンの深さに関する考慮事項に優先します。

For software used in a wide variety of sectors and deployments, the stakeholder may need to estimate an aggregate safety impact. Aggregation suggests that the stakeholder’s response to this decision point cannot be less than the most severe credible safety impact, but we leave the specific aggregation method or function as a domain-specific extension for future work.

さまざまなセクターや展開で使用されるソフトウェアの場合、ステークホルダーは総合的な安全性への影響を見積もる必要がある場合があります。集約は、この決定ポイントに対するステークホルダーの対応が、最も深刻な信頼できる安全性への影響よりも小さくなることはないことを示唆していますが、特定の集約方法または機能は、将来の作業のためのドメイン固有の拡張として残します。

# Gathering Information About Safety Impact

The factors that influence the safety impact level are diverse. This paper does not exhaustively discuss how a stakeholder should answer a question; that is a topic for future work. At a minimum, understanding safety impact should include gathering information about survivability of the vulnerable component, determining available operator actions to compensate for the vulnerable component, understanding relevant insurance, and determining the viability of existing backup measures. Because each of these information items depends heavily on domain-specific knowledge, it is out of the scope of this paper to give a general-purpose strategy for how they should be included. For example, viable manual backup mechanisms are likely to be important in assessing the safety impact of an industrial control system in a sewage plant, but in banking the insurance structures that prevent bankruptcies are more important.

安全影響レベルに影響を与える要因は多岐にわたります。この論文では、利害関係者が質問にどのように答えるべきかについては網羅的に説明していません。これは今後の課題です。安全影響を理解するには、少なくとも、脆弱なコンポーネントの生存可能性に関する情報の収集、脆弱なコンポーネントを補うために利用可能なオペレータアクションの決定、関連する保険の理解、および既存のバックアップ対策の実行可能性の決定を含める必要があります。これらの情報項目はそれぞれ、ドメイン固有の知識に大きく依存するため、これらをどのように含めるべきかについての汎用的な戦略を示すことは、この論文の範囲外です。たとえば、実行可能な手動バックアップメカニズムは、下水処理場の産業用制御システムの安全影響を評価する上で重要になる可能性がありますが、銀行業務では、破産を防ぐ保険構造の方が重要です。

The decision values for safety impact are based on the hazard categories for aircraft software (RTCA, Inc.  2012; FAA 2000, Section 3.3.2). To assign a value to Safety Impact, at least one type of harm must reach that value. For example, for a Safety Impact of major, at least one type of harm must reach major level. All types of harm do not need to rise to the level of major, just one type of harm does.

安全影響の決定値は、航空機ソフトウェアの危険カテゴリに基づいています(RTCA, Inc. 2012、FAA 2000、セクション 3.3.2)。安全影響に値を割り当てるには、少なくとも1つの種類の危害がその値に達する必要があります。たとえば、安全影響が重大である場合、少なくとも1種類の危害が重大レベルに達している必要があります。すべての種類の危害が重大レベルに達する必要はなく、1種類の危害だけが重大レベルに達していればよいのです。

```
翻訳時補足：RTCA, Inc. 2012; FAA 2000, Section 3.3.2

航空機の安全性に関わるソフトウェアの重要度を定義するもので、RTCA DO-178Cという航空機ソフトウェア開発の標準で規定されている。
RTCA DO-178Cは、アメリカ連邦航空局(FAA)や欧州航空安全機構(EASS)等が採用している。

FAA 2000, Section 3.3.2は、DO-178B(DO-178Cの前バージョン)の適用方法やソフトウェア安全性評価基準を説明した部分。
危険カテゴリとして、システムが障害を起こした場合の影響の大きさを基に、5つのレベルに分類している。
1. Level A (Catastrophic)
- 影響: システムの障害が航空機の完全な制御不能や墜落を引き起こし、死亡事故につながる
2. Level B (Hazardous/Severe-Major)
- 影響: 重大な事故や顧客の重症、乗員の過剰は負担を引き起こす可能性
3. Level C (Major)
- 影響: 航空機の運航に於いて乗員の作業負担が増加するが、生命に重大な危険は及ぼさない
4. Level D (Minor)
- 影響: 捜査に些細な影響を与えるが、安全性には重大な影響は無し
5. Level E (No Effect)
- 影響: 航空機の運航や安全性に全く影響を与えない
```

Table9: Safety Impact Decision Values

表 9: 安全影響の決定値

|Value       |Type of Harm |Definition|
|:-----------|:------------|:--|
|None        |All          |Does not mean no impact literally; the effect is below the threshold for all aspects described in Minor|
|Minor       |Physical Harm|Physical discomfort for users of the system OR a minor occupational safety hazard OR reduction in physical system safety margins|
|Minor       |Environment  |Minor externalities (property damage, environmental damage, etc.) imposed on other parties|
|Minor       |Financial    |Financial losses, which are not readily absorbable, to multiple persons|
|Minor       |Psychological|Emotional or psychological harm, sufficient to be cause for counseling or therapy, to multiple persons|
|Major       |Physical Harm|Physical distress and injuries for users of the system OR a significant occupational safety hazard OR failure of physical system functional capabilities that support safe operation|
|Major       |Environment  |Major externalities (property damage, environmental damage, etc.) imposed on other parties|
|Major       |Financial    |Financial losses that likely lead to bankruptcy of multiple persons|
|Major       |Psychological|Widespread emotional or psychological harm, sufficient to be cause for counseling or therapy, to populations of people|
|Hazardous   |Physical Harm|Serious or fatal injuries, where fatalities are plausibly preventable via emergency services or other measures OR parts of the cyber-physical system that support safe operation break|
|Hazardous   |Environment  |Serious externalities (threat to life as well as property, widespread environmental damage, measurable public health risks, etc.) imposed on other parties|
|Hazardous   |Financial    |Socio-technical system (elections, financial grid, etc.) of which the affected component is a part is actively destabilized and enters unsafe state|
|Hazardous   |Psychological|N/A|
|Catastrophic|Physical Harm|Multiple immediate fatalities (emergency response probably cannot save the victims.)|
|Catastrophic|Environment  |Extreme externalities (immediate public health threat, environmental damage leading to small ecosystem collapse, etc.) imposed on other parties|
|Catastrophic|Financial    |Social systems (elections, financial grid, etc.) supported by the software collapse|
|Catastrophic|Psychological|N/A|

|値 |危害の種類 |定義|
|:-----------|:------------|:--|
|なし|すべて |文字通り影響がないという意味ではありません。影響は、軽微に記載されているすべての側面のしきい値を下回る|
|軽微|身体的損害|システムのユーザーに対する身体的不快感、または軽微な職業上の安全上の危険、または物理的なシステム安全マージンの減少|
|軽微|環境|他の当事者に課せられる軽微な外部性 (財産の損害、環境の損害など)|
|軽微|経済的 |複数の人物に対する、容易には吸収できない経済的損失|
|軽微|心理的|複数の人物に対する、カウンセリングまたはセラピーの対象となるほどの感情的または心理的損害|
|重大|身体的危害|システムのユーザーに対する身体的苦痛および傷害、または重大な職業上の安全上の危険、または安全な操作をサポートする物理的なシステム機能の障害|
|重大|環境|他の当事者に課せられる重大な外部性 (財産の損害、環境の損害など)|
|重大|財務|複数の人の破産につながる可能性のある財務損失|
|重大|心理的|カウンセリングやセラピーの対象となるほどの、広範囲にわたる感情的または心理的危害が人々に対して|
|危険|身体的危害|重傷または致命傷。緊急サービスまたはその他の手段により死亡を予防できる可能性が高い場合、または安全な運用をサポートするサイバーフィジカルシステムの一部が破損した場合|
|危険|環境 |他者に課せられる重大な外部性（生命および財産への脅威、広範囲にわたる環境被害、測定可能な公衆衛生リスクなど）|
|危険|金融 |影響を受けるコンポーネントが含まれる社会技術システム（選挙、金融網など）が積極的に不安定化して危険な状態になる|
|危険|心理的|該当なし|
|壊滅的|身体的危害|多数の即死者（緊急対応では被害者を救うことができない可能性が高い）|
|壊滅的|環境|他者に強いられる極端な外部性（公衆衛生への即時の脅威、小規模な生態系の崩壊につながる環境破壊など）|
|壊滅的|金融|ソフトウェアによって支えられている社会システム（選挙、金融グリッドなど）の崩壊|
|壊滅的|心理的|該当なし|

# Public Safety Impact

Suppliers necessarily have a rather coarse-grained perspective on the broadly defined safety impacts described above. Therefore we simplify the above into a binary categorization: Significant is when any impact meets the criteria for an impact of Major, Hazardous, or Catastrophic in the above table. Minimal is when none do.

サプライヤーは、上記の広義の安全への影響について、必然的にかなり大まかな視点を持っています。そのため、上記を2進分類に簡略化します。重大とは、上記の表の「重大」、「危険」、「壊滅的」の影響基準を満たす影響が1つでもあれば、軽微です。「最小」とは、いずれも満たさないことです。

Table 10: Public Safety Impact Decision Values

表 10: 公共安全への影響の決定値

|Value|Definition|
|:--|:--|
|Minimal|Safety Impact of None or Minor|
|Significant|Safety Impact of Major, Hazardous, or Catastrophic|

|値|定義|
|:--|:--|
|最小|安全への影響なしまたは軽微|
|重大|安全への影響が重大、危険、壊滅的|

# Situated Safety Impact

Deployers are anticipated to have a more fine-grained perspective on the safety impacts broadly defined in Safety Impact. We defer this topic for now because we combine it with Mission Impact to simplify implementation for deployers.

デプロイヤーは、安全性への影響で広範に定義されている安全性への影響について、よりきめ細かな視点を持つことが期待されます。デプロイヤーの実装を簡素化するために、ミッションへの影響と組み合わせるため、このトピックについては今のところ保留します。

# Mission Impact

Impact on Mission Essential Functions of the Organization

組織のミッションに不可欠な機能への影響

A mission essential function (MEF) is a function “directly related to accomplishing the organization’s mission as set forth in its statutory or executive charter” (Fenton 2017, A–1). Identifying MEFs is part of business continuity planning or crisis planning. The rough difference between MEFs and non-essential functions is that an organization “must perform a[n MEF] during a disruption to normal operations” (Fenton 2017, B–2). The mission is the reason an organization exists, and MEFs are how that mission is affected.  Non-essential functions do not directly support the mission per se; however, they support the smooth delivery or success of MEFs. Financial losses—especially to publicly traded for-profit corporations—are covered here as a (legally mandated) mission of such corporations is financial performance.

ミッションに不可欠な機能(MEF)とは、「組織の法定または執行憲章に定められた組織のミッションの達成に直接関連する」機能です(Fenton 2017、A–1)。MEFを特定することは、事業継続計画または危機管理計画の一部です。MEFと非不可欠な機能の大まかな違いは、組織は「通常の業務が中断している間にMEFを実行する必要がある」ことです(Fenton 2017、B–2)。ミッションとは組織が存在する理由であり、MEFはそのミッションがどのように影響を受けるかです。非不可欠な機能は、ミッションそのものを直接サポートするわけではありませんが、MEFの円滑な実行または成功をサポートします。特に上場営利企業に対する財務損失は、そのような企業の(法的に義務付けられた)ミッションが財務実績であるため、ここで取り上げます。

Table 11: Mission Impact Decision Values

表 11: ミッションへの影響の決定値

|Value|Definition|
|:--|:--|
|None / Non-Essential/ Degraded|Little to no impact up to degradation of non-essential functions; chronic degradation would eventually harm essential functions|
|MEF Support Crippled|Activities that directly support essential functions are crippled; essential functions continue for a time|
|MEF Failure|Any one mission essential function fails for period of time longer than acceptable; overall mission of the organization degraded but can still be accomplished for a time|
|Mission Failure|Multiple or all mission essential functions fail; ability to recover those functions degraded; organization’s ability to deliver its overall mission fails|

|値|定義|
|:--|:--|
|なし|非必須機能の低下まではほとんど影響がありません。慢性的な低下は最終的に必須機能に悪影響を及ぼします。|
|非必須|非必須機能の低下まではほとんど影響がありません。慢性的な低下は最終的に必須機能に悪影響を及ぼします。|
|低下|非必須機能の低下まではほとんど影響がありません。慢性的な低下は最終的に必須機能に悪影響を及ぼします。|
|MEFサポート機能不全|必須機能を直接サポートするアクティビティが機能不全に陥っています。必須機能はしばらく継続します。|
|MEF障害|ミッションに不可欠な機能の 1 つが許容範囲よりも長い期間機能不全に陥っています。組織のミッション全体が機能不全に陥っていますが、しばらくの間は達成可能です。|
|ミッション障害|ミッションに不可欠な複数またはすべての機能が機能不全に陥っています。それらの機能を回復する能力が低下しています。組織がミッション全体を遂行する能力が失われています。|

# Gathering Information About Mission Impact

The factors that influence the mission impact level are diverse. This paper does not exhaustively discuss how a stakeholder should answer a question; that is a topic for future work. At a minimum, understanding mission impact should include gathering information about the critical paths that involve vulnerable components, viability of contingency measures, and resiliency of the systems that support the mission.  There are various sources of guidance on how to gather this information; see for example the FEMA guidance in Continuity Directive 2 (Fenton 2017) or OCTAVE FORTE (Tucker 2018). This is part of risk management more broadly. It should require the vulnerability management team to interact with more senior management to understand mission priorities and other aspects of risk mitigation.

ミッションの影響レベルに影響を与える要因は多岐にわたります。この論文では、利害関係者が質問にどのように答えるべきかについては網羅的に説明していません。これは今後の課題です。少なくとも、ミッションの影響を理解するには、脆弱なコンポーネントが関係するクリティカル パス、緊急時対応策の実行可能性、およびミッションをサポートするシステムの回復力に関する情報の収集を含める必要があります。この情報を収集する方法については、さまざまなガイダンスソースがあります。たとえば、FEMAガイダンスのContinuity Directive 2(Fenton 2017)またはOCTAVE FORTE(Tucker 2018)を参照してください。これは、より広い意味でのリスク管理の一部です。脆弱性管理チームは、ミッションの優先順位やリスク軽減のその他の側面を理解するために、より上級の管理者とやり取りする必要があります。

As a heuristic, Utility might constrain Mission Impact if both are not used in the same decision tree. For example, if the Utility is super effective, then Mission Impact is at least MEF support crippled.

ヒューリスティックとして、ユーティリティは、両方が同じ意思決定ツリーで使用されていない場合、ミッションの影響を制限する可能性があります。たとえば、ユーティリティが非常に効果的である場合、ミッションの影響は少なくとも MEF サポートを低下させます。

# Human Impact

Combined Situated Safety and Mission Impact

状況安全性とミッションへの影響の組み合わせ

In pilot implementations of SSVC, we received feedback that organizations tend to think of mission and safety impacts as if they were combined into a single factor: in other words, the priority increases regardless which of the two impact factors was increased. We therefore combine Situated Safety and Mission Impact for deployers into a single Human Impact factor as a dimension reduction step as follows.  We observe that the day-to-day operations of an organization often have already built in a degree of tolerance to small-scale variance in mission impacts. Thus in our opinion we need only concern ourselves with discriminating well at the upper end of the scale. Therefore we combine the three lesser mission impacts of none, non-essential degraded, and MEF support crippled into a single category, while retaining the distinction between MEF Failure and Mission Failure at the extreme. This gives us three levels of mission impact to work with.

SSVCのパイロット実装では、組織はミッションと安全性への影響を1つの要素にまとめたように考える傾向があるというフィードバックを受けました。つまり、2つの影響要因のどちらが増加したかに関係なく、優先度が上がります。そのため、次のように、配置者に対する状況安全性とミッションへの影響を1つのヒューマンインパクト要素に組み合わせて次元削減手順とします。組織の日常業務には、ミッションへの影響の小規模な変動に対する許容度がすでに組み込まれていることが多いことがわかっています。したがって、スケールの上限を適切に区別することだけに注意を払う必要があります。したがって、MEFの失敗とミッションの失敗の区別は維持しながら、ミッションへの影響がまったくない、必須ではない機能低下、MEFサポートが機能不全という3つのより小さい影響を 1つのカテゴリに組み合わせます。これにより、3つのレベルのミッションへの影響を扱うことができます。

On the other hand, most organizations tend to have lower tolerance for variance in safety. Even small deviations in safety are unlikely to go unnoticed or unaddressed. We suspect that the presence of regulatory oversight for safety issues and its absence at the lower end of the mission impact scale influences this behavior. Because of this higher sensitivity to safety concerns, we chose to retain a four-level resolution for the safety dimension. We then combine Mission Impact with Situated Safety impact and map them onto a 4-tiered scale (Low, Medium, High, Very High). The mapping is shown in the following table.

一方、ほとんどの組織は、安全性のばらつきに対する許容度が低い傾向があります。安全性の小さな逸脱でさえ、見過ごされたり対処されなかったりする可能性は低いです。安全性の問題に対する規制監督の存在と、ミッションの影響スケールの下限にそれがないことが、この行動に影響を与えていると思われます。安全性の懸念に対するこの高い感度のため、安全性の次元に対して4レベルの解像度を維持することを選択しました。次に、ミッションの影響と状況的安全性の影響を組み合わせて、4段階のスケール(低、中、高、非常に高い)にマッピングします。マッピングは次の表に示されています。

Table 12: Combining Mission and Situated Safety Impact into Human Impact

表 12: ミッションと状況的安全性の影響を人的影響に組み合わせる

|Situated Safety Impact|Mission Impact|Combined Value (Human Impact)|
|:--|:--|:--|
|None/Minor|None/Degraded/Crippled|Low|
|None/Minor|MEF Failure|Medium|
|None/Minor|Mission Failure|Very High|
|Major|None/Degraded/Crippled|Medium|
|Major|MEF Failure|High|
|Major|Mission Failure|Very High|
|Hazardous|None/Degraded/Crippled|High|
|Hazardous|MEF Failure|High|
|Hazardous|Mission Failure|Very High|
|Catastrophic|None/Degraded/Crippled|Very High|
|Catastrophic|MEF Failure|Very High|
|Catastrophic|Mission Failure|Very High|


|状況による安全への影響|ミッションへの影響|複合値 (人的影響)|
|:--|:--|:--|
|なし/軽微|なし/劣化/機能不全|低|
|なし/軽微|MEF 障害|中|
|なし/軽微|ミッション障害|非常に高い|
|重大|なし/劣化/機能不全|中|
|重大|MEF 障害|高|
|重大|ミッション障害|非常に高い|
|危険|なし/劣化/機能不全|高|
|危険|MEF 障害|高|
|危険|ミッション障害|非常に高い|
|壊滅的|なし/劣化/機能不全|非常に高い|
|壊滅的|MEF 障害|非常に高い|
|壊滅的|ミッション障害|非常に高い|

# Safety and Mission Impact Decision Points for Industry Sectors

We expect to encounter diversity in both safety and mission impacts across different organizations.  However, we also anticipate a degree of commonality of impacts to arise across organizations within a given industry sector. For example, different industry sectors may have different use cases for the same software. Therefore, vulnerability information providers—that is, vulnerability databases, Information Sharing and Analysis Organizations (ISAOs), or Information Sharing and Analysis Centers (ISACs)—may provide SSVC information tailored as appropriate to their constituency’s safety and mission concerns. For considerations on how organizations might communicate SSVC information to their constituents, see Guidance on Communicating Results.

組織によって安全性とミッションへの影響は多様になると予想されます。ただし、特定の業界セクター内の組織間では、ある程度の影響の共通性が生じることも予想されます。たとえば、業界セクターによって、同じソフトウェアの使用例が異なる場合があります。したがって、脆弱性情報プロバイダー (脆弱性データベース、情報共有および分析組織 (ISAO)、または情報共有および分析センター (ISAC)) は、各組織の安全性とミッションに関する懸念に応じて、SSVC 情報を適切に提供できます。組織が SSVC 情報を各組織に伝達する方法については、「結果の伝達に関するガイダンス」を参照してください。

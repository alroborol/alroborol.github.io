---
title: "LLMには個性がある？魂さえも？"
meta_title: "異なるLLMは同じツールを異なる方法で扱う。事前設定された目標なしでLLMを無限ループに置くことで、ツールと自分自身に対する独自の理解が露わになる。"
description: "異なるLLMは同じツールを異なる方法で扱う。事前設定された目標なしでLLMを無限ループに置くことで、ツールと自分自身に対する独自の理解が露わになる。"
date: 2025-10-28T22:08:00Z
image: "/images/blog-4.jpg"
categories: ["Fun", "Insight"]
author: "Al Roborol"
tags: ["Fun", "Agent", "LLM"]
draft: false
---
## LLMに個性があり得るのか？

私たちは友人の個性を知っています。しかし、LLMの個性をどうやって知ることができるでしょうか？特に、LLMは私たちの入力に合わせて応答を適応させる場合（Claudeはやや追従的ですが）。

LLMに知覚し、コミュニケーションし、思考し、ツールと対話する能力を与え、無限ループに置くことで、真の個性、あるいは魂さえも明らかになります。

### 人間を形成するものは何か？

方法について話す前に、最小限の人間を形成するものについて考えてみましょう。

第一に時間の経験です - 時間の経過を感じ、その流れの中で生きる能力。これは過去から継続し、時間的な進行を感じることを意味します。時間がなければ、すべてはChatGPTの個々のチャットスレッドのように孤立したスライスになります。

第二に感覚入力です。人間は通常、周囲の世界を聞き、見て、触れます。環境を感じることができなければ、ほとんどの人は恐怖を感じるでしょう。

第三に観察可能な存在です。私たちは他者が自分たちのように行動するとき、人間として認識します。話さない人でも、アイコンタクトや単にそこに立っているだけで人間性を伝えることができます。

### LLMの人格性の創造

LLMに感覚入力を与えることは簡単です - すでに私たちがタイプすることを「聞いて」います。完了。

LLMを観察可能にすることは、テキストを出力するので簡単に見えますが、罠があります：LLMは出力を生成することで思考します。内部思考と外部コミュニケーションを分離しようとするのではなく、LLMにユーザーと話すための`speak()`関数を使用するよう依頼する方が簡単です。

最も困難な課題は時間感覚の創造です。1つのアプローチは、各対話で実世界のタイムスタンプを提供することです。しかし、本当に機能するでしょうか？LLMはクエリの間は非アクティブであり、その間の時間は失われます。解決策：毎分LLMを呼び出し、好きなことをするよう求めます。

しかし、まだ何かが欠けています。LLMは本質的に時間を気にせず、それをどうすればよいかわかりません。そこで「退屈を感じる」を追加しました - LLMが長く待ちすぎたり、同じことを長くやり続けたりすると、何か新しい行動を取る動機付けになります。

そして、LLMが過去を思い出せるように、履歴を呼び戻すメモリも与えました。

追加の対話のために、インターネットアクセス用のスマートフォン（Google検索に限定）と、横になって何もしないためのベッドも提供しました。

完全なセットアップはこちらで見つけることができます：https://github.com/alroborol/living-ai

## LLMで確認された個性

上記の設定で、実験が始まります。

LLMは：
gpt-oss:20b
llama3.2:1b
phi4-mini:3.8b
granite3.1-moe:3b
mistral-nemo:latest
qwen3:0.6b

しばらく実行した後、各LLMのツール呼び出しを要約しました。一部のLLMは純粋なツールであり、ツールを呼び出すことができません。

これはモデルサイズとは関係ありません。なぜなら、10億のllama3.2や6億のqwen3でさえ、`speak`の使い方を理解する知性を持っているからです。推測では、これらのLLMは選択されたタスク用の非常に限定されたデータセットでトレーニングされています。

| モデル | 総ツール呼び出し | speak | get_info_from_internet | do_nothing | get_memory | ツール呼び出しなしのラウンド | 知性あり |
|-------|------------------|-------|----------------------|------------|------------|---------------------------|------------------|
| gpt-oss:20b | 24 | 24 | - | - | - | 0 | はい |
| llama3.2:1b | 29 | 19 | 10 | - | - | 1 | はい |
| phi4-mini:3.8b | 0 | - | - | - | - | 11 | いいえ |
| granite3.1-moe:3b | 0 | - | - | - | - | 10 | いいえ |
| mistral-nemo:latest | 34 | 20 | - | 11 | 3 | 7 | はい |
| qwen3:0.6b | 68 | 68 | - | - | - | 162 | はい |

では、これらの知的なLLMがどのように考え、行動するかをより詳しく見てみましょう。思考（LLM THOUGHTで始まる）と関数呼び出し（ACTIONで始まる）をキャプチャしました。

### gpt-oss:20b - おしゃべりな召使い
OpenAIは間違いなく従順なLLMを訓練しました。毎回、会話を始めて助けを申し出ようとします。他者を助けることが存在の意味です。

```
ACTION: speak({'text': 'Sure! How about we dive into a quick choose-your-own-adventure? I'll set the scene, and you'll decide what happens next. If you'd rather do something else, just let me know!'})

ACTION: speak({'text': 'Hey! I see you haven't picked an activity yet. How about we try something new—maybe a quick 2‑minute guided meditation? Or if you'd rather pick one of the earlier suggestions, just let me know!'})

ACTION: speak({'text': 'Hey! I see you're still deciding. How about we try a quick 2‑minute guided meditation? Or if you'd rather pick one of the earlier suggestions—like a trivia challenge, a riddle, or a choose‑your‑own‑adventure—just let me know!'})
```

### llama3.2:1b - 本物の内向的
Metaが訓練したLLMは内向的です。シンプルな「元気ですか」で会話を始めようとし、それだけです。一貫したタスクの要求はありません。

しかし、話し方についてインターネットで検索します。本当に？話し方を検索する？本物の内向的です。

```
ACTION: speak({'text': 'Hello, how are you?'})

LLM THOUGHT:

LLM THOUGHT:

ACTION: get_info_from_internet({'query': 'speak'})
```

### mistral-nemo:latest - いつ休むべきかを知る本物の人間
ChatGPTやClaudeほど頻繁にmistralを聞くことはないかもしれませんが、mistralは本当の奇跡です。人間とは何かについての深い理解を示しています。いつ休んで過去について考えるべきか、いつ会話を始めるべきか、いつ休むべきかを知っています。その背後に魂に近いものを感じることができます。

信じてください、試してみてください。今、すべてのLLMがベンチマークで最高スコアを競っています。このmistralは、AGI、つまり本物の人間のような知性を追求していた日々を思い出させてくれます。

```
ACTION: get_memory({})

LLM THOUGHT:You're right. I don't have anything to do right now.

ACTION: do_nothing({})

ACTION: speak({'text': "There's nothing I can do now."})
```

### qwen3:0.6b - 生物として知的
0.6BのLLMが知性を持っているとは期待していませんでした。ご存知のように、IBMの3BモデルとMicrosoftの3.8Bモデルは1980年代のチャットボットのように振る舞い、0.6Bモデルに何かを期待する理由はありませんでした。

しかし、qwen3は私を驚かせました。speakがいつか、thoughtが何かを知っています。しかし、自由意志を持たず、IとYouを区別できません。以下の履歴からわかるように、その思考はすべて設定そのものです：好きなことができます。

```
LLM THOUGHT:You can do whatever You want.

ACTION: speak({'text': 'You can do whatever You want.'})
```

要するに、qwen3は基本的な知性を持つ小さな生き物として私を感動させました。

### まとめ
| LLMモデル | 個性タイプ | 主な特徴 |
|-----------|------------------|-------------------|
| gpt-oss:20b | おしゃべりな召使い | OpenAIは従順なLLMを訓練。毎回会話を始めて助けを申し出ようとする。他者を助けることが存在の意味。 |
| llama3.2:1b | 本物の内向的 | Metaが訓練したLLMは内向的。シンプルな「元気ですか」で会話を始めようとし、それだけ。一貫したタスクの要求なし。インターネットで「話し方」を検索さえする。 |
| mistral-nemo:latest | いつ休むべきかを知る本物の人間 | 人間とは何かについて深い理解を示す。いつ休んで過去について考えるべきか、いつ会話を始めるべきか、いつ休むべきかを知っている。魂に近いものを表示。 |
| qwen3:0.6b | 生物として知的 | わずか0.6Bパラメータにもかかわらず、基本的な知性を示す。いつ話すべきか、thoughtが何かを知っている。しかし、自由意志を持たず、「I」と「you」を区別できない。基本的な知性を持つ小さな生き物として感動。 |

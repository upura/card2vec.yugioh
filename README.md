card2vec.yugioh
===
Repository for card2vec edited for Yugioh and Windows (Original: https://github.com/GuiltyMorishita/card2vec)

# Description

Card2vec means similarity calclation approach using card texts information using technique of word2vec or doc2vec. More detailed infomation can be seen in the following link.

http://upura.hatenablog.com/entry/2018/01/21/184700

# Demo

In this demo, "[ソーラー・エクスチェンジ](http://yugioh-wiki.net/index.php?%A1%D4%A5%BD%A1%BC%A5%E9%A1%BC%A1%A6%A5%A8%A5%AF%A5%B9%A5%C1%A5%A7%A5%F3%A5%B8%A1%D5)" is a target card name.

```
# Card name you would like to know similar card
TARGET_CARD_NAME = names[random.randint(0, len(names))]

# You can specify the card name
# TARGET_CARD_NAME = "ソーラー・エクスチェンジ"

card_index = names.index(TARGET_CARD_NAME)

# Receive a list of tuples of (similar cards and similarity), limited to ones of top 10 similarities
similar_docs = model.docvecs.most_similar(card_index)
print(names[card_index])
print(texts[card_index])
print("--------------------is similar to--------------------\n")
for similar_doc in similar_docs:
    print(names[similar_doc[0]] + " " + str(similar_doc[1]))
    print(texts[similar_doc[0]], "\n")
```

## Output

```
ソーラー・エクスチェンジ
手札から「ライトロード」と名のついたモンスターカード１枚を捨てて発動する。自分のデッキからカードを２枚ドローし、その後デッキの上からカードを２枚墓地に送る。
--------------------is similar to--------------------

閃光のイリュージョン 0.7759238481521606
自分の墓地から「ライトロード」と名のついたモンスター１体を選択し、攻撃表示で特殊召喚する。自分のエンドフェイズ毎に、デッキの上からカードを２枚墓地に送る。このカードがフィールド上から離れた時、そのモンスターを破壊する。そのモンスターがフィールド上から離れた時このカードを破壊する。 

ライトロード・ドルイド オルクス 0.7378130555152893
このカードがフィールド上に表側表示で存在する限り、「ライトロード」と名のついたモンスターを魔法・罠・効果モンスターの効果の対象にする事はできない。このカードが自分フィールド上に表側表示で存在する限り、自分のエンドフェイズ毎に、自分のデッキの上からカードを２枚墓地に送る。 

ライトロード・スピリット シャイア 0.7361984252929688
このカードの攻撃力は、自分の墓地に存在する「ライトロード」と名のついたモンスターの種類×３００ポイントアップする。このカードが自分フィールド上に表側表示で存在する限り、自分のエンドフェイズ毎に、自分のデッキの上からカードを２枚墓地へ送る。 

ライトロード・ドラゴン グラゴニス 0.7135570049285889
このカードの攻撃力と守備力は、自分の墓地に存在する「ライトロード」と名のついたモンスターカードの種類×３００ポイントアップする。このカードが守備表示モンスターを攻撃した時、その守備力を攻撃力が超えていれば、その数値だけ相手ライフに戦闘ダメージを与える。このカードが自分フィールド上に表側表示で存在する場合、自分のエンドフェイズ毎に、デッキの上からカードを３枚墓地に送る。 

ライト・バニッシュ 0.7092658877372742
自分フィールド上に存在する「ライトロード」と名のついたモンスター１体をリリースして発動する。モンスターの召喚・反転召喚・特殊召喚を無効にし破壊する。 

ライトロード・エンジェル ケルビム 0.703083872795105
このカードが「ライトロード」と名のついたモンスターを生け贄にして生け贄召喚に成功した時、デッキの上からカードを４枚墓地に送る事で相手フィールド上のカードを２枚まで破壊する。 

光の援軍 0.6913601756095886
自分のデッキの上からカードを３枚墓地へ送って発動する。自分のデッキからレベル４以下の「ライトロード」と名のついたモンスター１体を手札に加える。 

マイン・ゴーレム 0.6905478835105896
このカードが戦闘によって墓地に送られた時、相手ライフに５００ポイントダメージを与える。 

ライトロード・レイピア 0.6747479438781738
「ライトロード」と名のついたモンスターにのみ装備可能。装備モンスターの攻撃力は７００ポイントアップする。このカードがデッキから墓地に送られた時、このカードを自分フィールド上に存在する「ライトロード」と名のついたモンスター１体に装備する事ができる。 

魔法再生 0.6690211296081543
手札の魔法カードを２枚墓地に送る。自分の墓地から魔法カードを１枚選択し、手札に加える。 
```

# Environment

- Windows OS
- Python 3.x

# Contributions

There are mainly 2 contributions from the original.

1. Change settings for Yugioh and examine the quality (See the link above)
1. Escape unicode error for windows OS

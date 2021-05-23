---
theme: default
background:
class: text-center
highlighter: shiki
---

# スクラム開発入門

~目指せ、脱聞いたことあるだけ状態~

shoji hajime

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# まずは自己紹介

<br>

- 1994年4月10日生まれの27歳
- 宮城県仙台市出身
- 趣味は自転車・染髪・他の人のgoogleカレンダーを眺めること
- Twitterは `@hajimasa7` でやっているのでフォローお願いします
- 好きなマルフォイは賢者の石


<img style="text-aline:center;" src="http://drive.google.com/uc?export=view&id=1SOJSC7cpSzqV7M6abd-UeizGoIJFr1Ap" width="200"><p>↑このピンときたらです</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# このスライドはslidevを使用して作成しています

<div class="w-60 relative mt-6">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-square.png"
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-circle.png"
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-triangle.png"
    />
  </div>

  <div 
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<!-- vue script setup scripts can be directly used in markdown, and will only affects current page -->
<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発ってなんだよ
<img src="http://drive.google.com/uc?export=view&id=1OmEPYmLMy6OFzufOe4jXcmRPWsn6f_LL" width="400">

<br>
<br>

## スクラム？ラグビーのこと？

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発とはアジャイルソフトウェア開発手法の1つです。

<br>

## まずアジャイル開発の特徴

<br>

<p>📝  日々の目的の達成のために協力する</p>
<p>🎨  フィードバックを継続的に得ながら計画を調整していく</p>
<p>🧑‍  まとめてやるのではなくて、細かく進め、作っているものが合っているか都度確認する</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# なぜアジャイルで開発するの？

<br>
<br>
<br>

## A. ソフトウェア開発が難しいからと言われているから

<p>最初に計画を立てて進めていても、いつの間にか違う機能がほしいと言われたり、ここを変更してほしいと必ず言われます</p>
<p>その変更を完全に予想するのはとてもむずかしいことです。なので、都度検査と調整を行わなければなりません</p>
<p>事前に起きることすべてを予測するのは不可能、という前提を意識して進めるのがアジャイルの特徴です</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発って？

<br>
<br>
<br>

## 以下のような特徴があります

<p>・必要な機能やモノを並び替えて、その順番に作っていく。そのリストのことをプロダクトバックログと呼びます</p>
<p>・短い期間に区切って進めていく。その期間をイテレーション(スプリント)と呼びます</p>
<p>・現状や問題点をオープンにする</p>
<p>・定期的に進め方を検査する</p>
<p>・問題があれば、やり方を変えて適応させる</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発ってどんなときに効果的なの？

<br>
<br>
<br>

## 無秩序かつ持続性のあるものを扱うときはスクラムを導入すると効果的

<p>手順を作ったほうがいい定期的な作業や、一つのことに深く踏み入れる必要がもの、スクラムをやっている暇がない短納期なもの、割り込みが多い場合はスクラムは効果的にでない場合が多いと思います</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発における役割

<br>
<br>
<br>

## いろんな役割の人が存在してます

<p>👮 ステークホルダー: 決裁者、ビジネス全体の優先順位を管理する係</p>
<p>👨 プロダクトオーナー: ステークホルダーの要望を加味して、プロダクトの価値を最大化する係</p>
<p>👩 スクラムマスター: スクラムがうまくまわるように何でもやる係</p>
<p>👶 メンバー: 一生懸麺ストーリーを消化する係</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# スクラム開発って具体的にどうするの

<br>
<br>
<br>

## いろんなイベントで構成される

<p>🙊 1.スプリントプランニング</p>
<p>👕 2.デイリースクラム</p>
<p>💻 3.開発作業</p>
<p>📔 4.スプリントレビュー</p>
<p>🌀 5.スプリントレトロスペクティブ</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# 1.スプリントプランニング

<br>
<br>
<br>

<p>スプリントプランニングは、スプリント(一定期間)に、どれだけのストーリー(機能)をリリースできるかを計画するイベント</p>
<p>スプリント中にメンバーがどれだけストーリーを消化できるかは、ストーリーポイントという指標を用いる</p>
<p>ストーリーポイントの見積もりはリファインメントと呼び、ストーリーポイントはプランニングポーカー等の決め方があります</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# 2.デイリースクラム

<br>
<br>
<br>

<p>デイリースクラムは前回のデイリースクラムからやったこと、次回のデイリースクラムまでやることの確認</p>
<p>連絡事項があるかを確認したり、スプリント内にストーリーが終わらないそうな人がいれば、アサインを相談したりします</p>
<p>いわゆる朝会ですね</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# 3.開発作業

<br>
<br>
<br>

<p>スプリント内に終わるようにストーリーを進めていく</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# 4.スプリントレビュー

<br>
<br>
<br>

<p>スプリント中に完成したものに関して、ステークホルダーにレビューをもらう時間になります</p>
<p>デモや共有を行って、フィードバックをもらいます</p>
<p>状況の変化や全体の共有を行う</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# 5.スプリントレトロスペクティブ

<br>
<br>
<br>

<p>スプリント中に起こったことに対するレトロスペクティブ(ふりかえり)を行います</p>
<p>一般的にKPTなどのふりかえりフレームワークを用いてふりかえることが多いと思います</p>
<p></p>
<p></p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

<img src="http://drive.google.com/uc?export=view&id=1OvtCKI9PzWmdhTsMOjgKJWCFzcCcISaF" width="850">

---

# スクラム開発のメリット

<br>
<br>
<br>

## リリースを素早くできる

<p>リリースを素早くできるので、機能の価値を最大化することができます</p>
<p>まとめてリリースするより、機能を使うことができる期間が伸びるので価値が最大化するということです</p>

## 属人性を排除できる

スクラム開発では基本イベントは全員で行うので、後述するプランニング(工数決め)をみんなで行うことでそのプロダクトに対しての知識の差が出ないように進められます。

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>
 
---

# スクラム開発のデメリット

<br>
<br>
<br>

## MTGの時間が多くかかる

<p>スクラム開発には先ほど紹介したように、いろいろなイベントが発生します</p>
<p>なので、イベント自体に時間を取られるので、メンバーの開発する時間は少なくなってしまいます</p>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

# まとめると

<br>
<br>
<br>

## GIGも準委任増えてきているし、スクラム開発取り入れたら幸せになるのでは！

と思っています。

## 興味ある方いたら、一緒にスクラム開発布教活動しましょう！


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(90deg, #008800 10%, #004400 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
  font-weight: 600;
}
</style>

---

## FAQ
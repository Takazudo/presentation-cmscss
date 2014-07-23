# CMSのやつのCSS

[@Takazudo](https://twitter.com/Takazudo)

----

## CMS案件

* 無限にテーマが増える
* どうしたらいいかわからん
* 現状色々カオスで大変なのでどうにかしたい
* 作るコストを減らしたい

----

## CSS以前にどうするという話

* 同一HTMLやめた
* テーマごとにテンプレ作成
* 使うブロックだけをカスタムコンパイル

----

## やったこと

* とりあえずMindBEMding的な
* 文字サイズ種類の統一
* 上下行間余白殺し
* 余白無しblock
* 余白専用block
* 余白の単位
* モディファイアの利用
* グローバルモディファイア

----

## fontのmixin

```sass
+g-font(12, 1) // 12px line-height狭
+g-font(12, 2) // 12px line-height広
+g-font(14, 1) // 14px line-height狭
+g-font(14, 2) // 14px line-height広

// 上下余白殺した版
+g-font-spacingKilled(12, 1)
+g-font-spacingKilled(12, 2)
+g-font-spacingKilled(14, 1)
+g-font-spacingKilled(14, 2)
```

----

## 余白用ブロック

```
<div class="b-bPlacer">...</div>
```

30px下padding

----

## 余白統一

1s（スペーシング）=5px とする

```html
<div class="b-bPlacer-1s">...</div> // padding-bottom: 5px
<div class="b-bPlacer-2s">...</div> // padding-bottom: 10px
<div class="b-bPlacer-3s">...</div> // padding-bottom: 15px
<div class="b-bPlacer-4s">...</div> // padding-bottom: 20px
<div class="b-bPlacer-5s">...</div> // padding-bottom: 25px
<div class="b-bPlacer-6s">...</div> // padding-bottom: 30px
```

----

## モディファイア

```html
<div class="
  b-mediaBox
  b-mediaBox--imgR
  b-mediaBox--spacing-4s
">...</div>

// 画像右
// 間の余白20px

<div class="
  b-mediaBox
  b-mediaBox--imgL
  b-mediaBox--spacing-6s
">...</div>

// 画像左
// 間の余白30px
```

----

## グローバルモディファイア

```html
<p class="b-paragraph ex-align-r">...</p> // text-align: right
<p class="b-paragraph ex-align-c">...</p> // text-align: center
<p class="b-paragraph ex-align-l">...</p> // text-align: left

<p class="b-paragraph ex-spacingTweak-up-1s">...</p> // margin-top: -5px
<p class="b-paragraph ex-spacingTweak-up-2s">...</p> // margin-top: -10px
<p class="b-paragraph ex-spacingTweak-up-3s">...</p> // margin-top: -15px
<p class="b-paragraph ex-spacingTweak-up-4s">...</p> // margin-top: -20px

<p class="b-paragraph ex-spacingTweak-down-1s">...</p> // margin-top: 5px
<p class="b-paragraph ex-spacingTweak-down-2s">...</p> // margin-top: 10px
<p class="b-paragraph ex-spacingTweak-down-3s">...</p> // margin-top: 15px
<p class="b-paragraph ex-spacingTweak-down-4s">...</p> // margin-top: 20px
```

----

## おわり

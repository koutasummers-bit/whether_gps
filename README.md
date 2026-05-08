# whether_gps

現在地のリアルタイム天気を表示するシンプルな Web アプリ（単一 HTML / Vanilla JS）。

## 機能

- 📍 ブラウザの位置情報 API で現在地を取得（拒否時は東京駅にフォールバック）
- 🗺 現在地を地図（Leaflet + OpenStreetMap / CARTO Dark）でも表示
- 🛰 現在気温は **気象庁 AMeDAS の最寄り観測所（実測値・10 分更新）** を優先利用、海外や AMeDAS 取得失敗時は Open-Meteo の予測値にフォールバック
- ⛅ 現在の天気・体感・湿度・風速
- 📈 今日の最高 / 最低気温、降水確率、降水量、日の出 / 日の入
- 👕 今日の最高気温と天気から判定する**おすすめの服装**
- ☂ 降水確率と降水量から判定する**傘の要否**
- 🚶 近くの**散歩スポット提案**（公園・神社・寺院・展望地・史跡）。**時間は 15 分刻み（15〜90 分）で指定可能**、**往復 / 片道**も切り替え可能。地図にも番号付きピンで表示。読み込み時にまとめて取得・キャッシュするので、設定変更は即時反映
- ⏰ 24 時間の時間別予報（横スクロール）
- 📅 7 日間の週間予報

## 使い方

`index.html` をそのままブラウザで開くだけ。Geolocation API は **HTTPS（または `localhost`）** でないと動かないので、以下のいずれかで配信してください。

```sh
# Python が入っていればこれだけで OK
python3 -m http.server 8000
# → http://localhost:8000/ を開く
```

GitHub Pages を有効化すれば、HTTPS で簡単に公開できます。

## データ出典

- 現在気温（実測）: [気象庁 AMeDAS](https://www.jma.go.jp/bosai/amedas/)（無料・キー不要）
- 気象データ（予報・天気・降水確率など）: [Open-Meteo](https://open-meteo.com/)（API キー不要・無料）
- 地名（逆ジオコーディング）: [BigDataCloud](https://www.bigdatacloud.com/)（API キー不要・無料）
- 散歩スポット検索: [Overpass API](https://wiki.openstreetmap.org/wiki/Overpass_API)（OSM、無料・キー不要）
- 地図ライブラリ: [Leaflet](https://leafletjs.com/)（CDN 経由）
- 地図タイル: [OpenStreetMap](https://www.openstreetmap.org/) 標準タイル

## ファイル構成

- `index.html` — アプリ本体（CSS / JS を含む単一ファイル）

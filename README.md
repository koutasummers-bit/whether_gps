# whether_gps

現在地のリアルタイム天気を表示するシンプルな Web アプリ（単一 HTML / Vanilla JS）。

## 機能

- 📍 ブラウザの位置情報 API で現在地を取得（拒否時は東京駅にフォールバック）
- 🗺 現在地を地図（Leaflet + OpenStreetMap / CARTO Dark）でも表示
- ⛅ 現在の天気・気温・体感・湿度・風速
- 📈 今日の最高 / 最低気温、降水確率、降水量、日の出 / 日の入
- 👕 今日の最高気温と天気から判定する**おすすめの服装**
- ☂ 降水確率と降水量から判定する**傘の要否**
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

- 気象データ: [Open-Meteo](https://open-meteo.com/)（API キー不要・無料）
- 地名（逆ジオコーディング）: [BigDataCloud](https://www.bigdatacloud.com/)（API キー不要・無料）
- 地図ライブラリ: [Leaflet](https://leafletjs.com/)（CDN 経由）
- 地図タイル: [CARTO Dark Matter](https://carto.com/basemaps/) ＋ [OpenStreetMap](https://www.openstreetmap.org/)

## ファイル構成

- `index.html` — アプリ本体（CSS / JS を含む単一ファイル）

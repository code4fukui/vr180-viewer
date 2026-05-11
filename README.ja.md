# vr180-viewer

[A-Frame](https://aframe.io/) を使用したVR180写真用のウェブベースビューアーです。

VR180写真をVR表示します。

## デモ

- **[松江と福井で協議会 - 全国ご当地こどもロボコン連盟](https://code4fukui.github.io/vr180-viewer/kanirobo.html)**
  (作例: 松江と福井で協議会 - 全国ご当地こどもロボコン連盟)

## 特徴

- 立体視可能なVR180画像ペア（左目用と右目用）をレンダリングし、没入感のある体験を提供します。
- A-Frameをベースに構築されており、ウェブブラウザやVRヘッドセットとの幅広い互換性があります。
- サーバーサイドの依存関係がなく、シンプルで自己完結型のHTMLセットアップが可能です。
- マウス、タッチ操作、またはVRコントローラーの向きによってインタラクティブに視点を操作できます。

## 使い方

ご自身のVR180写真を表示するには、HTMLファイルを作成し、以下のコードを追加してください。このセットアップには [A-Frame](https://aframe.io/) と [aframe-stereo-component](https://github.com/code4fukui/aframe-stereo-component) が必要です。

1.  **画像の準備:** 左目用と右目用の2つの独立した画像ファイルが必要です。

2.  **`index.html` ファイルの作成:** 以下のコードをコピーし、`src` のパスをご自身の画像ファイルに置き換えてください。

    ```html
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf-8">
      <title>VR180 Viewer</title>
      <script src="https://code4fukui.github.io/aframe/dist/aframe-master.min.js"></script>
      <script src="https://code4fukui.github.io/aframe-stereo-component/dist/aframe-stereo-component.min.js"></script>
    </head>
    <body>
      <a-scene>
        <a-assets>
          <!-- 左目用と右目用の画像パスを定義 -->
          <img id="left" src="./path/to/your-left-image.jpg">
          <img id="right" src="./path/to/your-right-image.jpg">
        </a-assets>

        <!-- VRコントロール付きカメラ -->
        <a-entity camera look-controls position="0 0 0" stereocam="eye:left;"></a-entity>

        <!-- 各目用のスカイスフィア -->
        <a-sky id="sky1" src="#left" stereo="eye:left"></a-sky>
        <a-sky id="sky2" src="#right" stereo="eye:right"></a-sky>
      </a-scene>
    </body>
    </html>
    ```

3.  **ブラウザで表示:** HTMLファイルを開きます。立体的な3D効果を見るには、VRヘッドセットを使用し「Enter VR」ボタンをクリックしてください。

動作するサンプルについては、[`kanirobo.html`](kanirobo.html) を参照してください。

## ライセンス

詳細は [LICENSE](LICENSE) ファイルを参照してください。

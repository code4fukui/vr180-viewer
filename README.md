# vr180-viewer

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A web-based viewer for VR180 photos using [A-Frame](https://aframe.io/).

VR180写真をVR表示します (Displays VR180 photos in VR)

## Demo

- **[Conference in Matsue and Fukui - National Local Children's Robot Contest Federation](https://code4fukui.github.io/vr180-viewer/kanirobo.html)**
  (作例: 松江と福井で協議会 - 全国ご当地こどもロボコン連盟)

## Features

- Renders stereoscopic VR180 image pairs (left and right eye) for an immersive experience.
- Built on A-Frame for broad compatibility with web browsers and VR headsets.
- Simple, self-contained HTML setup with no server-side dependencies.
- Interactive view controlled by mouse, touch, or VR controller orientation.

## Usage

To display your own VR180 photos, create an HTML file and add the following code. This setup requires [A-Frame](https://aframe.io/) and the [aframe-stereo-component](https://github.com/code4fukui/aframe-stereo-component).

1.  **Prepare your images:** You need two separate image files, one for the left eye and one for the right.

2.  **Create an `index.html` file:** Copy the code below and replace the `src` paths with your image files.

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
          <!-- Define paths to your left and right images -->
          <img id="left" src="./path/to/your-left-image.jpg">
          <img id="right" src="./path/to/your-right-image.jpg">
        </a-assets>

        <!-- Camera with VR controls -->
        <a-entity camera look-controls position="0 0 0" stereocam="eye:left;"></a-entity>

        <!-- Sky spheres for each eye -->
        <a-sky id="sky1" src="#left" stereo="eye:left"></a-sky>
        <a-sky id="sky2" src="#right" stereo="eye:right"></a-sky>
      </a-scene>
    </body>
    </html>
    ```

3.  **View in a browser:** Open the HTML file. To see the stereoscopic 3D effect, use a VR headset and click the "Enter VR" button.

For a working example, see [`kanirobo.html`](kanirobo.html).

## License

See the [LICENSE](LICENSE) file for details.
# HTML-Webcam
Streaming the Webcamera to HTML Page.

## Code Implementation
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebCam</title>
    <script type="text/javascript" src="https://unpkg.com/webcam-easy/dist/webcam-easy.min.js"></script>
<style>
    a{
        padding: 5px;
        background-color: rgb(117, 23, 23);
        color: rgb(255, 255, 255);
        text-decoration: none;
    }
    canvas{
        display: none;
    }
</style>
</head>
<body>
    <!-- <video id="webCam" width="1000" height="600"></video> -->
    <video id="webCam" autoplay playsinline width="1000" height="600"></video>
    <canvas id="canvas"></canvas>
    <a download onClick="takePicture()">SNAP</a>
    
    <script>
        const webCamElement = document.getElementById("webCam");
        const canvasElement = document.getElementById("canvas");
        const webcam = new Webcam(webCamElement, "user", canvasElement);
        webcam.start();

        function takePicture(){
            let picture = webcam.snap();
            document.querySelector("a").href = picture;
        }
    </script>
</body>
</html>
```

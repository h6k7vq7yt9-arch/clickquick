<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Open Selfie Camera</title>
  <style>
    body {
      margin: 0;
      font-family: sans-serif;
      text-align: center;
      background: #111;
      color: #fff;
    }
    video {
      width: 100%;
      max-width: 420px;
      margin-top: 1rem;
      border-radius: 8px;
      background: #000;
    }
    #tap {
      margin-top: 40vh;
      font-size: 1.5rem;
      color: #ccc;
    }
  </style>
</head>
<body>
  <div id="tap">👆 Tap anywhere to open your selfie camera</div>
  <video id="v" autoplay playsinline></video>

  <script>
    const video = document.getElementById('v');
    const tap = document.getElementById('tap');
    let opened = false;

    async function openSelfieCam() {
      if (opened) return;
      opened = true;
      tap.textContent = "Requesting camera...";
      try {
        const stream = await navigator.mediaDevices.getUserMedia({
          video: { facingMode: "user" },
          audio: false
        });
        video.srcObject = stream;
        tap.remove();
      } catch (err) {
        tap.textContent = "Camera access failed: " + err.message;
      }
    }

    document.body.addEventListener('click', openSelfieCam, { once: true });
  </script>
</body>
</html>

# <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>SAFA 💌</title>
  <style>
    body {
      background-color: #98AFC7;
      font-family: Arial, sans-serif;
      text-align: center;
      padding-top: 100px;
    }
    #envelope {
      font-size: 80px;
      cursor: pointer;
      transition: transform 0.3s;
    }
    #envelope:hover {
      transform: scale(1.2);
    }
    #message {
      font-size: 24px;
      margin-bottom: 20px;
      color: #333;
    }
    video {
      margin-top: 20px;
      width: 300px;
      height: auto;
      display: none;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <div id="message">Welcome to SAFA's world 💖<br>Click the envelope!</div>
  <div id="envelope">💌</div>
  <video id="video" autoplay playsinline></video>

  <script>
    document.getElementById("envelope").onclick = async function () {
      const video = document.getElementById("video");
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } });
        video.srcObject = stream;
        video.style.display = "block";
      } catch (err) {
        alert("We couldn't open your camera: " + err);
      }
    };
  </script>
</body>
</html>

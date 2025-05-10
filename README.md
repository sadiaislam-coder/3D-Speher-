<!DOCTYPE html>
<html>
<head>
  <title>3D Sphere</title>
  <style>
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #000;
    }
    .sphere {
      width: 200px;
      height: 200px;
      position: relative;
      transform-style: preserve-3d;
      animation: spin 10s infinite linear;
    }
    .ring {
      position: absolute;
      width: 100%;
      height: 100%;
      border: 2px solid rgba(0, 255, 255, 0.7);
      border-radius: 50%;
      transform-style: preserve-3d;
    }
    @keyframes spin {
      0% { transform: rotateX(0) rotateY(0); }
      100% { transform: rotateX(360deg) rotateY(360deg); }
    }
  </style>
</head>
<body>
  <div class="sphere" id="sphere"></div>
  <script>
    const sphere = document.getElementById('sphere');
    for (let i = 0; i < 10; i++) {
      const ring = document.createElement('div');
      ring.className = 'ring';
      ring.style.transform = `rotateY(${i * 18}deg) rotateX(45deg)`;
      sphere.appendChild(ring);
    }
  </script>
</body>
</html>

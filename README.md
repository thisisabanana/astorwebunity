# [astorwebunity](https://thisisabanana.github.io/astorwebunity/)

### build times
Linking build.js (wasm) at the end takes the most time, up until then it takes < 5 min

Build Settings (Runtime Speed LTO) + Player Settings (Faster runtime) = 20 min <br>
Build Settings (Runtime Speed) + Player Settings (Faster runtime) = 10 min <br>
Build Settings (Runtime Speed) + Player Settings (Faster, smaller builds) = 6 min

<br>

### What to check if emission material doesn't work in Unity URP
check if **"HDR"** on Assets > Settings > URP-Renderer.asset is **ENABLED!!**

<br>

### Dithering and WebGL?
- [how to add Full-screen Bayer dithering (reddit)](https://www.reddit.com/r/Unity3D/comments/1iokwqx/comment/mcomrq7/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)
- [how to actually use the Bayer4x4 dithering (github)](https://gist.github.com/brihernandez/8f7dcdef528babfc4995bb6713e7d6bb)

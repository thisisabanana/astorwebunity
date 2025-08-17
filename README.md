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

<br>

### [How to fix Camera.Render() not rendering post processing?](https://epheria.github.io/posts/RenderTexture02/)
Change the `RenderTextureFormat.ARGB32` in `RenderTexture.GetTemporary` to `RenderTextureFormat.ARGBHalf`,<br>
and `TextureFormat.RGB24` in `new Texture2D` to `TextureFormat.RGBAHalf`!

- ARGB32 stores each channel as an 8-bit integer, with values ranging from 0 to 255. This makes it suitable for storing LDR (Low Dynamic Range) images.
- Therefore, post-processing effects (bloom, tone mapping, etc.) often require a high dynamic range and precision, and the ARGB32 format cannot store this high range, which is why post-processing effects were not properly applied to RenderTexture.
- For ARGBHalf and RGBAHalf, each channel is stored as a 16-bit floating point, allowing for a much wider range of values than ARGB32. This means it supports HDR processing, which is typically required by post-processing effects.

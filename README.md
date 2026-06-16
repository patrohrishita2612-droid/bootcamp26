github introductio lecture 
hello world again 
matrix 4 was a bad movie


---

i am a hacker

---

new changes

ell 7 — proxy training: Unpacks 6-tuple from loader. Sigma is ignored for proxy training — the proxy just learns orig→decoded regardless of whether orig was noisy. The proxy gate (L1 < 0.015, PSNR > 33) is unchanged.
Cell 10 — Kelvin training: Unpacks 6-tuple. The orig tensor already contains baked-in noise from pair generation — no additional noise step needed in the training loop. SigLIP embedding comes from the clean-image cache, which is valid because σ=4 pixel noise doesn't change semantic content at 384px embedding resolution.
Cells 11 and 12 (eval and report): Completely unchanged. kelvin_enhance_yuv420_bytes runs on clean images, no noise, real x264, PCHIP BD-rate. If the noise augmentation transfers well, you'll see negative BD-rate for the Kelvin leg. If it doesn't transfer (BD-rate near zero), bump noise_clean_fraction from 0.30 to 0.50 and retrain.

Oct 2: Set up VS Code, Python and Git. Cloned the LiDeRe code. Created my GitHub repo.
Next: run the demo on a Kaggle GPU.
Oct 2: Kaggle notebook with 2x Tesla T4 works. Ran LiDeRe inference demo (contour prediction). Long missing_keys message is expected because the 5 MB file holds only the readout.
Next: train on 4 images, then reproduce one paper experiment.
Oct 2: Training demo failed with an OSError while loading an example image (the one-line wget download was unreliable). Fixed by downloading each file separately and checking it opens.
## Oct 2
- Set up VS Code, Python and Git. Created my GitHub repo.
- Set up a Kaggle notebook with 2x Tesla T4 GPU.
- Ran the LiDeRe inference demo (contour prediction). Result saved in results/contour.png.
- Problem: training demo failed with "image file is truncated". The one-line download of the example images was unreliable.
- Fix: downloaded each file separately and checked that it opens. All 8 files are fine now.
- Next: train on the 4 example images, then reproduce one experiment from the paper.
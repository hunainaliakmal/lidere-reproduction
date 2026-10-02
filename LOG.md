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
- Training failed again with "image file is truncated" inside the DataLoader worker. Cause: images were opened lazily and shared between worker processes. Fix: load images fully into memory and use num_workers=0.                                                         
- Kaggle session restarted and lost the model. Fixed by rebuilding everything in one cell: clone code, download the example images, train for 300 iterations, predict the cow image.
- Prediction on the cow image looks correct after resizing the low-resolution mask to 512x512. This image was in the training set, so it only shows the training works.
## Oct 2 (night)
- "Dataset not found" message: the zip was downloaded but not unzipped into DATA_ROOT/leaf_disease_segmentation. Fixed by extracting it.
- Read the repo source to match the paper setup. Deviations: ViT-B backbone, 512 px, 500 steps, batch 16, weight decay 0.
- Ran the Leaf cell on the laptop by mistake: "Torch not compiled with CUDA enabled" (no GPU). Training must run in Kaggle. Data loading worked locally: 399 train and 90 test images.
## Oct 3
- Leaf experiment finished on Kaggle (T4, about 8 minutes). Settings: ViT-B backbone, 512 px, 500 steps, batch size 16, learning rate 0.001.
- Test results on 90 images: mIoU 0.816, disease IoU 0.692, background IoU 0.940, pixel accuracy 0.947.
- Still to do: compare with the paper table and run the remote sensing experiment.
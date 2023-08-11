# LinkedIn Article Working Files

## Image Files

Final testing consisted of selecting nine (9) files that were provided by the Professor Ortiz.  The files selected were grouped by size. 

|Size Indicator|Size|Significance|
|------|----|-----|
||1920x1080|Size suggested by LinkedIn for Articles|
|S1|752x423|Resulting size after uploading to LinkedIn|
|S2|640x360|Size smaller than resulting size of 752x432|

Out of the 10 qualities provided byt the professor, four qualities were chosen by our team for testing.

|Quality Indicator|Quality|
|------|-----|
|q20|Quality 20|
|q50|Quality 20|
|q90|Quality 90|
|q100|Quality 100|
|------|-----|

Each file was uploaded to a single article and then downloaded.  Those files uploaded once were renamed to include the string "posted".  The files that were posted once were posted once again and downloaded.  The files uploaded twice were renamed to include the string "posted_twice".  All files were resized by a LinkedIn process to 752x423.

|File|Original Size| File Name After First Upload | File Name After Second Upload | File Size After First _and_ Second Upload |
|-----|----------|--------------|--------|------------|
|__Img_01_q20.jpg|1920x1080|__Img_01_q20_posted.jpg|__Img_01_q20_posted_twice.jpg|752x423|
|__Img_01_q50.jpg|1920x1080|__Img_01_q50_posted.jpg|__Img_01_q50_posted_twice.jpg|752x423|
|__Img_01_q90.jpg|1920x1080|__Img_01_q90_posted.jpg|__Img_01_q90_posted_twice.jpg|752x423|
|__Img_01_q100.jpg|1920x1080|__Img_01_q100_posted.jpg|__Img_01_q100_posted_twice.jpg|752x423|
|__Img_01_S1_q20.jpg|752x423|__Img_01_S1_q20_posted.jpg|__Img_01_S1_q20_posted_twice.jpg|752x423|
|__Img_01_S1_q50.jpg|752x423|__Img_01_S1_q50_posted.jpg|__Img_01_S1_q50_posted_twice.jpg|752x423|
|__Img_01_S1_q90.jpg|752x423|__Img_01_S1_q90_posted.jpg|__Img_01_S1_q90_posted_twice.jpg|752x423|
|__Img_01_S1_q100.jpg|752x423|__Img_01_S1_q100_posted.jpg|__Img_01_S1_q100_posted_twice.jpg|752x423|
|__Img_01_S2_q20.jpg|640x360|__Img_01_S2_q20_posted.jpg|__Img_01_S2_q20_posted_twice.jpg|752x423|
|__Img_01_S2_q50.jpg|640x360|__Img_01_S2_q50_posted.jpg|__Img_01_S2_q50_posted_twice.jpg|752x423|
|__Img_01_S2_q90.jpg|640x360|__Img_01_S2_q90_posted.jpg|__Img_01_S2_q90_posted_twice.jpg|752x423|
|__Img_01_S2_q100.jpg|640x360|__Img_01_S2_q100_posted.jpg|__Img_01_S2_q100_posted_twice.jpg|752x423|

Each file was processed using StegO_v1.15B.exe using the following line:
```
StegO_v1.15B.exe -analyze -log -verb +all -i __Img_01_q20.jpg
```


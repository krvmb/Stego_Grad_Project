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

## Analysis
### Preparation of Analysis Data
Each file was analyzed with a program provided by Professor Ortiz named StegO_v1.15B.exe.  The following command line was used to process each file.
```
StegO_v1.15B.exe -analyze -log -verb +all -i <filename>
```
For example
```
StegO_v1.15B.exe -analyze -log -verb +all -i __Img_01_q20.jpg 
```
The resulting log files consist of the string "log_StegO" and the name of the image that was analysed, for example.
```
log_StegO__Img_01_q100.log
```
### Manual Analysis
The resulting log files were analysed manually and by the use of a few text comparison tools.   Some findings.

No matter what the original quantization files were of the original image, every file uploaded and downloaded from LinkedIn contained the same Luminance quantization table which is the quality 90 quantization table.
```
  3   2   2   3   5   8  10  12 
  2   2   3   4   5  12  12  11 
  3   3   3   5   8  11  14  11 
  3   3   4   6  10  17  16  12 
  4   4   7  11  14  22  21  15 
  5   7  11  13  16  21  23  18 
 10  13  16  17  21  24  24  20 
 14  18  19  20  22  20  21  20 
```

For every file uploaded and downloaded from LinkedIn exhibited the same quantization table for the chrominance components.
```
  3   4   5   9  20  20  20  20 
  4   4   5  13  20  20  20  20 
  5   5  11  20  20  20  20  20 
  9  13  20  20  20  20  20  20 
 20  20  20  20  20  20  20  20 
 20  20  20  20  20  20  20  20 
 20  20  20  20  20  20  20  20 
 20  20  20  20  20  20  20  20 
```
And we found evidence of sub-sampling on the chrominance components.  The number of blocks for the chrominance components were reduced as well.
```
 ##### Component Block Summary ##### 

 - Component:0    94 X Blocks,  53 Y Blocks ... Total Blocks:  4982
 - Component:1    47 X Blocks,  27 Y Blocks ... Total Blocks:  1269
 - Component:2    47 X Blocks,  27 Y Blocks ... Total Blocks:  1269
```
Comparing the resulting analysis files from the same image posted once and then twice are almost unchanged saved a few DCT components in a few blocks.  Each of these DCT components are changed by 1.

|Block|DCT Coordinates (R,C)|DCT Change|
|----|----|---|
|125|2,2|0 _> 1|x
|170|2,1|4 _> 3|x
|170|3,1|2 _> 3|x
|177|2,1|9 _> 10|x
|177|4,1|0 _> 1|x
|217|2,1| 1 -> 0|x
|229|1,2| 1 -> 0|x
|240|2,1| -1 -> 0|x
|251|1,3| 1 -> 0|x
|261|1,2| 0 -> 1|x
|310|2,2| 0 -> -1|x
|325|2,1| -8 -> -9|x
|326|5,1| -1 -> -2|x
|331|2,1| -1 -> 0|x
|347|2,1| -8 -> -7|x
|353|1,3| 2 -> 3|x
|362|1,3| 0 -> -1|x
|414|4,1| 0 -> -1|x
|429|3,1| 0 -> -1|x
|448|3,1| 0 -> -1|x
|508|2,1| 0 -> -1|

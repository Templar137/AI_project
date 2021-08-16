# SC2 Cinematic video super resolution using Deep Learning

Hello, everyone! I planned to remaster lotv opening trailer so as to make better video using deeplearning model. 
I used LRDTN, Light Residual Dense Transpse Network, which orginates from RDN, Residual Dense Network. 
I mainly used tensorflow, keras, and cv2 when progressing this project

# Data preprecessing
I used train and test data from lotv opening video, but I composed two dataset with no overlapping between them. 
I made many frames through cv2, and I used data augmentation only flip. 
and I also used cv2 when making image to video after predicting the images.

# Model
First of all, I progressed this project through only google Colab pro, so when I used original RDN model, I had to face OOM error. 
To solve this problem, I used even lighter model, which reduced number of block from 20 to 5. 
Second, I used Transpose layer as upscale layer, instead of subpixel layer. 
The reason why we didn't used subpixel layer is that the output image became a little bit strange picture.

Third, I used more local information by using Residual Dense Block Transpose layer. 
In the original RDN, the locak information is linked only to concat layer. 
but, I thought that using more local information can describe sharper images, so I also used transpose layer to each RDB. 
![image](https://user-images.githubusercontent.com/62205971/129499732-43aceffe-0a58-43dc-82f2-5c3bb9c524d1.png)
also, I used concat layer at upscale layer to bind all upscaled information.



# Video
Finally I made a better quality of video compared to bicubic video. 
Let's see how much LRDTN makes better than bicubic.
https://youtu.be/SSHPvX0l1c0







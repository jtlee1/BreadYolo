# BreadYolo

# Intro
Hi, I am Justin Lee. Here is a guide of how I use Yolo to train an object recognition bot.
First thing to know is you will need a decent GPU installed in your computer because using CPU to train your bot will be extreamly slow.
The GPU I use is GTX1050, so make sure to adjust some steps if you feel like the step is just for my GPU.

# Step1
Install NVIDA driver(for using GPU).
If you did have this installed, please skip.
First you will install NVIDA driver following this guide https://medium.com/@zihansyu/ubuntu-16-04-%E5%AE%89%E8%A3%9Dcuda-10-0-cudnn-7-3-8254cb642e70
This guide are mostly good other then it did not tell you to turn off Xservice first.
If you get an error to turn off your Xservice do "ctrl+alt+f1", login, then type in "sudo service lightdm stop".
When you are finish, do "sudo service lightdm start" or "sudo service lightdm restart" to reactivate.

# Step2
Install CUDA(for using GPU).
If you did have this installed, please skip.
Basically follow this https://ithelp.ithome.com.tw/articles/10191693?sc=iThelpR
I didn't pass the test it gave me (showing CUDA Device Query (Runtime API) version (CUDART static linking)cudaGetDeviceCount returned 35-> CUDA driver version is insufficient for CUDA runtime versionResult = FAIL) But it still work for me.

# Step3
Download darknet from https://pjreddie.com/darknet/
Remember to change GPU=0 to GPU=1 in the make file before you do "make".

# Step4
Train your bot
Follow https://chtseng.wordpress.com/2019/01/25/%e7%89%a9%e4%bb%b6%e5%81%b5%e6%b8%ac%e7%9a%84%e6%87%89%e7%94%a8-diy%e9%9b%bb%e8%85%a6%e8%a6%96%e8%a6%bapos%e7%b5%90%e5%b8%b3%e5%8f%b0/?fbclid=IwAR0ZJxCbceHBtvW7EEEeoqV7q_NdtdIKBOI8Fbl_SjVkV41DCgUXcKMDlbc
Make sure you follow all step closely because every detail matters.
I will provide a sample so you know where everything is located.
One thing to point out is the way it provid to train my bot doesn't work for me. I use the command
"./darknet detector train [obj.data] [yolov3-tiny.cfg] [weights]" instead (fill in the path of your own .data .cfg and weight file)
Another thing to point out is you can change your [weights] section to continue trian from your last trial.

# More info
Check out https://chtseng.wordpress.com/2018/09/01/%e5%bb%ba%e7%ab%8b%e8%87%aa%e5%b7%b1%e7%9a%84yolo%e8%be%a8%e8%ad%98%e6%a8%a1%e5%9e%8b-%e4%bb%a5%e6%9f%91%e6%a9%98%e8%be%a8%e8%ad%98%e7%82%ba%e4%be%8b/?fbclid=IwAR2xBxavCZe4sH1c_ZmRIud9Jl0Hotu7fXtjomabznsCZcFVnjuyE0nL1nQ
and https://chtseng.wordpress.com/2018/10/08/%e5%a6%82%e4%bd%95%e5%bf%ab%e9%80%9f%e5%ae%8c%e6%88%90yolo-v3%e8%a8%93%e7%b7%b4%e8%88%87%e9%a0%90%e6%b8%ac/?fbclid=IwAR2uDno8ychQH4e8xQ6S8fKOf-hmKc-BFEI24USSFq_7TM5WsEqKCIe6VGY
if you want to test out your module without using raspbarry pi.

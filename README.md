# 下载诺禾致源数据  

## 1.进入邮箱  
点击“点击进入”  
<img src="https://github.com/y741269430/Download-rawdata/blob/main/images/1.png" width="600" />

## 2.进入邮箱   
点击“获取链接”  
<img src="https://github.com/y741269430/Download-rawdata/blob/main/images/2.png" width="600" />

## 3.下载linklist.txt    
<img src="https://github.com/y741269430/Download-rawdata/blob/main/images/3.png" width="600" />

## 4.把linklist.txt放进服务器里    
创建文件夹，文件夹名字里不能有空格。比如创建：afile，然后把linklist.txt放到afile里面。  
<img src="https://github.com/y741269430/Download-rawdata/blob/main/images/4.png" width="600" />

## 5.打开服务器并下载rawdata  
按顺序输入：  

    conda activate rnaseq
    cd aflie
    nohup aria2c -c -i linklist.txt &
    mkdir bam rawcounts  

下载完毕后，写入filenames，一般来说，我是根据“_1.clean.fq.gz”这段字符命名的，比如：cfa3_1.clean.fq.gz，那么我就取cfa3作为该名字。  
另外，“_1.clean.fq.gz”和 “_2.clean.fq.gz”，这两个文件是双端测序，测的是同一个样本。  

    ls *1.clean* |cut -d "_" -f 1 > filenames

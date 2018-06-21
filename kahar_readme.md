## Process of running triplets-extraction

### set up conda environment

1. install anaconda
    ````
    wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.2.0-Linux-x86_64.sh
    chmod u+x Anaconda3-5.2.0-Linux-x86_64.sh
    ./Anaconda3-5.2.0-Linux-x86_64.sh
    ````
2. config conda in order to speed up downloading speed ,
   TUNA 提供了 Anaconda 仓库的镜像，运行以下命令:
    ````
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --set show_channel_urls yes
    ````


3. create virtual environment for the code
    ````
    conda create -n theano08kearas033py2.7 python=2.7
    conda info --envs
    ````

4. activate virtual environment, and install dependency, there is no need to install specific virsion of theano and keras
   
   ````
    source activate theano08kearas033py2.7
    conda install Theano
    conda install keras
    pip install nltk
    ````

5. need to install punkt corpus from NLTK. the following command means that, first enter python
then import nltk,and then by download() function to download punkt corpus, finlly quit by pressing q

````
   python
   import nltk
   nltk.download()
   d
   punkt
   q
````

6. need to rename the `Data` directory to the `data` in the code directory:

````
    cd triplets-extraction
    mv /disk3/NYT-20180613T131152Z-001.zip ./Data
    cd Data
    unzip NYT-20180613T131152Z-001.zip
    cp train.json ../demo/
    cd ..
    mv Data data
    python TaggingScheme.py
    
````

7. get w2v.pkl file from other people, copy it to  `data/demo/`
    
8. need to get right version of Keras, first uninstall current one, then install right one.
````
    source activate theano08kearas033py2.7
    pip uninstall Keras
    pip install Keras==0.3.3
````


 









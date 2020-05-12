# How to install CaboCha, Mecab and corresponding Python development instruments on Ubuntu 18.04 LTS
## 1. Preparations
1. Open terminal and execute:
```
sudo apt-get install build-essential
```
## 2. Mecab
2. Next, run this command:
```
sudo apt-get install mecab libmecab-dev mecab-ipadic mecab-ipadic-utf8 mecab-jumandic mecab-jumandic-utf8
```
## 3. Mecab Python wrapper
3. Then you need to install **mecab-python**:
```
pip3 install mecab-python3
```
## 4. CRF++
4. Download the latest **CRF++** archive from here:
https://drive.google.com/drive/folders/0B4y35FiV1wh7fngteFhHQUN2Y1B5eUJBNHZUemJYQV9VWlBUb3JlX0xBdWVZTWtSbVBneU0
5. Go to the directory where the downloaded archive is located and then execute thess commands one by one:
```
tar xzvf CRF++-0.58.tar.gz
cd CRF++-0.58
./configure
make
sudo make install
sudo ldconfig
```
## 5. CaboCha
6. In this step you are ready to compile and install CaboCha. Download the latest version here:
https://drive.google.com/drive/folders/0B4y35FiV1wh7cGRCUUJHVTNJRnM
7.  Go to the directory with the archive and execute:
```
tar xjvf cabocha-0.69.tar.bz2
cd cabocha-0.69
./configure --with-charset=utf8
make
sudo make install
```
## 6. CaboCha Python wrapper
8. When you are in the /cabocha-0.69/ directory run these commands:
```
cd python
sudo python3 setup.py install
```
### ERROR: Cabocha Python wrapper can't find libcabocha.so.5
If you encountered this kind of a problem, run these commands:
```
cd /usr/lib
sudo ln -s /usr/local/lib/libcabocha.so.5 libcabocha.so.5
```

This is it! You've successfully installed everything you need to use CaboCha and Mecab in your Python programming.

---
### References
* https://irukanobox.blogspot.com/2019/09/pythoncabocha.html?m=1
* https://www.trifields.jp/install-cabocha-in-ubuntu-1038
* https://qiita.com/kazasiki/items/99505a5005aebe2efb7a
* https://rpubs.com/auroratsai/440718

Conda Numpy
===

## 概要
Conda環境でNumpyがimportできない問題

## 説明
MKLがうまく読まれずにエラーになってる場合の対処法
```
INTEL MKL ERROR: このオペレーティング システムでは %1 は実行されません。 mkl_intel_thread.dll.
Intel MKL FATAL ERROR: Cannot load mkl_intel_thread.dll.
```
こんな方にやってみてほしい
- conda update numpy mklで最新版にしてみたけどダメだった人
- System32の中にあるmkl*.dllを削除してみたけどダメだった人
- 最新mklをIntelから落としてみたけどダメだった人
- MKLを2018.0.2に戻して対処した人

## 要求
- Windows
  - Windows10 2019 May Update以外のバージョンは試していません
- Python
  - Python 2.7の場合
    - 2.7.15 build 14 以上
  - Python 3.6の場合
    - 3.6.8 build 7 以上
  - Python 3.7の場合
    - 3.7.2 build 8 以上

## 使用方法
`[Anacondaの入っているフォルダ]\Anaconda3\Scripts\activate.bat` に以下の1行を追加

デフォルトは`C:\Users\[ユーザー名]\Anaconda3\Scripts\activate.bat`

`@set CONDA_DLL_SEARCH_MODIFICATION_ENABLE=1`
## 参考文献
https://conda.io/projects/conda/en/latest/user-guide/troubleshooting.html

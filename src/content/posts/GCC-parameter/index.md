---
title: GCC parameter
slug: gcc
description: note of gcc
date: 2025-09-10
cover: ../../../assets/wallpaper1.png
tags:
  - c
  - gcc
---

- -o
執行檔的名稱  
ex `gcc -o main main.c`
- -E
- -c
編譯但不連結，產生.o 檔  
ex `gcc -c -o mymax.o mymax.c`
- -l...  
ex. 使用math.h需加`-lm`
- -share  
使.o變成share library(.so)
ex `gcc -share mymax.o -o libmymax.o`

## static link vs dynamic link
查看使用的share library
`ldd ./main`

#### static link
```bash!
gcc -c -o mymax.o mymax.c
gcc main.c mymax.o -o main_static
```

#### dynamic link
```bash!
gcc -c mymax.c -o mymax.o
gcc -shared mymax.o -o libmymax.so
gcc main.c -o main_dynamic -L. -lmymax
```

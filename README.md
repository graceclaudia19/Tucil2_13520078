# Tugas Kecil 2 Strategi Algoritma 
## Pencarian convex hull menggunakan konsep algoritma divide and conquer
---
## Requirements
---
dibutuhkan depedencies berupa
- `numpy`
- `pandas`
- `matplotlib`
- `sklearn`
- `python`

## _Command_ untuk meng-_install depedencies_ :
---
install [python](https://www.python.org/downloads/) lalu jalankan:
```
py3 -m pip install numpy pandas matplotlib sklearn
```
setelah depedencies di install, maka tinggal menggunakan ipynb untuk menjalankannya

## Cara menjalankannya
---
1. Buka folder src untuk melihat file "Tucil2_13520078.ipynb"
2. Jalankan file ipynb dengan menggunakan tombol `run all` yang tertera pada masing-mading IDE
3. Setelah dijalankan, user diminta memasukkan pilihan untuk memilih dataset serta kolom yang ingin divisualisasikan
4. Setelah masukan tervalidasi benar, maka akan ditampilkan diagram convex hull 

## Algoritma secara garis besar
---
Garis Besar Implementasi:

```
function convexHull(points, a, b, direction):
    # mencari convex hull dari titik-titik yang ada
    # input: titik-titik kandidat (points), titik pembentuk garis(p1 dan p2), arah (direction)
    # output: convex hull dari titik-titik kandidat
    if len(points)==0:
        # apabila titik kandidat kosong, maka return kosong
        return []
    if direction == None:
        a <- titik paling kiri pada dataset
        b <- titik paling kanan pada dataset

        up <- array di atas garis yang terbentuk oleh titik a dan b
        down <- array di bawah garis yang terbentuk oleh titik a dan b

        return [a] + convexHull(up, a, b, 1) + [b] + convexHull(down, a, b, -1)[::-1]

    else:
        if direction == 1:
            up <- array di atas garis yang terbentuk oleh titik a dan b

            furthestPoint <- titik terjauh dari garis yang terbentuk oleh titik a dan b di dalam array up

            return [a] + convexHull(up, a, furthestPoint, 1) + [b] + convexHull(up, furthestpoint, b, 1)

        if direction == -1:
            down <- array di bawh garis yang terbentuk oleh titik a dan b

            furthestPoint <- titik terjauh dari garis yang terbentuk oleh titik a dan b di dalam array down

            return [a] + convexHull(down, a, furthestPoint, 1) + [b] + convexHull(down, furthestpoint, b, 1)

```     
### Author: 13520078 - Grace Claudia

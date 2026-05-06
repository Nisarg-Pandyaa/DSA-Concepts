# mtx[n][m] -> new_mtx[m][n]

*Ignore Crystals </br>
<img width="652" height="341" alt="image" src="https://github.com/user-attachments/assets/a19c7ed3-c62a-4d04-9fca-7b30a1004b98" />
</br>
- Code to transfer data from old matrix to new matrix after rotating it 90 degree `CLOCKWISE`

```java
for(int i = 0; i < r; i++){
      for(int j = 0; j < c; j++){
              new_mtx[j][r - 1 - i] = mtx[i][j];
      }
}
```

</br>

- Code to transfer data from old matrix to new matrix after rotating it 90 degree `ANTI CLOCKWISE`

```java
for(int i = 0; i < r; i++){
      for(int j = 0; j < c; j++){
              new_mtx[c - 1 - j][i] = mtx[i][j];
      }
}
```

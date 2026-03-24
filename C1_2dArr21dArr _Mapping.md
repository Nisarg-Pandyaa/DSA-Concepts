# Prefix/Suffix Product/Sum Of Matrix In 1D Array {The "Locker" Logic}

```java
int R = grid.length;
int C = grid[0].length;
int N = R * C;

long[] pre = new long[N];
long[] suf = new long[N];

// 1. Build Prefix Product
long p = 1;
for (int i = 0; i < R; i++) {
    for (int j = 0; j < C; j++) {
        int idx = i * C + j;
        p = p * grid[i][j];
        pre[idx] = p;
    }
}

// 2. Build Suffix Product
p = 1;
for (int i = R - 1; i >= 0; i--) {
    for (int j = C - 1; j >= 0; j--) {
        int idx = i * C + j;
        p = p * grid[i][j];
        suf[idx] = p;
    }
}
```

- `int idx = i * C + j;` => Converts 2D Mtx Co-Ordinates Into A Linear Sequence Index. </br>

  > `i*c` : Tells How Many Rows You Have Passed (i.e, `i` rows we crossed in r*c mtx). </br>
  > `+j` : Tells How Many Steps To Move Forward In Current Row.
  

------------------------------------------------------------------------------------------------------------------------------

# [Product Of Mtx Element Except Self](https://leetcode.com/problems/construct-product-matrix/description/?envType=daily-question&envId=2026-03-24)   [Optimization Of Above]

- S1 : Flatten Mtx Into Array </br>
- S2 : Build the "Left Side" (Prefix) </br>
- S3 : Build the "Right Side" (Suffix) </br>
- S4 : Fill Elements From 1D To Mtx Again

```java
int m = g.length, n = g[0].length;
int size = m * n, mod = [anything given];

int a[] = new int[size];                   // a[x] = mtx[x^th] element 
long p[] = new long[size];                 // p[x] = the product of all elements before index x
long s[] = new long[size];                 // s[x] = the product of all elements after index x.

//S1

int idx = 0;
for(int i=0; i<m; i++){
    for(int j=0; j<n; j++){
        a[idx++] = g[i][j]; // Fill 1D array
    }
}

//S2

p[0] = 1; 
for(int i=1; i < size; i++){                               // Prefix[i] = Previous element * everything before it
    p[i] = (p[i-1] * (a[i-1] % mod)) % mod;
}

//S3 

s[size - 1] = 1;
for(int i = size - 2; i >= 0; i--){                        // Suffix[i] = Element to the right * everything after it
    s[i] = ((a[i+1] % mod) * s[i+1]) % mod;
}

//S4

idx = 0;
for(int i=0; i<m; i++){
    for(int j=0; j<n; j++){
        // Result = (Everything Left) * (Everything Right)
        g[i][j] = (int)((p[idx] * s[idx]) % mod);
        idx++;
    }
}
return g;
```



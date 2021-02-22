## 29210222
* pandasで大容量ファイルをメモリを節約しつつ読み込むには、chunksizeを使う。

```
df = None
for tmp in pd.read_csv(path, chunksize=CHUNK_SIZE):
    if df is None:
        df = tmp
    else:
        df = df.append(tmp
    del tmp
    gc.collect()
```



```python
import pickle
file = open("recs.pkl",'r')
recs = pickle.load(file)
print len(recs)
file.close()
```

```text
2145
```

# tte,censor,age,gender

```python
res = []
N = 200
for i in range(len(recs)):
    if len(recs[i]) > N:res.append(recs[i][-N:])
res = np.array(res).reshape(len(res),N,5)
print res.shape
```

```text
(998, 200, 5)
```

```python
x = res[:,:,[2,3]]
y = res[:,:,[0,1]]
print x.shape, y.shape
idx = 8
print x[idx,:,:]
#print y[idx,:,:]
```

```text
(998, 200, 2) (998, 200, 2)
[[ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]
 [ 41.   1.]]
```






























































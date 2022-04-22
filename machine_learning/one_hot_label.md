One hot encoding is widely used when the result is not linear   
Using tf.one_hot is not as convinient as expected, so I wrote the following codes to do one hot encoding
```
## y is a list consists of decimal from 0.0 to 1.0
def decimal_to_one_hot(y):
    y = np.round(y,decimals=1)*10
    y_one_hot = np.zeros(shape=(y.shape + (11,)))
    for labels, j in zip(y,range(0,len(y))):
        one_hot_labels = np.zeros(shape=(3,11))
        for label,i in zip(labels,[0,1,2]):
            one_hot_arr = np.zeros(11)
            one_hot_arr[int(label)] = 1
            one_hot_labels[i] = one_hot_arr
        y_one_hot[j] = one_hot_labels
    return y_one_hot
```

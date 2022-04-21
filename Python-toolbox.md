# Python Toolbox

# Pandas

## Create a MultiIndex Dataframe from a mutidimensional numpy array
Suppose we have a `(n_frames,n_atoms,n_properties)` ndarray where :
for each frame , and for each atom of your system, you have a `n_properties` $specific properties

we want a DataFrame which have as indices :
- first level : a given frame
- second level : the index of the atom
and as many columns as properties :


level 1| level 2 | prop_1|prop2|prop_3
-|-|-|-|-
frame_1|atom_1|0|1|15
frame_1|atom_2|8|10|2
frame_1|atom_2|8|10|2
...|
frame_2|atom_1|15|23|0
frame_2|atom_2|0|1|1
frame_1|atom_2|8|10|2
...|

```Python
data.shape
``` 
(500,100,3)
```Python
frames = np.arange(data.shape[0])
idatm = np.arange(data.shape[1])
midx = pd.MultiIndex.from_product([frames,idatm],names=("frames","idatm"))
df = pd.DataFrame(
    data=data.reshape(-1,data.shape[2]),
    index=midx,
    columns=['prop_1','prop_2','prop_3']
)
```

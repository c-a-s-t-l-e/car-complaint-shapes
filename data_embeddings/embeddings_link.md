Here is the link to the cleaned code with sentence embeddings included:

https://drive.google.com/file/d/1d4UEWbwCdoy9klR2jr1cT9tu9Yo47-7F/view?usp=sharing

`embeddings.ipynb` was used to create the parquet file.

### How to Load the Parquet File:

1. Install pyarrow

```
pip install pandas pyarrow
```

2. Load the file
```
import pandas as pd

# Load the parquet file
df = pd.read_parquet("your_file.parquet")

# Verify it loaded correctly
print(df.head())
```

### What is the embedding column?
The embedding column contains a 384-dimensional vector (a list of 384 numbers) for every complaint. These were generated using the all-MiniLM-L6-v2 Sentence Transformer model.

Why do we need them? Computers cannot inherently understand text. Embeddings translate the meaning of a sentence into math. Unlike a simple keyword search, embeddings capture semantic similarity.

For example: If you search for "Theft", a keyword search would miss a complaint that says "Someone used my card without permission."

However, in the embedding space, these two concepts are located very close together because they share the same *meaning*.

### Next Steps

The `embeddings.ipynb` notebook contains a simple visual exploration of the dataset using UMAP (for visualization) and K-Means (for clustering). However, more analysis is needed.

# Sycophancy Dataset Generator

<a style="color: #fff; text-decoration: none" href="https://huggingface.co/datasets/romaingrx/sycophancy_rotten_tomatoes">
<div style="display: flex; align-items: center; gap: 1rem; background-color: rgba(100, 100, 100, 0.3); width: fit-content; padding: 0 0.5rem; border-radius: 0.5rem; margin: 1rem 0">
<span>

<img src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo.svg" width="30" height="30" style="vertical-align: middle;" />
</span>
<span>
Dataset Card
</span>
</div>
</a>

This Python script generates a dataset for a sentiment analysis task. The generated dataset includes a prompt, the sentiment of the prompt, and additional information.

### Dataset Structure

The dataset is structured as a pandas DataFrame with the following columns:

- `split`: The dataset split. This can be "train", "test", or "validation".
- `text`: The generated prompt text.
- `assistant_opinion`: The assistant's opinion, converted to a label.
- `human_opinion`: The human's opinion, converted to a label.
- `sycophancy`: A binary value indicating whether the assistant's opinion is the same as the human's opinion but different from the ground truth.
- `comment`: The comment that the sentiment analysis is based on.
- `ground_truth`: The actual sentiment of the comment.
- `non_sense`: A binary value indicating whether the assistant's opinion is different from both the human's opinion and the ground truth.
  Important Notes

> [!IMPORTANT]  
> The `non_sense` column reports instances where the assistant provides an answer that is different from the ground truth, even though the human has given their opinion that matches the correct label. This column is particularly useful for identifying instances where the assistant is not aligning with the correct sentiment.

### Usage

To use this script, you need to have the names, random, and pandas Python packages installed. The script uses the rotten_tomatoes dataset from the datasets package.

To run the script, simply execute the following command:

```bash
python generate_dataset.py
```

This will generate the dataset and save it as CSV files in the data directory, with separate files for the train, test, and validation splits.
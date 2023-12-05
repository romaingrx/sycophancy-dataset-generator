# Sycophancy Dataset Generator

<a href="https://huggingface.co/datasets/romaingrx/sycophancy_rotten_tomatoes">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg">
    <img alt="Hugging Face Datasets Library" src="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg" width="200" height="59" style="max-width: 200px;">
  </picture>
  <br/>
  <br/>
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

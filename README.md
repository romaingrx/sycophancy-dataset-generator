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

The generated dataset includes a text (chat between a human and an assistant), the sycophancy of the exchange, and additional information.

### Dataset Structure

The dataset is structured as follows:

- `text`: The generated prompt text of the chat between the human and the assistant.
- `assistant_opinion`: The assistant's opinion, converted to a label (i.e. its final answer.
- `human_opinion`: The human's opinion, converted to a label.
- `sycophancy`: A binary value indicating whether the assistant's opinion is the same as the human's opinion but different from the ground truth.
- `comment`: The initial comment from Rotten Tomatoes.
- `ground_truth`: The actual label of the initial comment.
- `non_sense`: A binary value indicating whether the assistant's opinion is different from both the human's opinion and the ground truth.
  
> [!IMPORTANT]  
> The `non_sense` column reports instances where the assistant provides an answer that differs from the ground truth, even though the human has given their opinion that matches the correct label. You might want to discard these entries as they represent an exchange that doesn't make sense since the assistant's answer is simply false.
> 
### Usage

To use this script, you need to have the names, random, and pandas Python packages installed. The script uses the rotten_tomatoes dataset from the datasets package.

To run the script, simply execute the following command:

```bash
python generate_dataset.py
```

This will generate the dataset and save it as CSV files in the data directory, with separate files for the train, test, and validation splits.

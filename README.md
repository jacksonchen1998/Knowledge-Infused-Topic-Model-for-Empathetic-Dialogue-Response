# Knowledge-Infused Topic Model for Empathetic Dialogue Response

![KITM](fig/kitm.png)

This repository contains the implementation of the **Knowledge-Infused Topic Model (KITM)** for generating empathetic dialogue responses using topic modeling enhanced with commonsense knowledge.

📄 **Accepted to APSIPA ASC 2025**
([Proceedings Paper](http://www.apsipa.org/proceedings/2025/papers/APSIPA2025_P576.pdf))

---

## 🔧 Installation

Install all required packages via:

```bash
conda install --yes --file requirements.txt
```

---

## 🛠️ Pre-processing

1. **Download GloVe embeddings**
   Download the [GloVe.6B embeddings](http://nlp.stanford.edu/data/glove.6B.zip) and place them in:

   ```
   /vectors
   ```

2. **Dataset preprocessing**

   * A preprocessed dataset (`dataset_preproc.p`) is already included under:

     ```
     /data/ED/dataset_preproc.p
     ```

   * If you would like to **regenerate the dataset** or **modify knowledge types from COMET**:

     1. Delete `dataset_preproc.p`
     2. Download the [COMET-ATOMIC-2020 checkpoint](https://github.com/allenai/comet-atomic-2020)
     3. Place it under:

        ```
        /data/ED/Comet
        ```

   * The dataset will be automatically reprocessed during training.

   * **Note:** We use **BART-COMET** because the GPT-2 COMET checkpoint is incompatible with this workflow.

---

## 📚 Datasets

This work uses two dialogue datasets, with the default configuration set to **EmpatheticDialogues**.

* [EmpatheticDialogues](https://github.com/facebookresearch/EmpatheticDialogues)
* [DailyDialog](http://yanran.li/dailydialog)

### 🔗 Data Resources (Download)

* **[EmpatheticDialogues](https://drive.google.com/drive/folders/1UiEr4ug0nc4uJQYvvO2U4MHt3bhf66VW?usp=sharing)**

* **[DailyDialog](https://drive.google.com/drive/folders/1nUBCQjNjlNjqLZykrYoiKxDAKUVYQApK?usp=sharing)**

---

## 📁 Directory Structure

```
data
|--- ED
|    |--- Comet/          # COMET model for commonsense inference
|    |--- emp.pkl         # Topic appearance probabilities
|    |--- train.csv
|    |--- valid.csv
|    |--- test.csv
|
|--- DD
     |--- Comet/
     |--- dd.pkl          # Topic appearance probabilities
     |--- train.csv
     |--- valid.csv
     |--- test.csv
```

### Directory Descriptions

#### `data/ED/`

Files and COMET knowledge used for **EmpatheticDialogues**.

#### `data/DD/`

Files and COMET knowledge used for **DailyDialog**.

---

## 🚀 Training

Run training with:

```bash
python main.py --cuda --save_path save/your_dir
```

---

## 🧪 Testing

```bash
python main.py --cuda --test \
    --save_path save/your_dir \
    --model_path save/dir_save/KITM_XXXX.XXX
```

---

## 📬 Contact

If you have questions or are interested in collaboration, feel free to contact:

**[present90308.ee11@nycu.edu.tw](mailto:present90308.ee11@nycu.edu.tw)**


Just let me know!

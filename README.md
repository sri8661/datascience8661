# kaggle-base

- Template directory for datascience competitions.
- Data is saved in PostgreSQL on Dockerð³ container and the data is reproducibule/reusable ðð

## Usage

### Step0. Clone the repository

```sh
git clone https://github.com/kiccho1101/kaggle-base.git
cd kaggle-base
```

### Step1. Pull/Build Docker image

Recommended:

```sh
make pull
```

or

```sh
make build
```

### Step2. Start up jupyter notebook

```sh
make jupyter
```

- Copy token and acccess to localhost:${JUPYTER_PORT} (default: 9000)

### Step3. Start up DB

```sh
make start-db
```

- Then you can access to localhost:${PGWEB_PORT} (default: 9002) to view the database.

### Step4. Split train data into K-fold

```sh
make kfold CONFIG_NAME(default: lightgbm_0)
```

### Step5. Create Features

- Create all features.

```sh
make feature
```

- Specify a feature that will be created.

```sh
make feature FEATURE_NAME
```

### Step6. Cross Validation

```sh
make cv CONFIG_NAME
```

### Step7. Create Stats of each table

```sh
make stats
```

### Step8. Train and Predict

```sh
make train-and-predict CONFIG_NAME
```

### Step9. Submit

- Then submit your output file!ð

```sh
./output/submission_xxx.csv
```

## Commands

### isort, black

```sh
make format
```

### flake8, mypy

```sh
make check
```

### Reset DB

```sh
make reset-db
```

### execute scripts

Recommended:

```sh
make shell
python xxx.py
```

or

```sh
make run python xxx.py
```

## References

### [1.ãã¼ã¿åæã³ã³ãã«ããã¦ ç¹å¾´éç®¡çã«ç²å¼ãã¦ããå¨äººé¡ã«ä¼ãããæ³ã][1]

ã¾ãã«ç¹å¾´éç®¡çã«ç²å¼ãã¦ããã¨ãã«è¦ã¤ããã¹ã©ã¤ãããããããããããã§ãã

### [2.Kaggleã§ä½¿ããFeatherå½¢å¼ãå©ç¨ããç¹å¾´éç®¡çæ³][2]

ã¯ã©ã¹ã®æ¸ãæ¹ãåèã«ãªãã¾ãã

### [3.flowlight0's directory][3]

### [4.upura's directory][4]

[1]:https://speakerdeck.com/takapy/detafen-xi-konpenioite-te-zheng-liang-guan-li-nipi-bi-siteiruquan-ren-lei-nichuan-etaixiang-i
[2]:https://amalog.hateblo.jp/entry/kaggle-feature-management
[3]:https://github.com/flowlight0/talkingdata-adtracking-fraud-detection
[4]:https://github.com/upura/ml-competition-template-titanic

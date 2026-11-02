# Python・Git Tips / Python and Git Tips

このファイルは構文を確認するための道具箱です。目的に合うものを自分で選んでください。  
This file is a syntax toolbox. Choose the tools that fit each task.

## 関数・引数・return / Functions, arguments, and return

```python
def make_message(name):
    message = "Hello, " + name
    return message
```

引数で受け取った値を使います。`return`がない関数の戻り値は`None`です。  
Use the value received as an argument. A function without `return` returns `None`.

## ファイルを読み込む / Read a file

```python
with open(filename, encoding="utf-8") as file:
    text = file.read()
```

## 行に分ける / Split into lines

```python
lines = text.splitlines()
```

## ヘッダーを除く / Remove the header

```python
data_lines = lines[1:]
```

## 空行を除く / Remove blank lines

```python
result = []
for line in lines:
    if line != "":
        result.append(line)
```

## カンマで列に分ける / Split fields by commas

```python
fields = line.split(",")
first = fields[0]
second = fields[1]
```

添字は0から始まります。 / Indexes start at 0.

## リストを作り、追加する / Create and append to a list

```python
values = []
values.append(value)
```

## 条件を確認する / Check conditions

```python
if status == "active":
    print(status)
```

```python
if username.startswith("abc-"):
    print(username)
```

## 条件を組み合わせる / Combine conditions

```python
if condition1 and condition2 and condition3:
    print("all conditions are true")
```

## 並べ替える / Sort values

```python
ascending = sorted(values)
descending = sorted(values, reverse=True)
```

## 件数と重複しない件数 / Count items and unique items

```python
count = len(values)
unique_count = len(set(values))
```

## 繰り返して表示する / Print items in a loop

```python
for value in values:
    print(value)
```

## Gitの確認と記録 / Check and record with Git

```bash
git status
git diff
git add ファイル名
git commit -m "変更内容"
git push
git log --oneline
```

Notebookは保存してから`git add`してください。  
Save the Notebook before running `git add`.

# Python・Git Tips / Python and Git Tips

このファイルは、構文を確認するための道具箱です。目的に合うものを自分で選んで使ってください。  
This file is a toolbox for checking syntax. Choose the appropriate tool for your task.

## ファイルを読み込む / Read a file

```python
with open("login_data.csv", encoding="utf-8") as file:
    text = file.read()
```

`file.read()`は、ファイル全体を1つの文字列として読み込みます。  
`file.read()` reads the entire file as one string.

## 文字列を行に分ける / Split text into lines

```python
lines = text.splitlines()
```

複数行の文字列を、1行ずつのリストにします。  
This converts multiline text into a list of lines.

## 区切り文字で列に分ける / Split a line into fields

カンマ区切り / Comma-separated:

```python
fields = line.split(",")
```

コロン区切り / Colon-separated:

```python
fields = line.split(":")
```

空白区切り / Whitespace-separated:

```python
fields = line.split()
```

## リストへ追加する / Add an item to a list

```python
values.append(value)
```

`append()`は、リストの末尾へ値を1つ追加します。  
`append()` adds one value to the end of a list.

## 条件が同じか確認する / Check for equality

```python
if status == "active":
    print(status)
```

`==`は、2つの値が等しいか確認します。  
`==` checks whether two values are equal.

## 文字列の先頭を確認する / Check the beginning of a string

```python
username = "siw-260101"

if username.startswith("siw-"):
    print(username)
```

`startswith()`は、文字列が指定した文字列から始まるか確認します。  
`startswith()` checks whether a string begins with the specified text.

## 文字列に含まれるか確認する / Check whether text is contained

```python
if "siw-" in username:
    print(username)
```

`in`は、指定した文字列が途中を含めてどこかに存在するか確認します。  
`in` checks whether the specified text appears anywhere in the string.

| 書き方 / Expression | 確認すること / Meaning |
|---|---|
| `username.startswith("siw-")` | 先頭が`siw-`で始まる / Begins with `siw-` |
| `"siw-" in username` | どこかに`siw-`を含む / Contains `siw-` somewhere |

## 複数の条件を組み合わせる / Combine conditions

両方を満たす / Both conditions must be true:

```python
if username.startswith("siw-") and shell == "/bin/zsh":
    print(username)
```

どちらかを満たす / At least one condition must be true:

```python
if shell == "/bin/bash" or shell == "/bin/zsh":
    print(shell)
```

## 並べ替える / Sort values

元のリストを変えず、並べ替えた新しいリストを作ります。  
Create a new sorted list without changing the original list.

```python
sorted_values = sorted(values)
```

元のリスト自体を並べ替えます。  
Sort the original list itself.

```python
values.sort()
```

降順 / Descending order:

```python
sorted_values = sorted(values, reverse=True)
```

## 重複を除く / Remove duplicate values

```python
unique_values = set(values)
```

`set()`は、重複を除いた集合を作ります。  
`set()` creates a collection without duplicate values.

## 件数を調べる / Count items

```python
count = len(values)
```

`len()`は、文字列、リスト、集合などの要素数を返します。  
`len()` returns the number of items in a string, list, set, or other collection.

## 文字列をつなげる / Join strings

カンマでつなぐ / Join with commas:

```python
text = ",".join(values)
```

改行でつなぐ / Join with line breaks:

```python
text = "\n".join(values)
```

## 繰り返して表示する / Display items in a loop

```python
for value in values:
    print(value)
```

`for`は、リストなどから値を1つずつ取り出します。  
`for` takes each value from a list or another iterable one at a time.

## Gitで状態を確認する / Check the Git status

```bash
git status
git diff
git log --oneline
```

- `git status`: 変更状態を確認する / Check the current state of files
- `git diff`: 変更内容を確認する / View changes
- `git log --oneline`: コミット履歴を確認する / View the commit history

## Gitへ記録する / Record changes with Git

```bash
git add ファイル名
git commit -m "変更内容を書く"
git push
```

```bash
git add filename
git commit -m "Describe the change"
git push
```

## NotebookをGitで扱うときの注意 / Working with a Notebook in Git

コミット前にセルを上から順に実行し、エラーがないことを確認してください。Notebookを保存してから`git add`します。  
Before committing, run the cells from top to bottom and confirm that there are no errors. Save the Notebook before running `git add`.

コミットメッセージには、何ができるようになったかを書きます。  
In the commit message, describe what the program can now do.

```text
CSVを読み込めるようにした
Add CSV file reading
```

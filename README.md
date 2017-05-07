# 項目說明

## 所有權說明

**這個github帳號whatot並非原著者，whatot只是將wjm_tcy編著的大李敖全集進行格式化，沒有其它額外加工。
所有權利由leeao與wjm_tcy保持，此處僅為傳播與留存。**

**編著者介紹見同目錄“wjm_tcy.md”**

## 建庫本意

我看wjm_tcy花費很多時間對“大李敖全集”進行整合，但是使用的txt格式，並且文件內無格式，不便於閱讀，於是就對成品txt進行格式化。
最終組成一個gitbook項目，可以通過gitbook轉化成pdf、epub或者mobi，便於在各種設備上閱讀。

我對作者的文章內容持保留態度，僅通過此項目減少編著的合集埋沒的可能。

## 生成pdf、epub或者mobi

參考 https://help.gitbook.com/

## 文件處理流程

* using enca to convert files to UTF-8/LF
	enca -L zh_CN -x UTF-8 */*.txt
* check all the txt files's coding
	find -type f -name '*.txt' | xargs file
* delete unneeded lines
	find -type f -name '*.txt' | xargs sed -i '/李敖研究網/d'
* deleted trailing spaces
	find -type f -name '*.txt' | xargs sed -i 's/[ \t\r ]\+$//'
* delete all spaces
	find -type f -name '*.md' | xargs sed -i 's/[  ]//'
* rename all *.txt to *.md
	for f in *.txt; do mv -- "$f" "${f%.txt}.md"; done


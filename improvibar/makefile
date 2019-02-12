all: improvibar.pdf improvibar.html

improvibar.pdf: improvibar.ipynb
	jupyter nbconvert --execute --to pdf improvibar.ipynb

improvibar.html: improvibar.ipynb
	jupyter nbconvert --execute --to html improvibar.ipynb

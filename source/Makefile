run:
	cp -R static-html/* ..
	pelican -t theme -s settings.py -o .. content
	cp ../pages/* ../
	cp -R ../theme/img/* ../img/
	rm -rf ../pages/

run-no-static:
	cp -R static-html/* ..
	pelican -t theme -s settings.py -o .. content
	cp ../pages/* ../
	rm -rf ../pages/

init:
	pip install -r requirements.txt

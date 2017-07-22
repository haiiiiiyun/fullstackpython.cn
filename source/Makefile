run:
	cp -R static-html/* ..
	cp redirects/* ..
	pelican -t theme -s settings.py -o .. content
	cp ../pages/* ../
	cp -R ../theme/img/* ../img/
	cp -R ../theme/css/* ../
	rm -rf ../pages/

run-no-static:
	cp -R static-html/* ..
	cp redirects/* ..
	pelican -t theme -s settings.py -o .. content
	cp ../pages/* ../
	rm -rf ../pages/

init:
	pip install -r requirements.txt

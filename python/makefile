install:
	pip install --upgrade pip &&\
		pip install pytest
		pip install black
		pip install pylint
		pip install -r requirements.txt

format:
	@find "$(PWD)" -name "*.py" -exec black {} +
	
lint:
	pylint --output-format=colorized --disable=R,C *.py

test:
	python3 -m pytest -vv test_*.py
	
run:
	python main.py	

all:
	make install format lint test

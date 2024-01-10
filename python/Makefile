all_versioned_python_files := $$(git ls-files '*.py')

install:
	pip install --upgrade pip
	pip install -r requirements.txt
	pip install black flake8 pylint pytest

submodules:
	git submodule sync
	git submodule update --init --recursive --remote

format:
	python3 -m black --line-length=79 $(all_versioned_python_files)

flake:
	python3 -m flake8 --max-complexity=8 $(all_versioned_python_files)

lint:
	python3 -m pylint --output-format=colorized --disable=R,C $(all_versioned_python_files)

test:
	python3 -m pytest -v -rP -x test_*.py

all:
	make \
	install \
	submodules \
	format \
	lint \
	test

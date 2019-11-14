.PHONY: all setup test install clean

PYTHON := python3
PYOPENABE := pyopenabe

all: $(PYOPENABE)

setup:
	pip install -r requirements.txt;

$(PYOPENABE): setup
	$(PYTHON) setup.py build_ext --inplace; \
	$(PYTHON) setup.py bdist --format=zip; \

test:
	$(PYTHON) test.py

install:
	$(PYTHON) setup.py install

clean:
	$(RM) -rf dist/ build/ *.cpp *.so

distclean:
	$(RM) -rf venv/ dist/ build/ *.cpp *.so

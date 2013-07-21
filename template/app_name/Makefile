.PHONY: test release doc

test:
	flake8 {{app_name}} --ignore=E501,E127,E128,E124 --filename=*.py --exclude=static,migrations
	coverage run --branch --source=shisan `which django-admin.py` test shisan --settings={{app_name}}.tests.test_settings
	coverage report --omit={{app_nam}}/test*

release:
	python setup.py sdist bdist_wheel register upload -s

doc:
	cd docs; make html; cd ..

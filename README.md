[![Tests](https://github.com/awi-response/ckanext-apgc_theme/workflows/Tests/badge.svg?branch=main)](https://github.com/awi-response/ckanext-apgc_theme/actions)

# ckanext-apgc_theme

CKAN Theme Extension for customizing the templates
for instruction how to build such an extension see: https://docs.ckan.org/en/2.9/theming/templates.html


## Requirements

Compatible with CKAN 2.11 python 3.10

## Installation

**TODO:** Add any additional install steps to the list below.
   For example installing any non-Python dependencies or adding any required
   config settings.

To install ckanext-apgc_theme:

1. Activate your CKAN virtual environment, for example:

     . /usr/lib/ckan/default/bin/activate

2. Clone the source and install it on the virtualenv

    git clone https://github.com/awi-response/ckanext-apgc_theme.git
   
    cd ckanext-apgc_theme
   
    pip install -e .
   
	pip install -r requirements.txt

4. Add `apgc_theme` to the `ckan.plugins` setting in your CKAN
   config file (by default the config file is located at
   `/etc/ckan/default/ckan.ini`).

5. Restart CKAN. For example if you've deployed CKAN with supervisor on Ubuntu:

     sudo service supervisor restart


## Config settings

None at present


## Developer installation

To install ckanext-apgc_theme for development, activate your CKAN virtualenv and
do:

    git clone https://github.com/awi-response/ckanext-apgc_theme.git
    cd ckanext-apgc_theme
    python setup.py develop
    pip install -r dev-requirements.txt


## Tests

To run the tests, do:

    pytest --ckan-ini=test.ini


## Releasing a new version of ckanext-apgc_theme

If ckanext-apgc_theme should be available on PyPI you can follow these steps to publish a new version:

1. Update the version number in the `setup.py` file. See [PEP 440](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers) for how to choose version numbers.

2. Make sure you have the latest version of necessary packages:

    pip install --upgrade setuptools wheel twine

3. Create a source and binary distributions of the new version:

       python setup.py sdist bdist_wheel && twine check dist/*

   Fix any errors you get.

4. Upload the source distribution to PyPI:

       twine upload dist/*

5. Commit any outstanding changes:

       git commit -a
       git push

6. Tag the new release of the project on GitHub with the version number from
   the `setup.py` file. For example if the version number in `setup.py` is
   0.0.1 then do:

       git tag 0.0.1
       git push --tags

## License

[AGPL](https://www.gnu.org/licenses/agpl-3.0.en.html)

** Getting Started **
To get a local copy up and running follow these simple example steps.
https://www.youtube.com/watch?v=0ut8-lL-E14&list=PLT3v18VYaHYXY6qa2frMIV2FVl52L2tmP

1. Setup Database
https://www.odoo.com/documentation/16.0/administration/install/source.html

On mac:
brew install postgresql@15 libpq
brew link --force libpq
brew services start postgresql@15

Once you've done that, let's check that it worked:
psql -d postgres

2. Create the user
CREATE USER odoo16 SUPERUSER;
ALTER USER odoo16 WITH PASSWORD 'odoo16';

3. Clone Odoo v16.0
git clone git@github.com:odoo/odoo.git --depth 1 --branch 16.0

4. Install dependencies 
pip install -r requirements.txt 

5. Install openssl to avoid errors below:
i. Install openssl with brew install openssl if you don't have it already.
ii. Add openssl path to LIBRARY_PATH :
export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/opt/openssl/lib/

 Running setup.py install for psycopg2 did not run successfully.
  │ exit code: 1
  ╰─> [155 lines of output]
 Resolution: pip install --upgrade wheel

  × python setup.py bdist_wheel did not run successfully.
  │ exit code: 1
  ╰─> [153 lines of output]
      /Users/altera/PycharmProjects/odoo-16/venv/lib/python3.9/site-packages/setuptools/config/setupcfg.py:508: SetuptoolsDeprecationWarning: The license_file parameter is deprecated, use license_files instead.
        warnings.warn(msg, warning_class)
      running bdist_wheel

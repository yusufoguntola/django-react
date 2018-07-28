## Django-React Startup Project

Webpack configuration is production ready.

### To run locally
Run `npm start` within `frontend` directory and then

Activate your virtualenv and run `python manage.py runserver`.

Hot reload is also setup, so updates should automatically be updated as usual.


### To prepare app for production
Create `settings_prod.py` in the project directory at the same level with `settings.py` and put the below code in it:

```python

from .settings import *

STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "assets"),
]

WEBPACK_LOADER = {
    'DEFAULT': {
            'BUNDLE_DIR_NAME': 'bundles/',
            'STATS_FILE': os.path.join(BASE_DIR, 'webpack-stats.prod.json'),
        }
}

```

Then create `assets` folder in the root directory and run `npm run build` (feel free to run build on the server to reduce file size to push).

Manually run `python manage.py collectstatic` on the production server if need be.

Everything should be fine now!!!


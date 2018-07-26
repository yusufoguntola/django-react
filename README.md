## Django-React Startup Project

Webpack configuration is production ready.

### To prepare app for production
Create `settings_prod.py` in the root directory and the below code in it:

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

Then create `assets` folder in the root directory and run `npm run build`.

Everything should be fine now!!!


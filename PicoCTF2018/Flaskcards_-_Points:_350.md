[Category:Picoctf](/Category:Picoctf "wikilink") We found this fishy
website for flashcards that we think may be sending secrets. Could you
take a look?

the title hints to flask(python) being used as a server

after some lookaround we dont see any sql injection stuff so lets look
at common flask vulnerabilities.

template injection if we have an input field or parameter we can do like
{{ 1+1 }} and it will evaluate to 2 so we can execute code on the server
cool

lets look at

Question:\<Config {'SQLALCHEMY_TRACK_MODIFICATIONS': False,
'APPLICATION_ROOT': '/', 'SESSION_COOKIE_NAME': 'session',
'PRESERVE_CONTEXT_ON_EXCEPTION': None, 'SESSION_COOKIE_HTTPONLY':
True, 'SQLALCHEMY_POOL_TIMEOUT': None, 'SESSION_COOKIE_PATH': None,
'SQLALCHEMY_RECORD_QUERIES': None, 'SESSION_COOKIE_SAMESITE': None,
'BOOTSTRAP_CDN_FORCE_SSL': False, 'TEMPLATES_AUTO_RELOAD': None,
'SECRET_KEY': 'picoCTF{secret_keys_to_the_kingdom_584f8327}',
'PREFERRED_URL_SCHEME': 'http', 'JSONIFY_MIMETYPE':
'application/json', 'DEBUG': False, 'BOOTSTRAP_LOCAL_SUBDOMAIN': None,
'TRAP_BAD_REQUEST_ERRORS': None, 'SEND_FILE_MAX_AGE_DEFAULT':
datetime.timedelta(0, 43200), 'PROPAGATE_EXCEPTIONS': None,
'SQLALCHEMY_POOL_RECYCLE': None, 'PERMANENT_SESSION_LIFETIME':
datetime.timedelta(31), 'SQLALCHEMY_COMMIT_ON_TEARDOWN': False,
'TESTING': False, 'JSONIFY_PRETTYPRINT_REGULAR': False,
'MAX_CONTENT_LENGTH': None, 'SESSION_COOKIE_DOMAIN': False,
'BOOTSTRAP_USE_MINIFIED': True, 'SQLALCHEMY_POOL_SIZE': None,
'SERVER_NAME': None, 'EXPLAIN_TEMPLATE_LOADING': False,
'JSON_AS_ASCII': True, 'JSON_SORT_KEYS': True,
'SESSION_COOKIE_SECURE': False, 'SQLALCHEMY_DATABASE_URI':
'sqlite://', 'SQLALCHEMY_ECHO': False, 'ENV': 'production',
'SQLALCHEMY_BINDS': None, 'BOOTSTRAP_SERVE_LOCAL': False,
'USE_X_SENDFILE': False, 'TRAP_HTTP_EXCEPTIONS': False,
'SQLALCHEMY_MAX_OVERFLOW': None, 'SESSION_REFRESH_EACH_REQUEST':
True, 'MAX_COOKIE_SIZE': 4093, 'SQLALCHEMY_NATIVE_UNICODE': None,
'BOOTSTRAP_QUERYSTRING_REVVING': True}\>

picoCTF{secret_keys_to_the_kingdom_584f8327}
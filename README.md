johnny@jyjetson:~/Downloads/web_play/python_flask$ python3
Python 3.6.9 (default, Jan 26 2021, 15:33:00) 
[GCC 8.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from app import db, BlogPost
/home/johnny/.local/lib/python3.6/site-packages/flask_sqlalchemy/__init__.py:873: FSADeprecationWarning: SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and will be disabled by default in the future.  Set it to True or False to suppress this warning.
  'SQLALCHEMY_TRACK_MODIFICATIONS adds significant overhead and '
>>> BlogPost.query.all()[2].date_posted
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
>>> BlogPost.query.all()
[Blog post 1, Blog post 2]
>>> BlogPost.query.all()
[Blog post 1, Blog post 2]
>>> BlogPost.query.first()
Blog post 1
>>> BlogPost.query[1]
Blog post 2
>>> BlogPost.query.filter_by(title='test'
... 
KeyboardInterrupt
>>> BlogPost.query.filter_by(title='test').all()
[]
>>> BlogPost.query.filter_by(title='*test*').all()
[]
>>> BlogPost.query.filter_by(title='not').all()
[]
>>> BlogPost.query.filter_by(title='*not*').all()
[]
>>> BlogPost.query.filter_by(title='%not%').all()
[]
>>> BlogPost.query.filter_by(title='This is not a user').all()
[Blog post 1]
>>> BlogPost.query.get(1)
Blog post 1
>>> BlogPost.query.get(2)

>>> db.session.delete(BlogPost.query.get(2))
>>> db.session.commit()


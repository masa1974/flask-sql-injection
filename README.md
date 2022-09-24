# flask-sql-injection
This is sql-injection demo site by flask.

1. execute sql-injection.py
   python sql-injection.py

2. Access localport 5000 by Browser
   http://localhost:5000

3. login normal
   ID: user1
   Pass: 123456

4. do sql injection
   ID: A' or '1' = '1' --
   Pass: 1111

If you want to fix this vulnerability, edit getuser.py Line 11
   
cur.execute("SELECT flag FROM user WHERE username='%s' AND password='%s'" %(username,password))
↓
cur.execute("SELECT flag FROM user WHERE username=? AND password=?",(username,password))

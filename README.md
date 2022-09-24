# flask-sql-injection
This is sql-injection demo site by flask.

1. execute sql-injection.py <br>
   python sql-injection.py <br><br>

2. Access localport 5000 by Browser <br>
   http://localhost:5000 <br><br>

3. login normal <br>
   ID: user1 <br>
   Pass: 123456 <br><br>

4. do sql injection <br>
   ID: A' or '1' = '1' -- <br>
   Pass: 1111 <br><br>

If you want to fix this vulnerability, edit getuser.py Line 11 <br>
   
cur.execute("SELECT flag FROM user WHERE username='%s' AND password='%s'" %(username,password)) <br>
↓ <br>
cur.execute("SELECT flag FROM user WHERE username=? AND password=?",(username,password))

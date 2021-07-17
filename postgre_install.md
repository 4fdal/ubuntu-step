```
sudo apt update
sudo apt install postgresql postgresql-contrib

sudo -i -u postgres

```


Create User
```
// change password user postgres to secret
alter user postgres with password 'secret'

//create new user home with password secret
create user home with password 'secret' ;

//change permisson home to super user
alter user home with superuser ;
```

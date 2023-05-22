## Software Installation for Ubuntu OS

### NVM and Node
Run the following commands to install nvm:
```
sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 
source ~/.bashrc
```
You can install node using the node-version-manager
```
nvm install node 
```
Then you can install specific node versions like this:
```
nvm install 00.00.0   // specify a version, or
nvm install --lts     // latest long-term-suport version
```

### Postgres
Postgres usually comes by default. But the latest documentation for installing it can be found at Postgres [website](https://www.postgresql.org/download/linux/ubuntu/).

```
sudo apt update
sudo apt -y upgrade
sudo apt-get install postgresql postgresql-contrib
```
Then run PostgreSQL server using:
```
sudo systemctl start postgresql.service
```
To automatically launch PostgreSQL upon system boot-up, register it with systemctl.
```
sudo systemctl enable postgresql.service
```
Verify PostgreSQL is running as expected.
```
sudo systemctl status postgresql.service
```
To secure PostgreSQL and access the `psql` shell:
```
sudo passwd postgres                                         // change pswd for postgres linux acc
sudo su - postgres                                           // switch to postgres user
psql -c "ALTER USER postgres WITH PASSWORD 'newpassword'"    // set a new passwor for user
psql -c "SELECT version();"                                  // check it works properly
psql postgres                                                // login to postgres
```
Exit psql shell using `\q` followed by `Enter`.

**From a Linode [article](https://www.linode.com/docs/guides/how-to-install-use-postgresql-ubuntu-20-04/):**  
"By default, PostgreSQL grants access to local system users without requiring a password. This is known as peer authentication. PostgreSQL obtains the system name of the user and verifies it against the database privileges. To enforce password authentication from local users, you must edit the `pg_hba.conf` file. Run the following command within the psql shell to determine the location of this file."
```
psql -c "SHOW hba_file;"       // see where hba file is located
\q                             // exit psql shell
sudo nano <file-location>      // open file to edit
```
Edit the pg_hba.conf file to enforce authentication. Find the local line under “Unix domain socket connections only” and change the `METHOD` attribute from `peer` to `md5`.
It should look like the following:
```
# "local" is for Unix domain socket connections only
local   all             all                                     md5
```
Then restart postgres server using:
```
sudo systemctl restart postgresql.service
```
Now that you have postgres set up, you can use the following commands to work with database:
```
psql -U postgres -W            // enter postgres shell
CREATE DATABASE testdb         // create a database 
\l                             // list all databases
```
If you prefer GUI, install Tableplus or similar data managemment software.

### Tableplus
Used for managing SQL database. Very convenient and simple to use. Makes it easier to interact with database content. To install, check the official installation instruction for Ubuntu [here](https://tableplus.com/blog/2019/10/tableplus-linux-installation.html).


### VS Code
Download the `.deb` file from VS Code [website](https://code.visualstudio.com/Download) and open it using Ubuntu "Software".


# Setting up a PERN Stack on Fedora Linux

## Part 1: Installations

---Make sure that you have administrator priviledges in your machine. If you do not have that access use "sudo" in front of some of these commands.---

### PostgreSQL Installation/Initial Database Setup
Follow these instructions in the command line of your fedora Linux machine:

Step 1: Install PostgreSQL Using dnf
```
dnf install postgresql-server postgre-contrib
```
Step 2: Set PostgreSQL to Start at Boot Time
```
systmectl enable postgresql
```
Step 3: Initialize the Database
```
postgresql-setup --initdb --unit postgresql
```
Step 4: Reboot System or Start PostgreSQL Manually Using:
```
systemctl start postgresql
```
Step 5: Create a PostgreSQL User and Database
```
psql postgres
```
After running the command above, you are in the postgresql command prompt. You can create a user and databse from here with these commands:
```
CREATE USER <username> WITH PASSWORD '<password>';
CREATE DATABASE <project_name> OWNER <username>;
```
Step 6: Exit the Terminal
```
/q
```
OR Ctrl + D

You can now access you user's database at any time with this command:
```
psql <project_name>
```


### Node.js Installation
Follow these instructions in the command line of your fedora Linux machine:
Step 1: Install Node.js Using dnf
```
dnf install nodejs
```
Step 2: Set Node.js to Start at Boot Time
```
systemctl enable nodejs
```
Step 3: Reboot System or Start Nodejs Maually with
```
systemctl start nodejs
```


### Express Installation/Web Server Setup
Follow these insctructions in the command line of your Fedora Linux machine to install and set up a basic web server using express:
Step 1: Create and Move Into a Directory for your project
```
mkdir <projectname>
cd <projectname>
```
Step 2: Create a package.json file. Accept all default options by pressing the enter key.
```
npm init -y
```
Step 3: Install Express using npm
```
npm i express pg
```

Get a copy of [virtualenv](https://pypi.python.org/pypi/virtualenv).

Configure AWS access key
```
$ cp .env.example .env
# fill your details in the .env file
```

Install packages
```
# create new python virtual env
$ virtualenv venv
New python executable in .../venv/bin/python2
Also creating executable in .../venv/bin/python
Installing setuptools, pip, wheel...done.

# activate virtual env
$ source venv/bin/activate

# install ansible and missing modules
$ pip install -r requirements.txt

# reload shell bin
$ hash -r
# or?
$ rehash
```

check vars/dev/vars.yml if you'd like to make any changes to instance type,
ssh keypair name, volume size or AMI. you probably want to change the keypair.

let's run
```
$ ansible-playbook -vvv -i "localhost," --connection=local ec2.yml
```

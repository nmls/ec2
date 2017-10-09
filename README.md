Get a copy of [virtualenv](https://pypi.python.org/pypi/virtualenv).

Configure AWS access key, region and your keypair for all EC2 instances
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

Check vars/dev/vars.yml if you'd like to make any changes to default EC2
instance.

If you're happy, run the playbook

```
$ ansible-playbook -vvv -i "localhost," --connection=local ec2.yml
```

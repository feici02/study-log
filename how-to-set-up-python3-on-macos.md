## How to setup a Python3 environment on macOS?

macOS Sierra (10.12) comes with Python2, but not with Python3.
Please follow steps below to setup a Python3 environment:

```
brew search python

# install Python3
brew install python3

# create a virtual environment
python3 -m venv venv

# activate above venv
# the prompt will change after this step
source venv/bin/activate

# check the path
# it should be under ./venv
which python

# pip and pip3 can also be found ./venv,
# and they are the same
which pip

# test your env
python hello.py
```

hello.py
```
print("Hello, world!")
```

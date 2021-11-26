# python-web-app
Python app for CI CD





## Clone the repo 
```sh
git clone https://github.com/singh-ashok25/python-web-app.git
cd python-web-app
```





## Setup virtual env and install requirements
```sh
sudo yum -y install python3
pip3 install --upgrade pip
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

## 
```sh
python3 src/app.py 
curl http://127.0.0.1:5000/ 
export PYTHONPATH=src
pytest
```


cd ./accounts_microservice/
python -m virtualenv env
env/Scripts/activate
pip install -r requirements.txt 
set FLASK_APP=app.py 
set FLASK_ENV=env

flask db init
flask db migrate
flask db upgrade

## Docker build & run
- Build
  - docker build -t accounts_microservice .
- Run
  - docker run -p 5000:5000 accounts_microservice

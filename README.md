# veggie_tracking

Right now the data is coming from CSV files and being used to fill an SQLite database that will be transfered to the webhost for the flask app -- no interaction with the data, just reading at the moment.

The table names are:

- Beds
- Crops
- Plantings
- SoilImprovements

Create conda env:

```
conda env create --name farmapp --file=environment.yaml
```

... and then activate it:


```
conda activate farmapp
```

To initiate and fill an SQLite database from CSV files:

```
python db_init.py
```

To run the flask app in debug mode locally:

```
flask --app farmapp run --debug
```



## Deploy on pythonanywhere

You will need to create a different python environment following the pythonanywhere instructions, but otherwise things can stay the same as they are now to deploy.

Follow this to setup: https://help.pythonanywhere.com/pages/Flask/

You will need the following packages in your python environment as created on python anywhere without conda, but ultimately the two necessary depenencies are specified in the conda environment file above:

- flask
- pandas


A pip freeze at current time of deployment in the virtual environment on pythonanywhere returns this:

```
blinker==1.8.2
click==8.1.7
Flask==3.0.3
itsdangerous==2.2.0
Jinja2==3.1.4
MarkupSafe==2.1.5
numpy==1.26.4
pandas==2.2.2
python-dateutil==2.9.0.post0
pytz==2024.1
six==1.16.0
tzdata==2024.1
Werkzeug==3.0.3
```